---
tags:
  - module/recruitment
aliases:
  - Recruitment Business Rules
---

# Recruitment Business Rules

Consolidation of all business rules that apply to the Recruitment area within the Oranje system. Cross-reference with [[Business Rules]] (general system consolidation).

## Continuous Recruitment and Pool

> [!important] The recruitment flow is **continuous**: hiring is always ongoing, whether or not there are open requisitions.

- Unmatched requisitions may accelerate or prioritize certain positions/zones, but they are **not a condition** for starting the flow.
- Only associates who passed the filter and were approved by Recruitment enter the [[Associate Pool]].
- The [[Recruiter]] must check the [[Core/Modules/Blacklist|Blacklist]] before recruiting a candidate.

## Associate Capture and Approval

The associate recruitment process consists of phases defined in the [[Recruitment/Recruitment Flow|Recruitment Flow]].

| Phase | Description | Responsible |
|---|---|---|
| 1 — Initial interview | Capture of full name, age, gender, address, and phone | [[Recruiter]] |
| 2 — App registration | Associate completes SSN, ITIN, Position, English level, Experience level, Transportation type, Modality | Associate |
| 3 — Validation and approval | Recruitment reviews the data and approves or rejects the associate | [[Recruiter]] |
| 4 — Access enablement | Associate's access to the panels is enabled | [[Recruiter]] |

- An approved associate enters the [[Associate Pool]] with [[Associate Status Indicator]] in **White** status.

## Requisitions — Reception and Assignment (Self-Pick)

| Step | Action | Responsible |
|---|---|---|
| 1 | The requisition authorized by the [[Hotel/General Manager\|General Manager]] or the [[Hotel/Area Manager\|Area Manager]] becomes available in the shared inbox, prioritized by the [[Core/Modules/Status Indicators/Requisition Urgency Indicator\|Requisition Urgency Indicator]] | System |
| 2 | A [[Recruiter]] or [[Recruitment/Recruiter Team Lead\|Team Lead]] takes the requisition from the inbox | [[Recruiter]] / [[Recruitment/Recruiter Team Lead\|Team Lead]] |
| 3 | The requisition moves to **Yellow** (In progress) in the [[Core/Modules/Status Indicators/Requisition Status Indicator\|Requisition Status Indicator]] | System |
| 4 | The [[Recruiter]] checks the hotel's [[Core/Modules/Schedule\|Schedule]] to see pending positions | [[Recruiter]] |
| 5 | If there is a match → assigns the associate and registers them in the Schedule | [[Recruiter]] |
| 6 | If there is no match → the [[Recruiter]] actively searches outside the system (social networks, external groups, etc.) | [[Recruiter]] |

> [!important] **Global inbox with filters** — all Recruiters see all available requisitions. They can filter by zone, urgency, position, and other criteria. The inbox is not segmented by group or by Recruiter.

> [!important] **Concurrency: first to confirm wins** — if two Recruiters attempt to take the same requisition simultaneously, the system locks it for the first one to confirm. The second receives a message indicating the requisition has already been taken.

> [!important] **Auto-assignment at 24 hours** — if a requisition has been untaken for more than **24 hours** (counted from authorization), the system automatically assigns it to the [[Recruiter]] with the lowest active requisition load. The [[Recruitment Manager]] does not receive a notification; the process is transparent.

> [!warning] **Escalation to Team Lead on timeout without match** — when the [[Recruiter]] cannot cover the requisition by searching inside and outside the system, the following escalation timeout to the [[Recruitment/Recruiter Team Lead\|Team Lead]] applies based on the [[Core/Modules/Status Indicators/Requisition Urgency Indicator\|Requisition Urgency Indicator]]:
>
> | Urgency color | Condition | Time to escalate |
> |---|---|---|
> | Red | Less than 72h until start | 24h without coverage |
> | Yellow | Between 72h and 120h until start | 48h without coverage |
> | Dark Green | More than 120h until start | 72h without coverage |
>
> Throughout this entire process the requisition remains in **Yellow** status in the [[Core/Modules/Status Indicators/Requisition Status Indicator\|Requisition Status Indicator]].

## Position Coverage

When assigning associates from the [[Associate Pool]] to the positions of a requisition, the [[Recruiter]] directly affects the [[Core/Modules/Status Indicators/Requisition Position Indicator|Requisition Position Status Indicator]]:

