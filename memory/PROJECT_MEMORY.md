# Memoria del proyecto

## Identidad

- Proyecto: agente de revision de codigo para la Fase II de la hoja de ruta del ICIMAF.
- Plataforma: OpenCode.
- Propietaria: Laura Garcia Miguel.
- Objetivo: revisar repositorios reales y emitir retroalimentacion razonada sobre estilo, errores y seguridad.

## Estado verificado

- Existe el skill `.opencode/skills/revision-estilo-java/SKILL.md`.
- Existe el skill `.opencode/skills/revision-seguridad-java/SKILL.md`.
- El skill de estilo fue probado en dos repositorios Java.
- El skill de seguridad fue probado en un repositorio Java con cifrado.
- La memoria persistente se carga desde este archivo mediante `opencode.json`.
- El agente puede editar solamente archivos dentro de `memory/`.

## Decisiones vigentes

- El agente debe razonar sobre el contexto del codigo y no comportarse como un linter mecanico.
- La edicion del codigo revisado permanece denegada.
- No se deben guardar secretos ni datos sensibles en esta memoria.

## Registro de pruebas de persistencia

- Prueba de persistencia realizada el 19 de septiembre de 2026 con la palabra clave CENTINELA-47.

## Proximos pasos

- Completar la justificacion de OpenCode en `docs/decisiones.md`.
- Versionar prompts y crear la documentacion tecnica de arquitectura.
- Evaluar una integracion MCP despues de validar la memoria.

## Regla de mantenimiento

Actualizar esta memoria solo con hechos duraderos y comprobados. Cuando la
persona usuaria pida recordar una decision o un dato de trabajo, incorporarlo
en la seccion correspondiente sin guardar la transcripcion completa.
Los resultados de pruebas de persistencia deben ir en `Registro de pruebas de persistencia`.
