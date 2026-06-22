---
tags:
  - departamento/qa
aliases:
  - QA Rules
  - Reglas de QA
---

# QA Rules

Consolidation of all the business rules that apply to the QA department within the Oranje system. Cross-reference with [[Business Rules|Business Rules]] (general system summary).

## Fundamental principle

> [!important] QA does not execute the operation of any department. Its function is to **observe, measure and provide feedback** so that each area keeps its quality within the defined standards.

## Department hierarchy

| Role | Function |
|---|---|
| [[QA Manager|QA Manager]] | Defines metrics and KPIs, supervises operators, consolidates findings, updates the [[Quality Indicator|Quality Indicator]] and presents reports to management |
| [[QA Operator|QA Operator]] | Operational executor. Monitors status lights, measures metrics, issues formal observations to the assigned department |

## Operator assignment

There are **6 QA Operators**, each permanently assigned to a department:

| Operator | Supervised department |
|---|---|
| Operator 1 | [[Inspection/Inspector\|Inspection]] |
| Operator 2 | [[Hotel/Hotel\|Hotel]] |
| Operator 3 | [[Collaborator/Collaborator\|Collaborator]] |
| Operator 4 | [[Sales/Sales\|Sales]] |
| Operator 5 | [[Recruitment/Recruitment\|Recruitment]] |
| Operator 6 | [[Customer Service/Customer Service\|Customer Service]] |

> [!note] The assignment is fixed: each operator thoroughly knows the operation of the department they supervise.

> [!note] Scope of this document
> The specific metrics and KPIs by department are defined in [[QA/Metrics and KPIs by Department|Metrics and KPIs by Department]]. This document covers the general structure of the QA module: roles, observation flow and escalation.

## Metrics and observations

- The [[QA Operator|QA Operator]] monitors the status lights of the assigned department ([[Collaborator Status Light|Collaborator Status Light]], [[Requisition Status Light|Requisition Status Light]], [[Onboarding Status Light|Onboarding Status Light]], etc.) as a source of operational context.
- Measures performance metrics: response times, success rates, error frequency and process compliance.
- Issues **formal observations** to the department with specific findings and improvement recommendations.
- Reports to the [[QA Manager|QA Manager]] with the collected data and the quality state.
- The specific metrics that each operator monitors are defined in [[QA/Metrics and KPIs by Department|Metrics and KPIs by Department]].

## Quality Indicator

The [[Core/Modules/Status Lights/Quality Indicator|Quality Indicator]] is QA's own measurement instrument. Each department has its own independent indicator; the initial state is **Green**.

| Color | State | Description |
|---|---|---|
| Green | Optimal quality | Metrics within expected parameters, no pending observations |
| Yellow | Quality at risk | Metrics out of range or there are pending observations not yet addressed |
| Red | Critical quality | Metrics well below standard or accumulation of ignored observations |

### Transitions

- **→ Green**: initial state when QA begins to supervise a department.
- **Green → Yellow**: when the [[QA Operator|QA Operator]] detects metrics out of range or issues unaddressed observations.
- **Yellow → Red**: when observations persist without attention or metrics deteriorate significantly.
- **Red → Yellow**: when the department begins to address observations and shows improvement.
- **Yellow → Green**: when all observations are resolved and metrics return to parameters.

### Who updates the indicator

| Action | Responsible |
|---|---|
| Propose state change based on measurements | [[QA Operator|QA Operator]] |
| Validate and approve the update | [[QA Manager|QA Manager]] |

> [!important] Only the [[QA Manager|QA Manager]] can formally update the [[Quality Indicator|Quality Indicator]] of each department.

## Escalation

- Department in **Red** state without improvement after notification → the [[QA Manager|QA Manager]] escalates the case to management.
- The [[QA Manager|QA Manager]] presents quality reports to management with findings, trends and areas for improvement.

## Summary of responsibilities by role

| Action | [[QA Operator|QA Operator]] | [[QA Manager|QA Manager]] |
|---|---|---|
| Monitor status lights of the assigned department | Yes | No |
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

- [[Business Rules|Business Rules]]
- [[QA Manager|QA Manager]]
- [[QA Operator|QA Operator]]
- [[Core/Modules/Status Lights/Quality Indicator|Quality Indicator]]
- [[Collaborator Status Light|Collaborator Status Light]]
- [[Requisition Status Light|Requisition Status Light]]
- [[Onboarding Status Light|Onboarding Status Light]]
- [[Requisition Urgency Status Light|Requisition Urgency Status Light]]
- [[Requisition Positions Status Light|Requisition Positions Status Light]]
