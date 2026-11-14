## Context

El repositorio parte de Shopify Skeleton Theme, un scaffold mínimo con `sections/hello-world.liquid`
como contenido de demostración. Los archivos del tema ya están en la raíz para que Shopify GitHub App
pueda sincronizar `main` y `production`. La tienda de desarrollo es `dama-maker.myshopify.com`.

Dama Maker vende figuras 3D para hogar, oficina y accesorios. El tema debe equilibrar una estética
cálida y de producto con requisitos estrictos de Shopify Theme Store: accesibilidad WCAG 2.1 AA,
rendimiento, theme editor claro, i18n y ausencia de dependencias obligatorias.

Restricciones:

- Liquid, JSON templates, sections, blocks, snippets y LiquidDoc.
- Sin frameworks ni librerías pesadas.
- Textos visibles con `t:` y locales `en`/`es`.
- Theme Check sin offenses.
- El tema debe funcionar sin apps adicionales.

## Goals / Non-Goals

**Goals:**

- Construir una base de tema reutilizable con design tokens y componentes compartidos.
- Cubrir el flujo completo: home → colección → producto → carrito → checkout.
- Dejar el theme editor usable con presets y settings agrupados.
- Cumplir accesibilidad, rendimiento, i18n y documentación para Theme Store.
- Mantener JavaScript progresivo: el flujo principal funciona sin JS cuando sea posible.

**Non-Goals:**

- Checkout personalizado, apps de reseñas, loyalty, analytics avanzado o marketing automation.
- Migración de catálogo real o contenido de marca definitivo.
- Soporte multi-market complejo más allá de `en`/`es`.
- Publicación en Theme Store dentro de este cambio.

## Decisions

### Arquitectura de carpetas y plantillas

- `layout/theme.liquid` incluye skip link, announcement bar, header, `main`, footer y cart drawer.
- `layout/password.liquid` y `layout/gift_card.liquid` se conservan/adaptan si existen en el scaffold.
- Plantillas JSON: `index`, `product`, `collection`, `list-collections`, `search`, `cart`, `page`,
  `page.about`, `page.contact`, `page.faq`, `blog`, `article`, `404`.
- Secciones compartidas: `header`, `footer`, `announcement-bar`, `main-product`, `main-collection`,
  `main-cart`, `main-search`, `main-page`, `main-blog`, `main-article`, `main-404`.
- Secciones de home: `hero`, `featured-products`, `category-tiles`, `brand-story`, `testimonials`,
  `newsletter`.
- Snippets compartidos: `product-card`, `price`, `responsive-image`, `pagination`, `icon`,
  `meta-tags`, `skip-to-content`, `cart-drawer`, `cart-line-item`, `cart-summary`.

**Por qué:** sigue el modelo de Shopify, mantiene secciones y bloques editables y evita duplicación.

**Alternativa considerada:** una sola sección gigante por plantilla. Se descarta porque limita al
comerciante y complica el mantenimiento.

### Design tokens y CSS

- Variables CSS globales para color, tipografía, espaciado, radios y sombras, generadas desde
  `settings` en un snippet de variables incluido en el layout.
- `assets/critical.css` para reset, tokens, tipografía base, utilidades y layout.
- `{% stylesheet %}` por sección/block para estilos encapsulados.
- Convención: variable CSS para settings de una propiedad; clase para settings de múltiples propiedades.
- Paleta inicial: base cálida neutra, tinta oscura y un acento terracota; tipografía de titular con
  carácter y cuerpo legible. Los valores exactos quedan como settings.

**Por qué:** permite personalización sin recompilar y mantiene el CSS cerca del componente.

**Alternativa considerada:** Tailwind u otro framework. Se descarta por dependencia, peso y
requisitos de build.

### JavaScript progresivo

- Custom elements nativos: `cart-drawer`, `product-form`, `variant-selects`, `quantity-input`,
  `collection-filters`, `faq-accordion`.
- `cart-drawer` usa `<dialog>` nativo para foco, Escape y backdrop; restaura foco al cerrar.
- Add to cart y cambios de carrito usan Cart AJAX API y Section Rendering API.
- Fallback sin JS: formularios POST a `/cart/add`, página de carrito completa y filtros GET.
- Sin bundler: módulos ES con `defer` y `{% javascript %}`.

**Por qué:** menos peso, mejor accesibilidad nativa y menor superficie de fallo.

**Alternativa considerada:** React/Preact. Se descarta por peso y porque Theme Store no lo requiere.

### Accesibilidad

