---
tags:
  - modulo/reclutamiento
aliases:
  - Recruitment Rules
---

# Recruitment Rules

Consolidation of all business rules that apply to the Recruitment area within the Oranje system. Cross-reference with [[Business Rules|Business Rules]] (general system summary).

## Continuous recruitment and Pool

> [!important] The recruitment flow is **continuous**: hiring is always ongoing, whether or not there are open requisitions.

- Requisitions without a match can accelerate or prioritize certain positions/zones, but they **are not a condition** to start the flow.
- Only collaborators who passed the filter and were approved by Recruitment enter the [[Collaborator Pool|Collaborator Pool]].
- The [[Recruiter|Recruiter]] must check the [[Core/Modules/Blacklist|Blacklist]] before recruiting a candidate.

## Collaborator capture and approval

The process of recruiting a collaborator consists of phases defined in the [[Recruitment/Recruitment Flow|Recruitment Flow]].

| Phase                       | Description                                                                                                     | Responsible     |
| --------------------------- | -------------------------------------------------------------------------------------------------------------- | --------------- |
| 1 — Initial interview       | Capture of full name, age, gender, address and phone                                                           | [[Recruiter\|Recruiter]] |
| 2 — App sign-up             | Collaborator completes SSN, ITIN, Position, English level, Experience level, Type of transport, Modality        | Collaborator    |
| 3 — Validation and approval | Recruitment reviews the data and approves or rejects the collaborator                                          | [[Recruiter\|Recruiter]] |
| 4 — Access enablement       | The collaborator's access to the panels is enabled                                                             | [[Recruiter\|Recruiter]] |

- An approved collaborator enters the [[Collaborator Pool|Collaborator Pool]] with the [[Collaborator Status Light|Collaborator Status Light]] in **Strong Green** (Available) state.

## Requisitions — intake and assignment (Self-Pick)

| Step | Action                                                                                                                                                                                                                                                                       | Responsible                                                              |
| ---- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| 1    | The requisition authorized by the [[Hotel/General Manager\|General Manager]] or the [[Hotel/Area Manager\|Area Manager]] becomes available in the shared inbox, prioritized by the [[Core/Modules/Status Lights/Requisition Urgency Status Light\|Urgency Status Light]] | System                                                                   |
| 2    | A [[Recruiter\|Recruiter]] or [[Recruitment/Recruiters Group Leader\|Group Leader]] takes the requisition from the inbox                                                                                                                                          | [[Recruiter\|Recruiter]] / [[Recruitment/Recruiters Group Leader\|Leader]] |
| 3    | The requisition moves to **Yellow** (In process) in the [[Core/Modules/Status Lights/Requisition Status Light\|Requisition Status Light]]                                                                                                                                         | System                                                                   |
| 4    | The [[Recruiter\|Recruiter]] checks the hotel's [[Core/Modules/Schedule\|Schedule]] to see pending positions                                                                                                                                                               | [[Recruiter\|Recruiter]]                                               |
| 5    | If there is a match → assigns the collaborator and registers them in the Schedule                                                                                                                                                                                            | [[Recruiter\|Recruiter]]                                               |
| 6    | If there is no match → the [[Recruiter\|Recruiter]] actively searches outside the system (social media, external groups, etc.)                                                                                                                                             | [[Recruiter\|Recruiter]]                                               |

> [!important] **Global inbox with filters** — all Recruiters see all available requisitions. They can filter by zone, urgency, position and other criteria. The inbox is not segmented by group or by Recruiter.

> [!important] **Collaborative model (RR-15)** — a requisition can have **several participating recruiters** working it at the same time; there is no single owner. Taking a requisition that is **already taken does NOT transfer or lock it**: the recruiter **joins** ("Join" action) as an additional participant, without displacing the existing ones or rolling back the status light. A recruiter can **leave** ("Leave" action) and only they are removed; the requisition stays **Yellow** if others remain and only returns to **Authorized** when the **last one** leaves. Progress is **shared** and the concurrency lock operates only at the **position/slot** level: if two assign the same position, the first wins and the second sees "position already covered". See [[Recruitment/Requisition Self-Pick|Requisition Self-Pick]].

> [!important] **Auto-assignment at 24 hours** — if a requisition has gone more than **24 hours** without being taken (counted from authorization), the system automatically assigns it to the [[Recruiter|Recruiter]] with the lowest load of active requisitions. The [[Recruitment Manager|Recruitment Manager]] receives no notification; the process is transparent.

> [!warning] **Escalation to the Group Leader on timeout without a match** — when the [[Recruiter|Recruiter]] fails to cover the requisition searching inside and outside the system, the following escalation deadline toward the [[Recruitment/Recruiters Group Leader\|Group Leader]] applies according to the [[Core/Modules/Status Lights/Requisition Urgency Status Light\|Urgency Status Light]]:
>
> | Urgency color | Condition | Deadline to escalate |
> |---|---|---|
> | Red | Less than 72h to start | 24h without covering |
> | Yellow | Between 72h and 120h to start | 48h without covering |
> | Strong Green | More than 120h to start | 72h without covering |
>
> Throughout this entire process the requisition remains in **Yellow** state in the [[Core/Modules/Status Lights/Requisition Status Light\|Requisition Status Light]].

> [!note] **Requisition history (RR-16)** — each action (take, join, leave, assign/unassign collaborator to a position, status change, closure) is recorded in an **immutable** chronological timeline with **actor** (role and name) and timestamp. It is visible to all participating recruiters, the [[Recruitment/Recruiters Group Leader\|Group Leader]] and the [[Recruitment Manager|Recruitment Manager]]. See RF-41 and [[Recruitment/Requisition Self-Pick\|Requisition Self-Pick]].

