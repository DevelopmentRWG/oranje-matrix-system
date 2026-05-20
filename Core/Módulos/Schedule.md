---
tags:
  - module/core
aliases:
  - Schedule
---

# Schedule

The hotel's weekly planning board. It is the **central axis of operations**: it brings together personnel demand ([[Requisition]]), coverage (associate assignment from the [[Associate Pool]]), and time tracking ([[Timesheet]]). Each hotel week has its own schedule.

## Initial Setup

- The hotel defines its **week start and end** in the [[Contract]].
- Oranje provides a **weekly planning format** based on that configuration.

## What the Schedule Contains

### Requisition (what the hotel needs)

- When a [[Requisition]] is created with a start date within the week, its positions are reflected in that week's schedule.
- The schedule shows the requested positions: role, headcount, schedule, dates, and language.

### Assignments (who covers the positions)

- The [[Recruiter]] checks the hotel's schedule to see the full picture: which positions were requested and which are already covered.
- When assigning an associate from the [[Associate Pool]], they are registered in the hotel's schedule.

### Timesheet (actual hours record)

- Each associate enrolled in the schedule has their own [[Timesheet]].
- The schedule is the basis for generating the timesheet and enabling punch-in/out by entry/exit pairs (Clock In, Lunch Out, Lunch In, Break Out, Break In, Clock Out).
- If the schedule is modified after the timesheet was created, the [[Timesheet]] is automatically updated to reflect the changes.

## Who Manages It

- **[[Hotel/Area Manager|Area Manager]]** — Manages the weekly schedule: distributes and plans their staff.
- **[[Recruiter]]** — Checks the schedule to see demand and registers associates when assigning them.

## What It Enables

- Unified view of the hotel's operational week (demand + coverage + records).
- Creation of the [[Timesheet]] per associate.
- Visibility for the hotel of what was requested vs. what is covered.

## Holidays

- Holidays are recorded in the system as operational data.
- Their purpose is to analyze operational behavior on special dates and feed the forecast module.

> [!info] The forecast module is pending definition. Holidays are recorded in the system as input for that module when it is implemented.

## Related

- [[Requisition]]
- [[Timesheet]]
- [[Recruiter]]
- [[Associate Pool]]
- [[Hotel/Area Manager|Area Manager]]
- [[Requisition Flow]]
