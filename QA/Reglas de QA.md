---
tags:
  - departamento/qa
aliases:
  - Reglas de QA
---

# Reglas de QA

Consolidación de todas las reglas de negocio que aplican al departamento de QA dentro del sistema Oranje. Referencia cruzada con [[Reglas de Negocio]] (concentrado general del sistema).

## Principio fundamental

> [!important] QA no ejecuta la operación de ningún departamento. Su función es **observar, medir y retroalimentar** para que cada área mantenga su calidad dentro de los estándares definidos.

## Jerarquía del departamento

| Rol | Función |
|---|---|
| [[Manager de QA]] | Define métricas y KPIs, supervisa operadores, consolida hallazgos, actualiza el [[Indicador de Calidad]] y presenta reportes a dirección |
| [[Operador de QA]] | Ejecutor operativo. Monitorea semáforos, mide métricas, emite observaciones formales al departamento asignado |

## Asignación de operadores

Existen **5 Operadores de QA**, cada uno asignado de forma fija a un departamento:

| Operador | Departamento supervisado |
|---|---|
| Operador 1 | [[Inspección/Inspector\|Inspección]] |
| Operador 2 | [[Hotel/Hotel\|Hotel]] |
| Operador 3 | [[Colaborador/Colaborador\|Colaborador]] |
| Operador 4 | [[Ventas/Ventas\|Ventas]] |
| Operador 5 | [[Reclutamiento/Reclutamiento\|Reclutamiento]] |

> [!note] La asignación es fija: cada operador conoce a fondo la operación del departamento que supervisa.

> [!note] Alcance de este documento
> Las métricas y KPIs específicos por departamento están definidos en [[QA/Métricas y KPIs por Departamento|Métricas y KPIs por Departamento]]. Este documento cubre la estructura general del módulo de QA: roles, flujo de observaciones y escalación.

## Métricas y observaciones

- El [[Operador de QA]] monitorea los semáforos del departamento asignado ([[Semáforo del Colaborador]], [[Semáforo de Requisición]], [[Semáforo Onboarding]], etc.) como fuente de contexto operativo.
- Mide métricas de desempeño: tiempos de respuesta, tasas de éxito, frecuencia de errores y cumplimiento de procesos.
- Emite **observaciones formales** al departamento con hallazgos específicos y recomendaciones de mejora.
- Reporta al [[Manager de QA]] con los datos recopilados y el estado de calidad.
- Las métricas concretas que cada operador monitorea están definidas en [[QA/Métricas y KPIs por Departamento|Métricas y KPIs por Departamento]].

## Indicador de Calidad

El [[Core/Módulos/Semáforos/Indicador de Calidad|Indicador de Calidad]] es el instrumento de medición propio de QA. Cada departamento tiene su propio indicador independiente; el estado inicial es **Verde**.

| Color | Estado | Descripción |
|---|---|---|
| Verde | Calidad óptima | Métricas dentro de parámetros esperados, sin observaciones pendientes |
| Amarillo | Calidad en riesgo | Métricas fuera de rango o existen observaciones pendientes sin atender |
| Rojo | Calidad crítica | Métricas muy por debajo del estándar o acumulación de observaciones ignoradas |

### Transiciones

- **→ Verde**: estado inicial cuando QA comienza a supervisar un departamento.
- **Verde → Amarillo**: cuando el [[Operador de QA]] detecta métricas fuera de rango o emite observaciones no atendidas.
- **Amarillo → Rojo**: cuando las observaciones persisten sin atención o las métricas se deterioran significativamente.
- **Rojo → Amarillo**: cuando el departamento comienza a atender observaciones y muestra mejora.
- **Amarillo → Verde**: cuando todas las observaciones están resueltas y las métricas regresan a parámetros.

### Quién actualiza el indicador

| Acción | Responsable |
|---|---|
| Proponer cambio de estado con base en mediciones | [[Operador de QA]] |
| Validar y aprobar la actualización | [[Manager de QA]] |

> [!important] Solo el [[Manager de QA]] puede actualizar formalmente el [[Indicador de Calidad]] de cada departamento.

## Escalamiento

- Departamento en estado **Rojo** sin mejora tras notificación → el [[Manager de QA]] escala el caso a dirección.
- El [[Manager de QA]] presenta reportes de calidad a la dirección con hallazgos, tendencias y áreas de mejora.

## Resumen de responsabilidades por rol

| Acción | [[Operador de QA]] | [[Manager de QA]] |
|---|---|---|
| Monitorear semáforos del departamento asignado | Sí | No |
| Medir métricas de desempeño | Sí | No |
| Emitir observaciones formales | Sí | No |
| Alimentar datos del Indicador de Calidad | Sí | No |
| Definir métricas y KPIs | No | Sí |
| Validar y aprobar cambios del Indicador | No | Sí |
| Consolidar hallazgos de todos los operadores | No | Sí |
| Presentar reportes a dirección | No | Sí |
| Escalar departamento en Rojo sin mejora | No | Sí |
| Supervisar operadores de QA | No | Sí |

## Relacionado

- [[Reglas de Negocio]]
- [[Manager de QA]]
- [[Operador de QA]]
- [[Core/Módulos/Semáforos/Indicador de Calidad|Indicador de Calidad]]
- [[Semáforo del Colaborador]]
- [[Semáforo de Requisición]]
- [[Semáforo Onboarding]]
- [[Semáforo de Urgencia de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