| Color | Status | Condition |
|---|---|---|
| Green | 100% covered | All associates assigned to the position are confirmed |
| Yellow | Up to 25% missing | Up to 25% of required staff is missing |
| Red | More than 25% missing | More than 25% missing — requires priority attention |

> [!important] The position results determine the final status of the requisition: if **all** reach Green → the requisition moves to **Light Blue** (fully covered). If at least one closes at Yellow or Red → the requisition moves to **Red** (partially covered).

## Temporary Assignment (Brown)

- The [[Recruiter]] can temporarily assign an available associate (→ **Brown** in the [[Associate Status Indicator]]).
- At the end of the temporary shift, the associate returns to **Dark Green** or **Orange** based on their previous state.

## Blacklist

| Action | Role | Type |
|---|---|---|
| Check the [[Core/Modules/Blacklist\|Blacklist]] before recruiting | [[Recruiter]] | Mandatory |
| Review Blacklist cases | [[Recruitment Manager]] | Oversight |

> [!note] No Recruitment role can send an associate to the Blacklist directly. Entry to Blacklist is automatic (3 absences) or executed by the [[Inspector]] after a dispute resolved in the hotel's favor.

## Internal Supervision

### Extended Lunch Indicator

- The [[Recruitment Manager]] has visibility of the Extended Lunch Indicator in the [[Timesheet]].
- It activates when an associate's lunch time exceeds 30 minutes.
- **Not visible** to the [[Hotel/General Manager|General Manager]], the [[Hotel/Area Manager|Area Manager]], or the [[Hotel/Supervisor|Supervisor]].
- Purpose: internal Oranje oversight; not automatically punitive.

### Supervision Hierarchy

| Role | Supervises | Reports to |
|---|---|---|
| [[Recruitment Manager]] | [[Recruitment/Recruiter Team Lead\|Team Leads]] | — |
| [[Recruitment/Recruiter Team Lead\|Recruiter Team Lead]] | [[Recruiter\|Recruiters]] in their group | [[Recruitment Manager]] |
| [[Recruiter]] | — | [[Recruitment/Recruiter Team Lead\|Team Lead]] |

## Quality Supervision (QA)

- A [[QA/QA Operator|QA Operator]] is permanently assigned to the Recruitment department.
- QA **does not execute** Recruitment operations; it only observes, measures, and provides feedback.
- The specific metrics that the QA Operator monitors for Recruitment are defined in [[QA/Metrics and KPIs by Department#Recruitment|Metrics and KPIs — Recruitment]].
- If the [[Core/Modules/Status Indicators/Quality Indicator|Quality Indicator]] for the department reaches **Red** status without improvement after notification, the QA Manager escalates to management.

## Responsibility Summary by Role

| Action | [[Recruiter]] | [[Recruitment/Recruiter Team Lead\|Team Lead]] | [[Recruitment Manager]] |
|---|---|---|---|
| Initial interview and data capture | Yes | Yes (inherited) | No |
| Validate and approve associate | Yes | Yes (inherited) | No |
| Enable panel access | Yes | Yes (inherited) | No |
| Take requisitions from the inbox | Yes | Yes (inherited) | Exceptions only (balancing, absent lead, assignment error) |
| Check Blacklist | Yes (mandatory) | Yes (inherited) | — |
| Review Blacklist cases | No | No | Yes |
| Temporary assignment (Brown) | Yes | Yes (inherited) | No |
| Manage position coverage | Yes | Yes (inherited) | No |
| View Extended Lunch Indicator | No | No | Yes |
| Supervise Recruiters | No | Yes | No (supervises Team Leads) |

> [!info] The [[Recruitment/Recruiter Team Lead|Recruiter Team Lead]] executes **all** operational responsibilities of a [[Recruiter]], in addition to their supervisory functions.

## Related

- [[Business Rules]]
- [[Recruiter]]
- [[Recruitment/Recruiter Team Lead|Recruiter Team Lead]]
- [[Recruitment Manager]]
- [[Recruitment/Recruitment Flow|Recruitment Flow]]
- [[Core/Modules/Requisition/Requisition Flow|Requisition Flow]]
- [[Associate Pool]]
- [[Core/Modules/Blacklist|Blacklist]]
- [[Associate Status Indicator]]
- [[Core/Modules/Status Indicators/Requisition Status Indicator|Requisition Status Indicator]]
- [[Core/Modules/Status Indicators/Requisition Position Indicator|Requisition Position Status Indicator]]
- [[Core/Modules/Schedule|Schedule]]
- [[Timesheet]]
