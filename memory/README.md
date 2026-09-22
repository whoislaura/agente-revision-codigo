# Memoria persistente

`PROJECT_MEMORY.md` es la memoria de trabajo persistente del agente. OpenCode
la carga al iniciar cada sesion mediante `instructions` en `opencode.json`.

## Que debe conservarse

- Decisiones de arquitectura y sus motivos.
- Estado verificado de skills, pruebas y documentacion.
- Convenciones especificas de este proyecto.
- Pendientes que afecten la siguiente sesion.

## Que no debe conservarse

- Credenciales, tokens, contrasenas o datos personales.
- Transcripciones completas de conversaciones.
- Informacion temporal que no ayude a continuar el trabajo.
- Suposiciones no verificadas.

El permiso de edicion del agente permite escribir solamente dentro de
`memory/`. Los cambios deben ser breves, verificables y quedar registrados en
Git.
