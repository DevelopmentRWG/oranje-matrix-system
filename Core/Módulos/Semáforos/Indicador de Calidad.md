---
tags:
  - modulo/core
  - departamento/qa
aliases:
  - Indicador de Calidad
  - Calidad Verde
  - Calidad Amarillo
  - Calidad Rojo
---

# Indicador de Calidad

Indicador que refleja el nivel de calidad operativa de cada departamento, alimentado por el [[Operador de QA]] asignado y supervisado por el [[Manager de QA]]. Cada departamento tiene su propio indicador independiente.

> [!info]
> Este indicador no reemplaza a los semáforos existentes ([[Semáforo del Colaborador]], [[Semáforo de Requisición]], etc.). QA **consulta** esos semáforos como fuente de datos y emite su evaluación en este indicador.

## Estados

| Color    | Estado            | Descripción                                                                                        |
| -------- | ----------------- | -------------------------------------------------------------------------------------------------- |
| Verde    | Calidad óptima    | Métricas dentro de parámetros esperados, sin observaciones pendientes.                             |
| Amarillo | Calidad en riesgo | Métricas fuera de rango o existen observaciones pendientes sin atender por parte del departamento. |
| Rojo     | Calidad crítica   | Métricas muy por debajo del estándar o acumulación de observaciones ignoradas por el departamento. |

## Reglas clave

### Transiciones

- **→ Verde**: estado inicial cuando QA comienza a supervisar un departamento, o cuando el departamento atiende todas las observaciones y sus métricas vuelven a parámetros.
- **Verde → Amarillo**: cuando el [[Operador de QA]] detecta métricas fuera de rango o emite observaciones que el departamento no ha atendido.
- **Amarillo → Rojo**: cuando las observaciones persisten sin atención o las métricas se deterioran significativamente.
- **Rojo → Amarillo**: cuando el departamento comienza a atender las observaciones y muestra mejora en métricas.
- **Amarillo → Verde**: cuando todas las observaciones están resueltas y las métricas regresan a parámetros.

### Quién actualiza el indicador

- El [[Operador de QA]] propone el cambio de estado con base en sus mediciones.
- El [[Manager de QA]] valida y aprueba el cambio.

> [!important]
> Un departamento en estado **Rojo** requiere atención inmediata. El [[Manager de QA]] escala el caso a la dirección si no hay mejora tras la notificación.

## Relacionado

- [[QA/QA|QA]]
- [[Manager de QA]]
- [[Operador de QA]]
- [[Semáforo del Colaborador]]
- [[Semáforo de Requisición]]
- [[Semáforo Onboarding]]
- [[Semáforo de Urgencia de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
