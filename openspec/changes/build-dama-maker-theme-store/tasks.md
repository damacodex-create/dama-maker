## 0. Setup (completado)

- [x] 0.1 Aplanar el tema a la raíz del repo para Shopify GitHub App.
- [x] 0.2 Crear `AGENTS.md`, `opencode.jsonc` y agentes del equipo.
- [x] 0.3 Configurar OpenSpec y crear el cambio `build-dama-maker-theme-store`.
- [x] 0.4 Crear CI de Theme Check y validar la configuración de OpenCode.
- [x] 0.5 Actualizar metadata del tema y textos base de Dama Maker.

## 1. Foundation

- [ ] 1.1 Auditar el scaffold Skeleton y retirar contenido de demostración innecesario.
- [ ] 1.2 Crear `snippets/theme-variables.liquid` con variables CSS desde settings.
- [ ] 1.3 Reorganizar `config/settings_schema.json` en marca, colores, tipografía, layout y redes.
- [ ] 1.4 Implementar `layout/theme.liquid` con skip link, announcement, header, main, footer y cart drawer.
- [ ] 1.5 Crear `sections/header.liquid` con navegación desktop/mobile, búsqueda y carrito.
- [ ] 1.6 Crear `sections/footer.liquid` con menús, contacto, políticas y redes.
- [ ] 1.7 Crear `snippets/meta-tags.liquid` con title, description, canonical y Open Graph.
- [ ] 1.8 Crear `assets/critical.css` con reset, tokens, tipografía base y utilidades.
- [ ] 1.9 Crear `locales/en.default.json` y `locales/es.json` con claves base.
- [ ] 1.10 Verificar Theme Check, navegación por teclado y layout a 320 px.

## 2. Home

- [ ] 2.1 Crear `sections/hero.liquid` con imagen, heading, subheading, CTA y overlay.
- [ ] 2.2 Crear `snippets/product-card.liquid` con LiquidDoc y estados sin imagen.
- [ ] 2.3 Crear `sections/featured-products.liquid` con colección y límite configurables.
- [ ] 2.4 Crear `sections/category-tiles.liquid` para hogar, oficina y accesorios.
- [ ] 2.5 Crear `sections/brand-story.liquid` con texto, imagen y CTA opcional.
- [ ] 2.6 Crear `sections/testimonials.liquid` con bloques de quote, autor y rating.
- [ ] 2.7 Crear `sections/newsletter.liquid` con formulario Shopify y feedback accesible.
- [ ] 2.8 Construir `templates/index.json` con el preset de home.
- [ ] 2.9 Verificar home responsive, settings del editor y Theme Check.

## 3. Product detail

- [ ] 3.1 Crear `sections/main-product.liquid` con bloques de media, título, precio, variantes, cantidad y compra.
- [ ] 3.2 Implementar galería con thumbnails y navegación por teclado.
- [ ] 3.3 Implementar `variant-selects` para actualizar variante, precio, disponibilidad y media.
- [ ] 3.4 Implementar `product-form` y `quantity-input` con Cart AJAX y fallback sin JS.
- [ ] 3.5 Implementar estado out-of-stock con mensaje accesible y acción deshabilitada.
- [ ] 3.6 Implementar bloques de confianza: envío, devoluciones y materiales.
- [ ] 3.7 Implementar productos relacionados desde una colección configurable.
- [ ] 3.8 Agregar JSON-LD de Product y breadcrumbs.
- [ ] 3.9 Crear `templates/product.json` con presets y bloques por defecto.
- [ ] 3.10 Verificar add to cart, teclado, lector de pantalla y Theme Check.

## 4. Collection and search

- [ ] 4.1 Crear `sections/main-collection.liquid` con grid responsive y paginación.
- [ ] 4.2 Crear `collection-filters` con filtros nativos, orden y estado activo.
- [ ] 4.3 Crear `sections/main-search.liquid` reutilizando el grid de productos.
- [ ] 4.4 Implementar empty states para colección y búsqueda.
- [ ] 4.5 Agregar metadata de colección y breadcrumbs.
- [ ] 4.6 Crear `templates/collection.json`, `list-collections.json` y `search.json`.
- [ ] 4.7 Verificar filtros, orden, paginación y mobile.

## 5. Cart and checkout

- [ ] 5.1 Crear `cart-drawer` con `<dialog>`, foco, Escape y restauración de foco.
- [ ] 5.2 Crear `snippets/cart-line-item.liquid` y `snippets/cart-summary.liquid`.
- [ ] 5.3 Implementar actualización de cantidad y eliminación con Cart API + Section Rendering.
- [ ] 5.4 Crear `sections/main-cart.liquid` con página de carrito y empty state.
- [ ] 5.5 Implementar anuncios `aria-live` para cambios de cantidad y total.
- [ ] 5.6 Implementar fallback progresivo sin JavaScript.
- [ ] 5.7 Crear `templates/cart.json`.
- [ ] 5.8 Verificar add/update/remove/checkout, teclado y lector de pantalla.

## 6. Content and support

- [ ] 6.1 Crear `sections/main-page.liquid` y plantillas de página base.
- [ ] 6.2 Crear página About con secciones y preset.
- [ ] 6.3 Crear página de contacto con formulario Shopify y validación accesible.
- [ ] 6.4 Crear página FAQ con acordeón accesible.
- [ ] 6.5 Crear blog listing y artículo con metadata y paginación.
- [ ] 6.6 Crear plantillas de políticas y 404.
- [ ] 6.7 Verificar formularios, acordeón, teclado y Theme Check.

## 7. Theme Store readiness

- [ ] 7.1 Ejecutar axe/Lighthouse en home, producto, colección, carrito y contacto; corregir hallazgos.
- [ ] 7.2 Auditoría manual de teclado y VoiceOver en el flujo de compra.
- [ ] 7.3 Auditoría responsive en 320, 375, 768, 1024 y 1440 px.
- [ ] 7.4 Auditar claves `t:` en `en`/`es` y eliminar strings hardcodeados.
- [ ] 7.5 Completar presets de plantillas y secciones en el theme editor.
- [ ] 7.6 Actualizar README con setup, uso del editor y pasos de release.
- [ ] 7.7 Crear `docs/theme-store-checklist.md` con requisitos y evidencia.
- [ ] 7.8 Ejecutar `shopify theme check` y corregir todas las offenses.
- [ ] 7.9 Ejecutar `theme-store-auditor` y `theme-reviewer`; resolver hallazgos.
- [ ] 7.10 Verificar ausencia de dependencias externas obligatorias y soporte de navegadores.

## 8. Integration and release

- [ ] 8.1 Hacer push de `main` a GitHub y verificar CI en verde.
- [ ] 8.2 Conectar Shopify GitHub App al repo y a `main` (acción manual en Shopify Admin).
- [ ] 8.3 Previsualizar el tema en Shopify Admin y probar el theme editor.
- [ ] 8.4 Crear `production` y completar el checklist de release.
- [ ] 8.5 Etiquetar `v1.0.0` después de la aprobación explícita.
