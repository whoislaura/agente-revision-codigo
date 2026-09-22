# Registro de pruebas del agente

## Prueba 1 — 2026-09-09

**Modelo:** Kimi K2.6 (OpenCode Go)
**Agente/modo:** Build (permiso de edición denegado)
**Repositorio analizado:** Metodos-de-cifrado-descifrado-de-texto (Java, consola)
**Skill activo:** revision-estilo-java

**Prompt usado:**
"Revisa el código del proyecto Metodos-de-cifrado-descifrado-de-texto en busca de problemas de estilo y errores comunes"

**Resultado:**
- El agente identificó y mencionó el skill al inicio de su razonamiento.
- Revisó 5 archivos, solicitando permiso de lectura en cada uno (permiso
  externo configurado como "ask").
- Presentó los hallazgos organizados por impacto/severidad, tal como
  especifica el skill.
- Detectó tanto errores algorítmicos como de estilo (incluyendo comentarios
  de código poco profesionales), con sugerencias de corrección para cada uno.

**Evaluación:** el agente razonó con criterio real sobre código escrito de
forma poco cuidada, no aplicó reglas mecánicas genéricas. No se requieren
ajustes al skill en esta iteración.

## Prueba 2 — 2026-09-11

**Modelo:** Kimi K2.6 (OpenCode Go)
**Agente/modo:** Build (permiso de edición denegado)
**Repositorio analizado:** Proyecto-Final-de-IP (Java, consola)
**Skill activo:** revision-estilo-java

**Prompt usado:**
"Revisa el código del proyecto en /mnt/c/Users/Laura/workspace/Proyecto-Final-de-IP
en busca de problemas de estilo y errores comunes"

**Resultado:**
- El skill se activó correctamente, igual que en la Prueba 1.
- Hallazgos de calidad similar a la Prueba 1, con predominancia de
  problemas de estilo en este repositorio.
- El agente ajustó su análisis al código real de este proyecto (no repitió
  patrones genéricos entre pruebas).
- A diferencia de la Prueba 1, el agente también señaló explícitamente qué
  aspectos del código estaban bien, además de las sugerencias de mejora.

**Evaluación:** el skill generaliza correctamente a un segundo repositorio
distinto. El hecho de que reconozca aciertos y no solo fallos es una señal
de razonamiento calibrado, no de sesgo hacia encontrar problemas por
sistema. No se requieren ajustes al skill.

## Prueba 3 — 2026-09-13

**Modelo:** Kimi K2.6 (OpenCode Go)
**Agente/modo:** Build (permiso de edición denegado)
**Repositorio analizado:** Metodos-de-cifrado-descifrado-de-texto (Java, consola)
**Skill activo:** revision-seguridad-java

**Prompt usado:**
"Revisa el código del proyecto en /mnt/c/Users/Laura/workspace/Metodos-de-cifrado-descifrado-de-texto
en busca de problemas de seguridad"

**Resultado:**
- El agente leyó el skill y lo aplicó correctamente al análisis.
- Presentó hallazgos organizados por severidad, con forma de corrección,
  advertencias de uso y recomendaciones priorizadas.

**Evaluación:** el skill de seguridad funciona correctamente en el
repositorio para el que fue diseñado. Prueba de especificidad (verificar
que NO se active en el proyecto genérico de IP) queda pendiente, no
prioritaria por ahora.

## Prueba 4 - 2026-09-19: persistencia de memoria

**Capacidad evaluada:** memoria persistente entre sesiones.

**Sesion 1:**
"Lee la memoria de este proyecto y agrega en memory/PROJECT_MEMORY.md un dato de prueba durable: Prueba de persistencia realizada el 19 de septiembre de 2026 con la palabra clave CENTINELA-47."
- El agente agrego el dato a `memory/PROJECT_MEMORY.md`.

**Sesion 2:**
"Hay alguna palabra clave de una prueba de persistencia reciente en este proyecto?"
- El agente recupero correctamente la palabra clave `CENTINELA-47`.

**Control de permisos:**
- Al solicitar que revisara un repositorio y agregara un comentario, el agente se nego por la restriccion de edicion.
- Esto confirma que la memoria puede actualizarse sin permitir modificaciones en el codigo revisado.

**Evaluacion:** la memoria persistio entre sesiones y el limite de permisos funciono correctamente. El primer registro se anadio al final del archivo sin respetar su seccion semantica; se reorganizo en `Registro de pruebas de persistencia` y se reforzo la regla de mantenimiento.
