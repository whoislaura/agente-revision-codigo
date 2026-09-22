# Decisiones de Arquitectura (ADRs)

## ADR-001: Elección de OpenCode como plataforma agéntica

**Fecha:** 2026-09-09
**Estado:** Borrador — pendiente de completar justificación

**Contexto:** Necesito elegir una plataforma agéntica de desarrollo para
construir el agente de revisión de código, entre las opciones sugeridas
por la hoja de ruta: Claude Code, OpenCode o el agente integrado en VS Code.

**Decisión:** Uso OpenCode.

**Justificación:**
- TODO: precisar argumento de costo (¿costo de qué, comparado con qué?)
- TODO: precisar por qué la variedad de modelos importa para ESTE proyecto

**Alternativas descartadas:**
- TODO

**Consecuencias:**
- TODO

## ADR-002: Memoria persistente local y versionada

**Fecha:** 2026-09-19
**Estado:** Aceptada

**Contexto:** La Fase II exige conservar contexto entre sesiones. La version
instalada de OpenCode no expone un campo `memory` nativo en su esquema de
configuracion, por lo que no conviene depender de una funcionalidad
experimental o de un servicio externo para esta capacidad.

**Decisión:** Usar `memory/PROJECT_MEMORY.md` como memoria curada del proyecto
y cargarla en cada sesion mediante el campo `instructions` de `opencode.json`.
El permiso de edicion queda limitado a `memory/**`.

**Alternativas descartadas:**
- Memoria global del usuario: no queda aislada por repositorio ni reproducible
  para un tercero.
- Un plugin de memoria externo: agrega dependencia y comportamiento no
  necesario antes de validar el requisito basico.
- Guardar el historial completo de sesiones: mezcla informacion temporal con
  conocimiento durable y puede conservar datos sensibles.

**Consecuencias:**
- La memoria es auditable, versionable y reproducible desde el repositorio.
- La memoria requiere mantenimiento curado; no realiza extraccion automatica
  de aprendizajes.
