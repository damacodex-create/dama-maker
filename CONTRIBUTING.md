# Contribuir a Dama Maker

## Flujo

1. Crear o retomar un cambio OpenSpec (`/opsx-propose`, `/opsx-apply`).
2. Crear una rama `change/<nombre>`.
3. Implementar y ejecutar `shopify theme check`.
4. Abrir un PR con una descripción clara del cambio y capturas si aplica.
5. Revisar con `theme-reviewer` y esperar CI en verde.
6. Merge a `main` para staging o a `production` solo en releases.

## Estándares

- Mantener el tema ligero, sin dependencias externas obligatorias.
- Usar LiquidDoc en snippets y blocks.
- Validar los `{% schema %}` contra los JSON schemas de Shopify.
- Usar `t:` para textos visibles y agregar las claves en `locales/`.
- Priorizar accesibilidad WCAG 2.1 AA y rendimiento.
- No hacer commit de secretos, tokens ni archivos de `.secrets/`.

## Código de conducta

Todas las contribuciones deben seguir el [Código de Conducta](./CODE_OF_CONDUCT.md).
