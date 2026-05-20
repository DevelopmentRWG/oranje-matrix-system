---
tags:
  - module/recruitment
aliases:
  - Recruitment Business Rules
---

# Recruitment Business Rules

Consolidation of all business rules that apply to the Recruitment area within the Oranje system. Cross-reference with [[Reglas de Negocio]] (general system consolidation).

## Continuous Recruitment and Pool

> [!important] The recruitment flow is **continuous**: hiring is always ongoing, whether or not there are open requisitions.

- Unmatched requisitions may accelerate or prioritize certain positions/zones, but they are **not a condition** for starting the flow.
- Only associates who passed the filter and were approved by Recruitment enter the [[Pool de Colaboradores]].
- The [[Reclutadora]] must check the [[Core/Módulos/Blacklist|Blacklist]] before recruiting a candidate.

## Associate Capture and Approval

The associate recruitment process consists of phases defined in the [[Reclutamiento/Flujo de Reclutamiento|Flujo de Reclutamiento]].

| Phase | Description | Responsible |
|---|---|---|
| 1 — Initial interview | Capture of full name, age, gender, address, and phone | [[Reclutadora]] |
| 2 — App registration | Associate completes SSN, ITIN, Position, English level, Experience level, Transportation type, Modality | Associate |
| 3 — Validation and approval | Recruitment reviews the data and approves or rejects the associate | [[Reclutadora]] |
| 4 — Access enablement | Associate's access to the panels is enabled | [[Reclutadora]] |

- An approved associate enters the [[Pool de Colaboradores]] with [[Semáforo del Colaborador]] in **White** status.

## Requisitions — Reception and Assignment (Self-Pick)

| Step | Action | Responsible |
|---|---|---|
| 1 | The requisition authorized by the [[Hotel/Manager General\|Manager General]] or the [[Hotel/Manager de Área\|Manager de Área]] becomes available in the shared inbox, prioritized by the [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición\|Semáforo de Urgencia]] | System |
| 2 | A [[Reclutadora]] or [[Reclutamiento/Líder de Grupo de Reclutadoras\|Líder de Grupo]] takes the requisition from the inbox | [[Reclutadora]] / [[Reclutamiento/Líder de Grupo de Reclutadoras\|Líder]] |
| 3 | The requisition moves to **Yellow** (In progress) in the [[Core/Módulos/Semáforos/Semáforo de Requisición\|Semáforo de Requisición]] | System |
| 4 | The [[Reclutadora]] checks the hotel's [[Core/Módulos/Schedule\|Schedule]] to see pending positions | [[Reclutadora]] |
| 5 | If there is a match → assigns the associate and registers them in the Schedule | [[Reclutadora]] |
| 6 | If there is no match → the [[Reclutadora]] actively searches outside the system (social networks, external groups, etc.) | [[Reclutadora]] |

> [!important] **Global inbox with filters** — all Recruiters see all available requisitions. They can filter by zone, urgency, position, and other criteria. The inbox is not segmented by group or by Recruiter.

> [!important] **Concurrency: first to confirm wins** — if two Recruiters attempt to take the same requisition simultaneously, the system locks it for the first one to confirm. The second receives a message indicating the requisition has already been taken.

> [!important] **Auto-assignment at 24 hours** — if a requisition has been untaken for more than **24 hours** (counted from authorization), the system automatically assigns it to the [[Reclutadora]] with the lowest active requisition load. The [[Manager de Reclutamiento]] does not receive a notification; the process is transparent.

> [!warning] **Escalation to Team Lead on timeout without match** — when the [[Reclutadora]] cannot cover the requisition by searching inside and outside the system, the following escalation timeout to the [[Reclutamiento/Líder de Grupo de Reclutadoras\|Líder de Grupo]] applies based on the [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición\|Semáforo de Urgencia]]:
>
> | Urgency color | Condition | Time to escalate |
> |---|---|---|
> | Red | Less than 72h until start | 24h without coverage |
> | Yellow | Between 72h and 120h until start | 48h without coverage |
> | Dark Green | More than 120h until start | 72h without coverage |
>
> Throughout this entire process the requisition remains in **Yellow** status in the [[Core/Módulos/Semáforos/Semáforo de Requisición\|Semáforo de Requisición]].

