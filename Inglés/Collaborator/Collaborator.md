---
tags:
  - modulo/colaborador
aliases:
  - Collaborator
---

# Collaborator

Central entity of the Oranje system. Represents the person who is recruited, assigned and operationally managed in the hotels. Their record lives in the [[Collaborator Pool|Collaborator Pool]] and their life cycle is reflected in the [[Collaborator Status Light|Collaborator Status Light]].

> [!info]
> The Collaborator is not just a static record: their state changes over time according to the [[Collaborator Status Light|Collaborator Status Light]], which defines which operational phase they are in at each moment.

## Collaborator data

The collaborator's data is captured in three phases.

### Phase 1 — Initial interview

Captured by the [[Recruiter|Recruiter]] during the first contact:

| Field | Captured by |
|---|---|
| Full name | Recruiter |
| Age | Recruiter |
| Gender | Recruiter |
| Address | Recruiter |
| Phone | Recruiter |

### Phase 2 — App sign-up

Completed by the Collaborator themselves:

| Field | Associated catalog |
|---|---|
| SSN | — |
| ITIN | — |
| Position | [[Posiciones|Positions]] |
| English level | [[English Levels|English Levels]] |
| Experience level | — |
| Type of transport | — |
| Modality | [[Employment Types|Hiring Modalities]] |

### Phase 3 — Emergency data

Completed by the Collaborator themselves from the app:

| Field | Description |
|---|---|
| Emergency contact — name | Person to contact in case of emergency |
| Emergency contact — phone | Contact's phone |
| Emergency contact — relationship | Relationship to the collaborator |
| Blood type | Blood group |
| Allergies or medical conditions | Relevant medical information |

## Life cycle

The Collaborator's state is managed through the [[Collaborator Status Light|Collaborator Status Light]], which defines 12 possible states from their entry into the [[Collaborator Pool|Collaborator Pool]] until their eventual exit or block in the [[Core/Modules/Blacklist|Blacklist]].

## Roles that interact with the Collaborator

- [[Recruiter|Recruiter]] — recruits them, validates documents and assigns them to a hotel.
- [[Recruitment Manager|Recruitment Manager]] — supervises the process and reviews Blacklist cases.
- [[Hotel/Area Manager|Area Manager]] — generates their access QR, manages breaks and reports.
- [[Inspector|Inspector]] — verifies their arrival on Day 1, delivers uniform on Day 3+, investigates Red cases.

## Daily operation

- Their weekly assignment is recorded in the [[Core/Modules/Schedule|Schedule]].
- Their hours worked are recorded in the [[Timesheet|Timesheet]] through QR punches in pairs of clock-in/clock-out: Clock-in, Lunch Out, Lunch In, Break Out, Break In, Clock-out.

## Related

- [[Collaborator Rules|Collaborator Rules]]
- [[Collaborator Pool|Collaborator Pool]]
- [[Collaborator Status Light|Collaborator Status Light]]
- [[Core/Modules/Blacklist|Blacklist]]
- [[Core/Modules/Schedule|Schedule]]
- [[Timesheet|Timesheet]]
- [[Recruitment/Recruitment Flow|Recruitment Flow]]
- [[Core/Modules/Requisition/Requisition|Requisition]]
- [[Core/Modules/Workplace Accident/Workplace Accident|Work Accident]]
