---
tags:
  - modulo/core
aliases:
  - Schedule
---

# Schedule

Weekly planning board of the hotel. It is the **central axis of the operation**: in it converge the staff demand ([[Requisition|Requisition]]), the coverage (assignment of collaborators from the [[Collaborator Pool|Collaborator Pool]]) and the record of worked time ([[Timesheet]]). Each week of the hotel has its own schedule.

## Initial configuration

- The hotel defines the **start and end of its week** in the [[Contrato|Contract]].
- Oranje offers a **weekly planning format** based on that configuration.

## What the schedule contains

### Requisition (what the hotel needs)

- When a [[Requisition|Requisition]] is created with a start date within the week, its positions are reflected in that week's schedule.
- The schedule shows the requested positions: job, number of people, schedule, dates and language.

### Assignments (who covers the positions)

- The [[Recruiter|Recruiter]] consults the hotel's schedule to see the full picture: which positions were requested and which are already covered.
- Upon assigning a collaborator from the [[Collaborator Pool|Collaborator Pool]], they are registered in the hotel's schedule.

### Timesheet (actual record of hours)

- Each collaborator enrolled in the schedule has their own [[Timesheet]].
- The schedule is the base on which the timesheet is generated and the clock-in by entry/exit pairs is enabled (Clock In, Lunch Out, Lunch In, Break Out, Break In, Clock Out).
- If the schedule is modified after the timesheet was created, the [[Timesheet]] is automatically updated to reflect the changes.

## Who manages it

- **[[Hotel/Area Manager|Area Manager]]** — Manages the weekly schedule: distributes and plans their staff.
- **[[Recruiter|Recruiter]]** — Consults the schedule to see the demand and registers collaborators upon assigning them.

## What it enables

- Unified view of the hotel's operational week (demand + coverage + record).
- Creation of the [[Timesheet]] per collaborator.
- Visibility for the hotel of what it requested vs. what it has covered.

## Holidays

- Holidays are recorded in the system as operational data.
- Their purpose is the analysis of operational behavior on special dates and feeding the forecast module.

> [!info] The forecast module is pending definition. Holidays are recorded in the system as input for that module when it is implemented.

## Related

- [[Requisition|Requisition]]
- [[Timesheet]]
- [[Recruiter|Recruiter]]
- [[Collaborator Pool|Collaborator Pool]]
- [[Hotel/Area Manager|Area Manager]]
- [[Requisition Flow|Requisition Flow]]
