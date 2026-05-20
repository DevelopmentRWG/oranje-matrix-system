---
tags:
  - module/associate
aliases:
  - Associate
---

# Associate

Central entity of the Oranje system. Represents the person who is recruited, assigned, and operationally managed at hotels. Their record lives in the [[Pool de Colaboradores]] and their lifecycle is reflected in the [[Semáforo del Colaborador]].

> [!info]
> The Associate is not just a static record: their status changes over time according to the [[Semáforo del Colaborador]], which defines what operational phase they are in at any given moment.

## Associate Data

Associate data is captured in three phases.

### Phase 1 — Initial Interview

Captured by the [[Reclutadora]] during the first contact:

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
| Position | [[Posiciones]] |
| English level | [[Niveles de Inglés]] |
| Experience level | — |
| Transportation type | — |
| Modality | [[Modalidades de Contratación]] |

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

The Associate's status is managed through the [[Semáforo del Colaborador]], which defines 12 possible states from their entry into the [[Pool de Colaboradores]] to their eventual departure or blocking in the [[Core/Módulos/Blacklist|Blacklist]].

## Roles That Interact with the Associate

- [[Reclutadora]] — recruits them, validates documents, and assigns them to a hotel.
- [[Manager de Reclutamiento]] — oversees the process and reviews Blacklist cases.
- [[Hotel/Manager de Área|Manager de Área]] — generates their QR access code, manages rest periods and reports.
- [[Inspector]] — verifies their arrival on Day 1, delivers uniform on Day 3+, investigates Red cases.

## Daily Operations

- Their weekly assignment is recorded in the [[Core/Módulos/Schedule|Schedule]].
- Their worked hours are recorded in the [[Timesheet]] via QR punches in entry/exit pairs: Clock In, Lunch Out, Lunch In, Break Out, Break In, Clock Out.

## Related

- [[Reglas del Colaborador]]
- [[Pool de Colaboradores]]
- [[Semáforo del Colaborador]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Timesheet]]
- [[Reclutamiento/Flujo de Reclutamiento|Flujo de Reclutamiento]]
- [[Core/Módulos/Requisicion/Requisición|Requisición]]
- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]]
