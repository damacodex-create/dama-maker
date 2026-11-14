## Why

Dama Maker necesita un tema Shopify propio para vender figuras 3D de hogar, oficina y accesorios.
El tema actual es un scaffold de Skeleton con contenido de demostración, sin identidad de marca ni
las secciones necesarias para merchandising, y no cumple todavía los requisitos para publicarse en
Shopify Theme Store. Construirlo ahora permite validar la experiencia de compra en la tienda de
desarrollo y preparar un release publicable.

## What Changes

- Reemplazar el scaffold de demostración por una base de tema Dama Maker con identidad visual,
  tipografía, color, espaciado y componentes reutilizables.
- Implementar la home con hero, productos destacados, categorías, historia de marca, testimonios
  y newsletter.
- Implementar la ficha de producto con galería, variantes, precio, add to cart, beneficios,
  envío/devoluciones, productos relacionados y datos estructurados.
- Implementar colecciones con grilla, filtros, orden, paginación, búsqueda y estados vacíos.
- Implementar carrito (drawer y página), actualización de cantidades, totales y handoff a checkout.
- Implementar páginas de contenido: about, contacto, FAQ, blog y políticas, además de 404.
- Incorporar i18n con `t:` y locales `en`/`es`, presets del theme editor y documentación de uso.
- Cumplir accesibilidad WCAG 2.1 AA, rendimiento, responsive y Theme Check sin offenses.
- Mantener el tema sin dependencias externas obligatorias ni librerías pesadas.
- Conectar el repo a Shopify mediante GitHub App y dejar `main` como staging y `production` para releases.

**No-goals**

- No se implementa checkout propio: se usa el checkout de Shopify.
- No se integran apps de terceros, reseñas, loyalty ni herramientas de marketing en esta fase.
- No se migran productos, colecciones ni contenido real; se usan datos de la tienda dev.
- No se publica el tema en Theme Store dentro de este cambio; solo se deja listo y auditado.

## Capabilities

### New Capabilities

- `storefront-foundation`: ajustes globales, layout, design tokens, header, footer, navegación,
  SEO base, responsive y accesibilidad estructural.
- `home-page`: secciones de home, merchandising, contenido de marca y presets.
- `product-detail`: página de producto, galería, variantes, compra, información de confianza y
  productos relacionados.
- `collection-browse`: páginas de colección, búsqueda, filtros, orden, paginación y estados vacíos.
- `cart-and-checkout`: carrito, drawer, cantidades, totales y transición a checkout.
- `content-and-support`: about, contacto, FAQ, blog, políticas y 404.
- `theme-store-readiness`: accesibilidad, rendimiento, i18n, presets, documentación, Theme Check y
  compatibilidad de navegadores.

### Modified Capabilities

Ninguna. No existen specs previas en `openspec/specs/`.

## Impact

- Archivos del tema en la raíz: `assets/`, `blocks/`, `config/`, `layout/`, `locales/`, `sections/`,
  `snippets/` y `templates/`.
- `config/settings_schema.json` y `config/settings_data.json` (solo vía theme editor/CLI).
- `locales/en.default.json`, `locales/es.json` y claves `t:` en todo el tema.
- `sections/hello-world.liquid` se reemplaza por la home real.
- `README.md`, `CONTRIBUTING.md` y documentación de uso del tema.
- `.github/workflows/theme-check.yml` y flujo de PR/review.
- Integración GitHub ↔ Shopify mediante Shopify GitHub App (acción manual en Shopify Admin).
- Sin cambios de backend, APIs externas ni dependencias obligatorias.

## Criterios de aceptación

- `shopify theme check` termina con 0 offenses.
- Lighthouse mobile en home, producto y colección: Performance ≥ 90 y Accessibility ≥ 95 en preview local.
- WCAG 2.1 AA: navegación por teclado, foco visible, contraste de texto ≥ 4.5:1 y formularios con labels.
- Todos los textos visibles usan `t:` y existen claves en `en` y `es`.
- Presets del theme editor disponibles para home, producto, colección, carrito, about, contacto y FAQ.
- Layout funcional de 320 px a 1440 px sin desbordes horizontales.
- Sin dependencias externas obligatorias ni librerías pesadas.
- Checklist de requisitos de Shopify Theme Store completo y documentado.
