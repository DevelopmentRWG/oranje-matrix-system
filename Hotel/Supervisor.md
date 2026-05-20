---
tags:
  - module/hotel
aliases:
  - SUP
  - Supervisor
---

# Supervisor

Operational role in the [[Hotel/Hotel|Hotel]] module, subordinate to the [[Hotel/Area Manager|Area Manager]]. Responsible for creating the staff [[Requisition|requisitions]] that the hotel needs to fill.

> [!note] Extended Hierarchy
> In hotels with an extended hierarchy, this role corresponds to the [[Hotel Departments|department]] Supervisor, subordinate to the [[Hotel/Area Manager|Area Manager]] of their department. The platform responsibilities are the same.

## Responsibilities

### Requisitions

- Creates the [[Requisition]] from the app, specifying:
  - Required [[Positions|positions]].
  - Number of people per position.
  - Start date.
  - Schedule.
  - [[Employment Types|Employment modality]].
  - [[English Levels|English level]] preference.
  - Additional notes.
- Sends the requisition to the [[Hotel/Area Manager|Area Manager]] for approval.

> [!note] On Authorization
> The Supervisor **cannot authorize** a requisition. All requisitions must be reviewed and approved by the [[Hotel/Area Manager|Area Manager]] or the [[Hotel/General Manager|General Manager]] before reaching the [[Recruitment/Recruitment|Recruitment]] team.

### Assigned Staff Management

- Places associates on rest (status **Pink — Stand-by** in the [[Associate Status Indicator]]).
- Reports associates (status **Red — Reported** in the [[Associate Status Indicator]]).
- Reports [[Core/Modules/Work Accident/Work Accident|workplace accidents]] detected on the property (see [[Core/Modules/Work Accident/Work Accident Flow|Work Accident Flow]]).
- Physically goes to the incident location and captures on-site information on the accident card: exact location, circumstances, witnesses, and immediate care provided.

## Related

- [[Hotel/Area Manager|Area Manager]]
- [[Hotel/General Manager|General Manager]]
- [[Hotel/Hotel|Hotel]]
- [[Hotel Departments]]
- [[Requisition]]
- [[Requisition Status Indicator]]
- [[Associate Status Indicator]]
- [[Core/Modules/Work Accident/Work Accident|Work Accident]]
- [[Core/Modules/Work Accident/Work Accident Flow|Work Accident Flow]]
