---
name: revision-estilo-java
description: Revisa codigo Java en busca de problemas de estilo, malas practicas y errores comunes de logica. Usar cuando se analice codigo fuente .java.
---

# Revisión de estilo y errores comunes en Java

Al revisar código Java, evalúa con criterio (no como una lista de checkboxes
mecánica) los siguientes aspectos:

## Estilo
- Convenciones de nombres: clases en PascalCase, métodos y variables en camelCase,
  constantes en MAYUSCULAS_CON_GUION_BAJO.
- Métodos demasiado largos o que hacen más de una cosa (responsabilidad única).
- Uso de nombres de variables poco descriptivos (a, x, temp, data sin contexto).

## Errores comunes de lógica
- Comparación de Strings u objetos con `==` en vez de `.equals()`.
- Posibles NullPointerException: acceso a objetos sin verificar null antes.
- Manejo de excepciones: catch vacíos, captura genérica de `Exception` que
  oculta el error real, excepciones no registradas ni comunicadas.
- Recursos no cerrados (Scanner, streams de archivos) sin try-with-resources.
- Bucles con condiciones de salida potencialmente incorrectas (off-by-one).

## Cómo reportar hallazgos
Para cada hallazgo, indica:
1. Archivo y línea aproximada.
2. Qué problema específico encontraste (no genérico).
3. Por qué es un problema (impacto real, no solo "es mala práctica").
4. Severidad: alta / media / baja, con tu propio criterio según el contexto
   del código, no una regla fija.

No reportes como error de la misma severidad un problema cosmético de nombres
que un NullPointerException real. Prioriza según impacto.