## Position coverage

When assigning collaborators from the [[Collaborator Pool|Collaborator Pool]] to the positions of a requisition, the [[Recruiter|Recruiter]] directly affects the [[Core/Modules/Status Lights/Requisition Positions Status Light|Requisition Positions Status Light]]:

| Color | State | Condition |
|---|---|---|
| Green | 100% covered | All collaborators assigned to the position are confirmed |
| Yellow | Up to 25% missing | Up to 25% of the required staff is missing |
| Red | More than 25% missing | More than 25% missing — requires priority attention |

> [!important] The result of the positions determines the final state of the requisition: if **all** reach Green → the requisition moves to **Light Blue** (fully covered). If at least one closes in Yellow or Red → the requisition moves to **Red** (partially covered).

## Temporary assignment (Brown)

- The [[Recruiter|Recruiter]] can temporarily assign an available collaborator (→ **Brown** in the [[Collaborator Status Light|Collaborator Status Light]]).
- At the end of the temporary shift, the collaborator returns to **Strong Green** or **Orange** according to their previous state.

## Blacklist

| Action | Role | Type |
|---|---|---|
| Check the [[Core/Modules/Blacklist\|Blacklist]] before recruiting | [[Recruiter\|Recruiter]] | Mandatory |
| Review Blacklist cases | [[Recruitment Manager\|Recruitment Manager]] | Supervision |

> [!note] No Recruitment role can send a collaborator to Blacklist directly. Entry into the Blacklist is automatic (3 absences) or executed by the [[Inspector|Inspector]] after a dispute resolved in favor of the hotel.

## Internal supervision

### Extended Lunch Indicator

- The [[Recruitment Manager|Recruitment Manager]] has visibility of the Extended Lunch Indicator in the [[Timesheet|Timesheet]].
- It is triggered when a collaborator's lunch time exceeds 30 minutes.
- It is **not visible** to the [[Hotel/General Manager|General Manager]], the [[Hotel/Area Manager|Area Manager]] or the [[Hotel/Supervisor|Supervisor]].
- Purpose: internal Oranje supervision; it is not automatically punitive.

### Supervision hierarchy

| Role | Supervises | Reports to |
|---|---|---|
| [[Recruitment Manager\|Recruitment Manager]] | [[Recruitment/Recruiters Group Leader\|Group Leaders]] | — |
| [[Recruitment/Recruiters Group Leader\|Recruiters Group Leader]] | [[Recruiter\|Recruiters]] in their group | [[Recruitment Manager\|Recruitment Manager]] |
| [[Recruiter\|Recruiter]] | — | [[Recruitment/Recruiters Group Leader\|Group Leader]] |

## Quality Supervision (QA)

- A [[QA/QA Operator|QA Operator]] is permanently assigned to the Recruitment department.
- QA does **not execute** the Recruitment operation; it only observes, measures and provides feedback.
- The specific metrics that the QA Operator monitors for Recruitment are defined in [[QA/Metrics and KPIs by Department#Reclutamiento|Metrics and KPIs — Recruitment]].
- If the department's [[Core/Modules/Status Lights/Quality Indicator|Quality Indicator]] reaches **Red** state without improvement after notification, the QA Manager escalates to management.

## Summary of responsibilities by role

| Action | [[Recruiter\|Recruiter]] | [[Recruitment/Recruiters Group Leader\|Group Leader]] | [[Recruitment Manager\|Recruitment Manager]] |
|---|---|---|---|
| Initial interview and data capture | Yes | Yes (inherits) | No |
| Validate and approve collaborator | Yes | Yes (inherits) | No |
| Enable access to panels | Yes | Yes (inherits) | No |
| Take requisitions from the inbox | Yes | Yes (inherits) | Only exceptions (balancing, absent leader, assignment error) |
| Join a requisition (already taken by another) | Yes | Yes (inherits) | Only exceptions |
| View requisition history | Yes (View) | Yes (View) | Yes (View) |
| Check Blacklist | Yes (mandatory) | Yes (inherits) | — |
| Review Blacklist cases | No | No | Yes |
| Temporary assignment (Brown) | Yes | Yes (inherits) | No |
| Manage position coverage | Yes | Yes (inherits) | No |
| View Extended Lunch Indicator | No | No | Yes |
| Supervise Recruiters | No | Yes | No (supervises Leaders) |

> [!info] The [[Recruitment/Recruiters Group Leader|Recruiters Group Leader]] executes **all** the operational responsibilities of a [[Recruiter|Recruiter]], in addition to their supervision functions.

## Related

- [[Business Rules|Business Rules]]
- [[Recruiter|Recruiter]]
- [[Recruitment/Recruiters Group Leader|Recruiters Group Leader]]
- [[Recruitment Manager|Recruitment Manager]]
- [[Recruitment/Recruitment Flow|Recruitment Flow]]
- [[Recruitment/Requisition Self-Pick|Requisition Self-Pick]]
- [[Core/Modules/Requisition/Requisition Flow|Requisition Flow]]
- [[Core/Modules/Requisition/Requisition|Requisition]]
- [[Collaborator Pool|Collaborator Pool]]
- [[Core/Modules/Blacklist|Blacklist]]
- [[Collaborator Status Light|Collaborator Status Light]]
- [[Core/Modules/Status Lights/Requisition Status Light|Requisition Status Light]]
- [[Core/Modules/Status Lights/Requisition Positions Status Light|Requisition Positions Status Light]]
- [[Core/Modules/Schedule|Schedule]]
- [[Timesheet|Timesheet]]
