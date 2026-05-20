---
tags:
  - department/qa
aliases:
  - QA Rules
---

# QA Rules

Consolidation of all business rules that apply to the QA department within the Oranje system. Cross-reference with [[Reglas de Negocio]] (system-wide consolidated rules).

## Fundamental Principle

> [!important] QA does not execute the operations of any department. Its function is to **observe, measure, and provide feedback** so that each area maintains its quality within the defined standards.

## Department Hierarchy

| Role | Function |
|---|---|
| [[Manager de QA]] | Defines metrics and KPIs, supervises operators, consolidates findings, updates the [[Indicador de Calidad]], and presents reports to management |
| [[Operador de QA]] | Operational executor. Monitors status indicators, measures metrics, issues formal observations to the assigned department |

## Operator Assignments

There are **6 QA Operators**, each permanently assigned to one department:

| Operator | Supervised Department |
|---|---|
| Operator 1 | [[Inspección/Inspector\|Inspection]] |
| Operator 2 | [[Hotel/Hotel\|Hotel]] |
| Operator 3 | [[Colaborador/Colaborador\|Associate]] |
| Operator 4 | [[Ventas/Ventas\|Sales]] |
| Operator 5 | [[Reclutamiento/Reclutamiento\|Recruitment]] |
| Operator 6 | [[Customer Service/Customer Service\|Customer Service]] |

> [!note] The assignment is fixed: each operator has an in-depth knowledge of the department they supervise.

> [!note] Scope of this document
> The specific metrics and KPIs per department are defined in [[QA/Métricas y KPIs por Departamento|Metrics and KPIs by Department]]. This document covers the general structure of the QA module: roles, observation flow, and escalation.

## Metrics and Observations

- The [[Operador de QA]] monitors the status indicators of the assigned department ([[Semáforo del Colaborador]], [[Semáforo de Requisición]], [[Semáforo Onboarding]], etc.) as a source of operational context.
- Measures performance metrics: response times, success rates, error frequency, and process compliance.
- Issues **formal observations** to the department with specific findings and improvement recommendations.
- Reports to the [[Manager de QA]] with the collected data and quality status.
- The specific metrics each operator monitors are defined in [[QA/Métricas y KPIs por Departamento|Metrics and KPIs by Department]].

## Quality Indicator

The [[Core/Módulos/Semáforos/Indicador de Calidad|Quality Indicator]] is QA's own measurement instrument. Each department has its own independent indicator; the initial status is **Green**.

| Color | Status | Description |
|---|---|---|
| Green | Optimal quality | Metrics within expected parameters, no pending observations |
| Yellow | Quality at risk | Metrics out of range or unaddressed pending observations exist |
| Red | Critical quality | Metrics well below standard or accumulation of ignored observations |

### Transitions

- **→ Green**: initial status when QA begins supervising a department.
- **Green → Yellow**: when the [[Operador de QA]] detects out-of-range metrics or issues unaddressed observations.
- **Yellow → Red**: when observations persist without attention or metrics deteriorate significantly.
- **Red → Yellow**: when the department begins addressing observations and shows improvement.
- **Yellow → Green**: when all observations are resolved and metrics return to parameters.

### Who Updates the Indicator

| Action | Responsible |
|---|---|
| Propose status change based on measurements | [[Operador de QA]] |
| Validate and approve the update | [[Manager de QA]] |

> [!important] Only the [[Manager de QA]] can formally update the [[Indicador de Calidad]] of each department.

## Escalation

- Department in **Red** status without improvement after notification → the [[Manager de QA]] escalates the case to management.
- The [[Manager de QA]] presents quality reports to management with findings, trends, and areas for improvement.

## Responsibility Summary by Role

| Action | [[Operador de QA]] | [[Manager de QA]] |
|---|---|---|
| Monitor status indicators of the assigned department | Yes | No |
| Measure performance metrics | Yes | No |
| Issue formal observations | Yes | No |
| Feed Quality Indicator data | Yes | No |
| Define metrics and KPIs | No | Yes |
| Validate and approve Indicator changes | No | Yes |
| Consolidate findings from all operators | No | Yes |
| Present reports to management | No | Yes |
| Escalate department in Red without improvement | No | Yes |
| Supervise QA operators | No | Yes |

## Related

- [[Reglas de Negocio]]
- [[Manager de QA]]
- [[Operador de QA]]
- [[Core/Módulos/Semáforos/Indicador de Calidad|Quality Indicator]]
- [[Semáforo del Colaborador]]
- [[Semáforo de Requisición]]
- [[Semáforo Onboarding]]
- [[Semáforo de Urgencia de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
