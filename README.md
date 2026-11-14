# Dama Maker

Tema Shopify para una tienda de figuras 3D para el hogar, la oficina y accesorios.
Diseñado para publicarse en Shopify Theme Store con foco en accesibilidad, rendimiento y facilidad de edición.

## Requisitos

- [Shopify CLI](https://shopify.dev/docs/api/shopify-cli) 5+
- Node.js 22+
- Acceso a la tienda de desarrollo `dama-maker.myshopify.com`

Si usas VS Code:

- [Shopify Liquid VS Code Extension](https://shopify.dev/docs/storefronts/themes/tools/shopify-liquid-vscode)

## Desarrollo

```bash
shopify theme dev --store dama-maker.myshopify.com
shopify theme check
```

## Estructura

```bash
.
├── assets          # CSS, JS, imágenes y fuentes
├── blocks          # Componentes reutilizables y anidables
├── config          # Ajustes globales del tema
├── layout          # Layouts base
├── locales         # Traducciones
├── sections        # Secciones personalizables
├── snippets        # Fragmentos Liquid reutilizables
└── templates       # Plantillas JSON
```

Los archivos del tema viven en la raíz del repositorio para mantener la integración GitHub ↔ Shopify.

## Flujo de trabajo

1. Crear o retomar un cambio OpenSpec (`/opsx-propose`, `/opsx-apply`).
2. Trabajar en una rama `change/<nombre>`.
3. Implementar y ejecutar `shopify theme check`.
4. Abrir PR y esperar revisión + CI en verde.
5. Merge a `main` (staging) o `production` (solo releases).

Consulta [CONTRIBUTING.md](./CONTRIBUTING.md) para más detalle.

## Convenciones

- LiquidDoc en snippets y blocks.
- `{% stylesheet %}` y `{% javascript %}` dentro de snippets, blocks y sections.
- Traducciones con `t:` y claves en `locales/`.
- Variables CSS para settings de una propiedad; clases para settings de múltiples propiedades.
- Sin dependencias externas obligatorias ni librerías pesadas.

## Licencia

Distribuido bajo la licencia [MIT](./LICENSE.md). El proyecto deriva de Shopify Skeleton Theme y conserva el aviso de licencia original.
