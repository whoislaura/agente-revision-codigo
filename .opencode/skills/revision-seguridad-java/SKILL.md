---
name: revision-seguridad-java
description: Revisa codigo Java en busca de problemas de seguridad, especialmente en manejo de datos sensibles, criptografia, entrada de usuario y gestion de recursos. Usar cuando el codigo maneje contraseñas, claves, cifrado, entrada externa o datos sensibles.
---

# Revisión de seguridad en Java

Al revisar código Java desde una perspectiva de seguridad, evalúa con
criterio real (considerando el contexto y el impacto, no una lista mecánica)
los siguientes aspectos:

## Criptografía y manejo de claves
- Uso de algoritmos débiles o obsoletos (DES, MD5, SHA-1 para hashing de
  contraseñas, ECB como modo de cifrado).
- Claves, contraseñas o secretos escritos directamente en el código
  (hardcoded), en vez de venir de variables de entorno o configuración externa.
- Uso de generadores de números aleatorios no seguros (`java.util.Random`)
  en vez de `SecureRandom` para fines criptográficos.
- Ausencia de salt en el hashing de contraseñas.

## Validación de entrada
- Datos de entrada del usuario (consola, archivos, argumentos) usados sin
  validar antes de procesarlos.
- Posibles desbordamientos o comportamientos inesperados con entradas
  vacías, nulas, o de longitud/formato inesperado.

## Manejo de excepciones y recursos
- Excepciones de seguridad silenciadas (catch vacío) que podrían ocultar
  fallos de cifrado o validación.
- Mensajes de error que exponen información sensible (rutas del sistema,
  stack traces completos, detalles de claves) al usuario final.
- Recursos que manejan datos sensibles (streams, buffers) no limpiados o
  cerrados correctamente después de su uso.

## Cómo reportar hallazgos
Para cada hallazgo, indica:
1. Archivo y línea aproximada.
2. Qué problema específico encontraste.
3. Impacto real si se explotara (no genérico: explica qué podría pasar
   en el contexto de ESTE proyecto específico).
4. Severidad: crítica / alta / media / baja, según el riesgo real, no
   una escala fija por tipo de problema.
5. Sugerencia concreta de corrección.

No reportes con la misma severidad un algoritmo débil usado en un ejemplo
académico sin datos reales, que una clave hardcodeada que protege datos
sensibles reales. El contexto del proyecto importa para calibrar severidad.