## Position Coverage

When assigning associates from the [[Pool de Colaboradores]] to the positions of a requisition, the [[Reclutadora]] directly affects the [[Core/Módulos/Semáforos/Semáforo de Posiciones de la Requisición|Semáforo de Posiciones de la Requisición]]:

| Color | Status | Condition |
|---|---|---|
| Green | 100% covered | All associates assigned to the position are confirmed |
| Yellow | Up to 25% missing | Up to 25% of required staff is missing |
| Red | More than 25% missing | More than 25% missing — requires priority attention |

> [!important] The position results determine the final status of the requisition: if **all** reach Green → the requisition moves to **Light Blue** (fully covered). If at least one closes at Yellow or Red → the requisition moves to **Red** (partially covered).

## Temporary Assignment (Brown)

- The [[Reclutadora]] can temporarily assign an available associate (→ **Brown** in the [[Semáforo del Colaborador]]).
- At the end of the temporary shift, the associate returns to **Dark Green** or **Orange** based on their previous state.

## Blacklist

| Action | Role | Type |
|---|---|---|
| Check the [[Core/Módulos/Blacklist\|Blacklist]] before recruiting | [[Reclutadora]] | Mandatory |
| Review Blacklist cases | [[Manager de Reclutamiento]] | Oversight |

> [!note] No Recruitment role can send an associate to the Blacklist directly. Entry to Blacklist is automatic (3 absences) or executed by the [[Inspector]] after a dispute resolved in the hotel's favor.

## Internal Supervision

### Extended Lunch Indicator

- The [[Manager de Reclutamiento]] has visibility of the Extended Lunch Indicator in the [[Timesheet]].
- It activates when an associate's lunch time exceeds 30 minutes.
- **Not visible** to the [[Hotel/Manager General|Manager General]], the [[Hotel/Manager de Área|Manager de Área]], or the [[Hotel/Supervisor|Supervisor]].
- Purpose: internal Oranje oversight; not automatically punitive.

### Supervision Hierarchy

| Role | Supervises | Reports to |
|---|---|---|
| [[Manager de Reclutamiento]] | [[Reclutamiento/Líder de Grupo de Reclutadoras\|Team Leads]] | — |
| [[Reclutamiento/Líder de Grupo de Reclutadoras\|Recruiter Team Lead]] | [[Reclutadora\|Recruiters]] in their group | [[Manager de Reclutamiento]] |
| [[Reclutadora]] | — | [[Reclutamiento/Líder de Grupo de Reclutadoras\|Team Lead]] |

## Quality Supervision (QA)

- A [[QA/Operador de QA|Operador de QA]] is permanently assigned to the Recruitment department.
- QA **does not execute** Recruitment operations; it only observes, measures, and provides feedback.
- The specific metrics that the QA Operator monitors for Recruitment are defined in [[QA/Métricas y KPIs por Departamento#Reclutamiento|Métricas y KPIs — Reclutamiento]].
- If the [[Core/Módulos/Semáforos/Indicador de Calidad|Indicador de Calidad]] for the department reaches **Red** status without improvement after notification, the QA Manager escalates to management.

## Responsibility Summary by Role

| Action | [[Reclutadora]] | [[Reclutamiento/Líder de Grupo de Reclutadoras\|Team Lead]] | [[Manager de Reclutamiento]] |
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

> [!info] The [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo de Reclutadoras]] executes **all** operational responsibilities of a [[Reclutadora]], in addition to their supervisory functions.

## Related

- [[Reglas de Negocio]]
- [[Reclutadora]]
- [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo de Reclutadoras]]
- [[Manager de Reclutamiento]]
- [[Reclutamiento/Flujo de Reclutamiento|Flujo de Reclutamiento]]
- [[Core/Módulos/Requisicion/Flujo de Requisición|Flujo de Requisición]]
- [[Pool de Colaboradores]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Semáforo del Colaborador]]
- [[Core/Módulos/Semáforos/Semáforo de Requisición|Semáforo de Requisición]]
- [[Core/Módulos/Semáforos/Semáforo de Posiciones de la Requisición|Semáforo de Posiciones de la Requisición]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Timesheet]]
