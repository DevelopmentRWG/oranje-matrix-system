---
tags:
  - module/core
  - department/qa
aliases:
  - Quality Indicator
  - Quality Green
  - Quality Yellow
  - Quality Red
---

# Quality Indicator

Indicator that reflects the operational quality level of each department, fed by the assigned [[Operador de QA]] and supervised by the [[Manager de QA]]. Each department has its own independent indicator.

> [!info]
> This indicator does not replace the existing Status Indicators ([[Semáforo del Colaborador]], [[Semáforo de Requisición]], etc.). QA **consults** those Status Indicators as a data source and issues its evaluation in this indicator.

## States

| Color  | State            | Description                                                                                              |
| ------ | ---------------- | -------------------------------------------------------------------------------------------------------- |
| Green  | Optimal quality  | Metrics within expected parameters, no pending observations.                                             |
| Yellow | Quality at risk  | Metrics out of range or pending observations unaddressed by the department.                              |
| Red    | Critical quality | Metrics well below standard or accumulation of observations ignored by the department.                   |

## Business Rules

### Transitions

- **→ Green**: initial state when QA begins supervising a department, or when the department addresses all observations and its metrics return to parameters.
- **Green → Yellow**: when the [[Operador de QA]] detects out-of-range metrics or issues observations that the department has not addressed.
- **Yellow → Red**: when observations persist without attention or metrics deteriorate significantly.
- **Red → Yellow**: when the department begins addressing observations and shows improvement in metrics.
- **Yellow → Green**: when all observations are resolved and metrics return to parameters.

### Who updates the indicator

- The [[Operador de QA]] proposes the state change based on their measurements.
- The [[Manager de QA]] validates and approves the change.

> [!important]
> A department in **Red** state requires immediate attention. The [[Manager de QA]] escalates the case to management if there is no improvement after notification.

### Quantitative thresholds

The specific thresholds that define when a KPI is at Target, At risk or Critical level — and how that translates into transitions of this indicator — are documented in [[QA/Métricas y KPIs por Departamento|Métricas y KPIs por Departamento]].

## Related

- [[QA/QA|QA]]
- [[Manager de QA]]
- [[Operador de QA]]
- [[Semáforo del Colaborador]]
- [[Semáforo de Requisición]]
- [[Semáforo Onboarding]]
- [[Semáforo de Urgencia de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
