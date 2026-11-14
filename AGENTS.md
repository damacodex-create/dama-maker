# Dama Maker — Shopify Theme

Tema Shopify para una tienda de figuras 3D para el hogar, la oficina y accesorios.
Objetivo: publicar **Dama Maker** en Shopify Theme Store.

> MANDATORY: when working with Liquid themes, call `learn_shopify_api` once. If the Shopify AI
> Toolkit is unavailable, read `docs/shopify-theme-reference.md` before changing theme code.

## Estructura

- Los archivos del tema están en la raíz del repo (requisito de la integración GitHub ↔ Shopify):
  `assets/`, `blocks/`, `config/`, `layout/`, `locales/`, `sections/`, `snippets/`, `templates/`.
- `openspec/` contiene propuestas, diseños, specs y tareas.
- `.opencode/` contiene comandos, skills y agentes del equipo.
- `docs/shopify-theme-reference.md` es la referencia completa de Shopify (Liquid, schemas, i18n, LiquidDoc).
- `.github/workflows/` ejecuta Theme Check en CI.

## Comandos

```bash
shopify theme dev --store dama-maker.myshopify.com
shopify theme check
openspec list
openspec status --change <name>
```

## Flujo de trabajo

1. Crear o retomar un cambio OpenSpec (`/opsx-propose`, `/opsx-apply`).
2. Trabajar en una rama `change/<nombre>`.
3. Implementar y ejecutar `shopify theme check`.
4. Abrir PR; revisar con el subagente `theme-reviewer` y esperar CI en verde.
5. Merge a `main` (staging) o `production` (solo releases).

## Convenciones

- LiquidDoc en snippets y blocks.
- `{% stylesheet %}` y `{% javascript %}` dentro de snippets, blocks y sections.
- Traducciones con `t:` y claves en `locales/`.
- Validar `{% schema %}` contra los JSON schemas de Shopify.
- Variables CSS para settings de una propiedad; clases para settings de múltiples propiedades.
- Sin dependencias externas obligatorias ni librerías pesadas.

## Límites

- No hacer commit de secretos, tokens ni `.secrets/`.
- No publicar el tema ni hacer merge sin aprobación explícita.
- No editar `config/settings_data.json` manualmente salvo que se pida.
- No modificar archivos fuera del repositorio.
