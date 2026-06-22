---
tags:
  - modulo/core
  - departamento/qa
aliases:
  - Quality Indicator
  - Quality Green
  - Quality Yellow
  - Quality Red
---

# Quality Indicator

Indicator that reflects the level of operational quality of each department, fed by the assigned [[QA Operator|QA Operator]] and supervised by the [[QA Manager|QA Manager]]. Each department has its own independent indicator.

> [!info]
> This indicator does not replace the existing status lights ([[Collaborator Status Light|Collaborator Status Light]], [[Requisition Status Light|Requisition Status Light]], etc.). QA **consults** those status lights as a data source and issues its evaluation in this indicator.

## States

| Color  | State              | Description                                                                                       |
| ------ | ------------------ | ------------------------------------------------------------------------------------------------- |
| Green  | Optimal quality    | Metrics within expected parameters, no pending observations.                                      |
| Yellow | Quality at risk    | Metrics out of range or pending observations not addressed by the department.                     |
| Red    | Critical quality   | Metrics well below standard or accumulation of observations ignored by the department.            |

## Key rules

### Transitions

- **→ Green**: initial state when QA starts supervising a department, or when the department addresses all observations and its metrics return to parameters.
- **Green → Yellow**: when the [[QA Operator|QA Operator]] detects metrics out of range or issues observations that the department has not addressed.
- **Yellow → Red**: when observations persist unaddressed or metrics deteriorate significantly.
- **Red → Yellow**: when the department begins to address observations and shows improvement in metrics.
- **Yellow → Green**: when all observations are resolved and metrics return to parameters.

### Who updates the indicator

- The [[QA Operator|QA Operator]] proposes the state change based on their measurements.
- The [[QA Manager|QA Manager]] validates and approves the change.

> [!important]
> A department in **Red** state requires immediate attention. The [[QA Manager|QA Manager]] escalates the case to management if there is no improvement after notification.

### Quantitative thresholds

The specific thresholds that define when a KPI is On Target, At Risk or Critical level — and how that translates into transitions of this indicator — are documented in [[QA/Metrics and KPIs by Department|Metrics and KPIs by Department]].

## Related

- [[QA/QA|QA]]
- [[QA Manager|QA Manager]]
- [[QA Operator|QA Operator]]
- [[Collaborator Status Light|Collaborator Status Light]]
- [[Requisition Status Light|Requisition Status Light]]
- [[Onboarding Status Light|Onboarding Status Light]]
- [[Requisition Urgency Status Light|Requisition Urgency Status Light]]
- [[Requisition Positions Status Light|Requisition Positions Status Light]]