- Skip link como primer elemento focusable; landmarks `header`, `nav`, `main`, `footer`.
- Foco visible con `:focus-visible` y contraste mínimo 3:1 para indicadores.
- Contraste de texto ≥ 4.5:1; textos grandes ≥ 3:1.
- `<dialog>` para drawer; `aria-expanded`, `aria-controls`, `aria-live="polite"` para updates.
- Formularios con `<label>`, `aria-describedby` para errores y mensajes de éxito.
- FAQ con `<details>/<summary>` o acordeón con `aria-expanded`; sin trampas de foco.
- Respeto a `prefers-reduced-motion`; animaciones no esenciales desactivadas.
- Imágenes decorativas con `alt=""`; imágenes de producto con alt descriptivo.

**Por qué:** WCAG 2.1 AA es requisito de Theme Store y reduce riesgo de rechazo.

### Rendimiento

- Imágenes con `image_url` + `widths`/`sizes`, `width`/`height` explícitos y `loading="lazy"`
  salvo la imagen LCP del hero/producto principal.
- `fetchpriority="high"` solo para el LCP; sin preloads indiscriminados.
- Fuentes con `font-display: swap` y solo pesos necesarios.
- JS diferido y limitado a componentes interactivos.
- Evitar CSS no usado y animaciones costosas; usar transform/opacity.
- Presupuesto: Lighthouse mobile ≥ 90 Performance y ≥ 95 Accessibility en home, producto y colección.

### Theme editor

- Settings globales agrupados: marca, colores, tipografía, layout, redes sociales.
- Cada sección con `presets`, `max_blocks` cuando aplique y labels orientados al resultado.
- Bloques de producto para media, título, precio, variantes, cantidad, compra, confianza,
  descripción y complementarios.
- Presets de página para home, about, contacto, FAQ y carrito.
- `info` y `paragraph` para explicar settings complejos.

### i18n y SEO

- `locales/en.default.json` y `locales/es.json`; claves semánticas y pluralización.
- `t:` en labels de schema y `{{ 'key' | t }}` en Liquid.
- `snippets/meta-tags.liquid` con title, description, canonical, Open Graph y Twitter card.
- JSON-LD: `Product`, `BreadcrumbList`, `Organization`, `WebSite`.
- URLs con `routes` y objetos de Shopify; sin URLs hardcodeadas.

### Integración y despliegue

- `main` como staging conectado a Shopify GitHub App.
- `production` solo para releases aprobados.
- CI con `shopify theme check` en PR y push.
- Preview local con `shopify theme dev --store dama-maker.myshopify.com`.
- Rollback: revertir commit y usar versiones de tema de Shopify si hiciera falta.

## Risks / Trade-offs

- **Revisión subjetiva de Theme Store** → checklist explícito, auditoría con `theme-store-auditor`
  y revisión con `theme-reviewer`.
- **Performance con imágenes de producto grandes** → responsive images, lazy loading, límites de
  tamaño y auditoría Lighthouse.
- **Complejidad del cart AJAX** → progressive enhancement y fallback a formularios/página completa.
- **Costo de mantener custom elements** → componentes pequeños, documentados y sin dependencias.
- **Theme editor sobrecargado** → presets, grupos y labels claros; evitar settings redundantes.
- **Traducciones incompletas** → Theme Check, revisión de claves y prueba en locale español.
- **Datos de tienda dev incompletos** → usar productos/colecciones de prueba y documentar supuestos.

## Migration Plan

1. Foundation: tokens, layout, header/footer, meta tags, i18n base.
2. Home: hero, featured products, categorías, brand story, testimonios, newsletter.
3. Producto: galería, variantes, compra, confianza, relacionados, JSON-LD.
4. Colección y búsqueda: grid, filtros, orden, paginación, empty states.
5. Carrito: drawer, página, cantidades, totales, checkout.
6. Contenido: about, contacto, FAQ, blog, políticas, 404.
7. Compliance: accesibilidad, performance, presets, documentación, Theme Check, auditoría.
8. Integración: conectar Shopify GitHub App, push a `main`, preview y release a `production`.

## Open Questions

- ¿Paleta y tipografía definitivas de la marca o se validan con el theme editor?
- ¿Habrá fotografía de producto real o se usan placeholders hasta el lanzamiento?
- ¿Se soportan solo `en`/`es` o se prevén más locales?
- ¿Los testimonios serán manuales o se integrará una app de reseñas más adelante?
- ¿Se requiere analytics/tracking en el tema o se maneja con Shopify/pixel apps?
