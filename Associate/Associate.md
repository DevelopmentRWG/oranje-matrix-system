---
tags:
  - module/associate
aliases:
  - Associate
---

# Associate

Central entity of the Oranje system. Represents the person who is recruited, assigned, and operationally managed at hotels. Their record lives in the [[Associate Pool]] and their lifecycle is reflected in the [[Associate Status Indicator]].

> [!info]
> The Associate is not just a static record: their status changes over time according to the [[Associate Status Indicator]], which defines what operational phase they are in at any given moment.

## Associate Data

Associate data is captured in three phases.

### Phase 1 — Initial Interview

Captured by the [[Recruiter]] during the first contact:

| Field | Captured by |
|---|---|
| Full name | Recruiter |
| Age | Recruiter |
| Gender | Recruiter |
| Address | Recruiter |
| Phone | Recruiter |

### Phase 2 — App Registration

Completed by the Associate themselves:

| Field | Associated catalog |
|---|---|
| SSN | — |
| ITIN | — |
| Position | [[Positions]] |
| English level | [[English Levels]] |
| Experience level | — |
| Transportation type | — |
| Modality | [[Employment Modalities]] |

### Phase 3 — Emergency Data

Completed by the Associate themselves from the app:

| Field | Description |
|---|---|
| Emergency contact — name | Person to contact in case of emergency |
| Emergency contact — phone | Contact's phone number |
| Emergency contact — relationship | Relationship with the associate |
| Blood type | Blood group |
| Allergies or medical conditions | Relevant medical information |

## Lifecycle

The Associate's status is managed through the [[Associate Status Indicator]], which defines 12 possible states from their entry into the [[Associate Pool]] to their eventual departure or blocking in the [[Core/Modules/Blacklist|Blacklist]].

## Roles That Interact with the Associate

- [[Recruiter]] — recruits them, validates documents, and assigns them to a hotel.
- [[Recruitment Manager]] — oversees the process and reviews Blacklist cases.
- [[Hotel/Area Manager|Area Manager]] — generates their QR access code, manages rest periods and reports.
- [[Inspector]] — verifies their arrival on Day 1, delivers uniform on Day 3+, investigates Red cases.

## Daily Operations

- Their weekly assignment is recorded in the [[Core/Modules/Schedule|Schedule]].
- Their worked hours are recorded in the [[Timesheet]] via QR punches in entry/exit pairs: Clock In, Lunch Out, Lunch In, Break Out, Break In, Clock Out.

## Related

- [[Associate Rules]]
- [[Associate Pool]]
- [[Associate Status Indicator]]
- [[Core/Modules/Blacklist|Blacklist]]
- [[Core/Modules/Schedule|Schedule]]
- [[Timesheet]]
- [[Recruitment/Recruitment Flow|Recruitment Flow]]
- [[Core/Modules/Requisition/Requisition|Requisition]]
- [[Core/Modules/Work Accident/Work Accident|Work Accident]]
