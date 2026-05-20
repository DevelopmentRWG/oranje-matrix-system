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

Indicator that reflects the operational quality level of each department, fed by the assigned [[QA Operator]] and supervised by the [[QA Manager]]. Each department has its own independent indicator.

> [!info]
> This indicator does not replace the existing Status Indicators ([[Associate Status Indicator]], [[Requisition Status Indicator]], etc.). QA **consults** those Status Indicators as a data source and issues its evaluation in this indicator.

## States

| Color  | State            | Description                                                                                              |
| ------ | ---------------- | -------------------------------------------------------------------------------------------------------- |
| Green  | Optimal quality  | Metrics within expected parameters, no pending observations.                                             |
| Yellow | Quality at risk  | Metrics out of range or pending observations unaddressed by the department.                              |
| Red    | Critical quality | Metrics well below standard or accumulation of observations ignored by the department.                   |

## Business Rules

### Transitions

- **→ Green**: initial state when QA begins supervising a department, or when the department addresses all observations and its metrics return to parameters.
- **Green → Yellow**: when the [[QA Operator]] detects out-of-range metrics or issues observations that the department has not addressed.
- **Yellow → Red**: when observations persist without attention or metrics deteriorate significantly.
- **Red → Yellow**: when the department begins addressing observations and shows improvement in metrics.
- **Yellow → Green**: when all observations are resolved and metrics return to parameters.

### Who updates the indicator

- The [[QA Operator]] proposes the state change based on their measurements.
- The [[QA Manager]] validates and approves the change.

> [!important]
> A department in **Red** state requires immediate attention. The [[QA Manager]] escalates the case to management if there is no improvement after notification.

### Quantitative thresholds

The specific thresholds that define when a KPI is at Target, At risk or Critical level — and how that translates into transitions of this indicator — are documented in [[QA/Metrics and KPIs by Department|Metrics and KPIs by Department]].

## Related

- [[QA/QA|QA]]
- [[QA Manager]]
- [[QA Operator]]
- [[Associate Status Indicator]]
- [[Requisition Status Indicator]]
- [[Onboarding Status Indicator]]
- [[Requisition Urgency Indicator]]
- [[Requisition Position Status Indicator]]
