---
tags:
  - modulo/colaborador
aliases:
  - Collaborator Rules
---

# Collaborator Rules

Consolidation of all business rules that apply to the Collaborator within the Oranje system. Cross-reference with [[Business Rules|Business Rules]] (general system summary).

## Data capture in 3 phases

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

## Status Light and transitions

The [[Collaborator Status Light|Collaborator Status Light]] defines 12 states. The transition rules that govern the collaborator's life cycle are documented below.

### Standard progression

| Transition | Condition | Responsible |
|---|---|---|
| → White | When the collaborator completes their data in the app (Phase 2 + Phase 3); pending validation by the Recruiter. No access enabled. | System |
| White → Strong Green | When the Recruiter approves the validation (RF-08). Collaborator enabled in the Pool, access propagated. | Recruiter |
| Strong Green → Apple Green | Upon being assigned to a position and attending Day 1 | [[Inspector\|Inspector]] (verifies on site) |
| Apple Green → Light Blue | Upon punching in at the property on the third day | System + [[Inspector\|Inspector]] (delivers uniform) |
| Light Blue → Orange | Upon completing 7 days | System (automatic) |
| Orange → Strong Green | Upon becoming free (end of fixed assignment or reincorporated) | System |

### Availability and assignments

- **Yellow (Voluntary available):** activated by the collaborator themselves **from the app, without anyone's approval**. It is self-service and the **only state the collaborator can activate on their own**.
- **Brown (Temporary assignment):** the [[Recruiter|Recruiter]] or the [[Recruitment/Recruiters Group Leader|Group Leader]] temporarily assigns the collaborator and defines the duration (assigned days) at the moment of assignment. The state closes automatically when those days expire; upon closing, it returns to Strong Green or Yellow according to its previous state. The Recruiter or the Group Leader can also manually cancel the temporary assignment before its expiration; upon canceling, the collaborator immediately returns to their previous state (Strong Green or Yellow) and is released from the hotel's Schedule.

### Stand-by (Pink)

- The [[Hotel/General Manager|General Manager]], the [[Hotel/Area Manager|Area Manager]] or the [[Hotel/Supervisor|Supervisor]] can put a collaborator in Pink.
- It indicates waiting on a hotel decision (vacation, low season).
- The position has no end date; it ends when the [[Hotel/General Manager|General Manager]], the [[Hotel/Area Manager|Area Manager]] or the [[Hotel/Supervisor|Supervisor]] removes the collaborator from the Pink state. Upon leaving, it returns to Strong Green.

## Incidence rules

### Absence (Purple)

- The system marks Purple when the collaborator does not attend without justification.
- Each absence is recorded individually.

### 3-absence rule

- 3 accumulated absences → automatic [[Core/Modules/Blacklist|Blacklist]] (Black state).
- Responsible: System (no manual action required).

### Hotel report (Red)

- The [[Hotel/General Manager|General Manager]], [[Hotel/Area Manager|Area Manager]] or [[Hotel/Supervisor|Supervisor]] activates the Red state (reported).
- The [[Inspector|Inspector]] investigates the case and resolves toward:
  - **Black** ([[Core/Modules/Blacklist|Blacklist]]), if the dispute is in favor of the hotel.
  - **Strong Green** (reincorporated), if the dispute is in favor of the collaborator.
- The [[Recruitment Manager|Recruitment Manager]] has visibility of Blacklist cases as subsequent supervision, but the decision is made by the [[Inspector|Inspector]].

## Work Accident protection (Gray)

- Any active state → **Gray** when a [[Core/Modules/Workplace Accident/Workplace Accident|Work Accident]] report is generated.
- While the collaborator is in Gray, absences **do not count** toward the 3-absence → Black rule.
- **Gray → Strong Green** requires: medical discharge + closure of the accident card by the [[Inspector|Inspector]].
- Reference: [[Core/Modules/Workplace Accident/Workplace Accident Flow|Work Accident Flow]].

## Punching and Timesheet

> [!info] The punching and Lunch deduction rules are also documented in [[Hotel/Hotel Rules|Hotel Rules]] from the hotel's perspective.

### Punching mechanism

- The collaborator punches via **QR** generated by the [[Hotel/General Manager|General Manager]] or the [[Hotel/Area Manager|Area Manager]].
- Punches are recorded in clock-in/clock-out pairs for each period (exactly six):
  - **Clock-in** — start of shift
  - **Lunch Out** — leaves for lunch
  - **Lunch In** — returns from lunch
  - **Break Out** — leaves for break
  - **Break In** — returns from break
  - **Clock-out** — end of shift
- The [[Timesheet|Timesheet]] is created from the [[Core/Modules/Schedule|Schedule]]; it cannot exist independently.

### Restriction by status light state

- The collaborator can only punch if they have an active [[Timesheet|Timesheet]], which requires being enrolled in a hotel's [[Core/Modules/Schedule|Schedule]] with an active assignment (fixed or temporary)
- In **Pink** state (Stand-by): there is no active assignment → no Schedule → no Timesheet → cannot punch
- In **Yellow** state (Voluntary available): the collaborator declared availability, but still has no assignment → cannot punch
- In **Brown** state (Temporary assignment): the [[Recruiter|Recruiter]] assigned them, Schedule and Timesheet are generated → can punch
- The path to work during a break is: **Pink → Yellow → Brown**. Each transition is recorded in the [[Collaborator Status Light|Collaborator Status Light]] journal

### Lunch deduction

> [!important] This rule applies to **all** collaborators without exception, every shift.

| Scenario | Applied deduction |
|---|---|
| Lunch < 30 min | 30 min (mandatory minimum) |
| Lunch ≥ 30 min | Actual time taken |
| No Lunch punch | 30 min (auto-deduction) |

- **Gross hours** = Clock-out − Clock-in
- **Net hours** = Gross hours − Lunch deduction − actual Breaks
- After 6 continuous hours of work, the collaborator must take their lunch.

### Extended Lunch Indicator

- The system automatically flags collaborators whose lunch exceeds 30 minutes.
- **Visible to:** [[Inspector|Inspector]], [[Inspection/Coordinator|Coordinator]], [[Recruitment Manager|Recruitment Manager]].
- **Not visible to:** [[Hotel/General Manager|General Manager]], [[Hotel/Area Manager|Area Manager]], [[Hotel/Supervisor|Supervisor]].
- Purpose: internal Oranje supervision; it is not automatically punitive.

## Weekly pay

- The collaborator receives **weekly** pay from Oranje
- The amount is calculated from the [[Accounting/Collaborator Weekly Summary|Weekly Consolidated]], which groups the [[Timesheet|Timesheets]] of all the hotels where they worked that week
- If they worked at multiple hotels, each hotel contributes its hours with the pay rate of its [[Core/Modules/Contrato|Contract]]
- Overtime is calculated per hotel, according to each contract's policy

## Eligibility and Pool

- Only collaborators who passed the filter and were approved by Recruitment enter the [[Collaborator Pool|Collaborator Pool]].
- The [[Recruiter|Recruiter]] must check the [[Core/Modules/Blacklist|Blacklist]] before recruiting a candidate.
- A collaborator approved by the Recruiter (RF-08) enters the Pool with the [[Collaborator Status Light|Collaborator Status Light]] in Strong Green (Available) state.

## Quality Supervision (QA)

- A [[QA/QA Operator|QA Operator]] is permanently assigned to the supervision of the Collaborator scope.
- QA does **not execute** Collaborator management; it only observes aggregated pool and life cycle metrics.
- The specific metrics that the QA Operator monitors for Collaborator are defined in [[QA/Metrics and KPIs by Department#Colaborador|Metrics and KPIs — Collaborator]].
- If the [[Core/Modules/Status Lights/Quality Indicator|Quality Indicator]] of the Collaborator scope reaches **Red** state without improvement after notification, the QA Manager escalates to management.

## Related

- [[Collaborator Status Light|Collaborator Status Light]]
- [[Business Rules|Business Rules]]
- [[Collaborator Pool|Collaborator Pool]]
- [[Core/Modules/Blacklist|Blacklist]]
- [[Core/Modules/Schedule|Schedule]]
- [[Timesheet|Timesheet]]
- [[Core/Modules/Workplace Accident/Workplace Accident|Work Accident]]
- [[Core/Modules/Workplace Accident/Workplace Accident Flow|Work Accident Flow]]
- [[Recruitment/Recruitment Flow|Recruitment Flow]]
- [[Core/Modules/Requisition/Requisition Flow|Requisition Flow]]
- [[Recruiter|Recruiter]]
- [[Recruitment Manager|Recruitment Manager]]
- [[Hotel/General Manager|General Manager]]
- [[Hotel/Area Manager|Area Manager]]
- [[Hotel/Supervisor|Supervisor]]
- [[Inspector|Inspector]]
- [[Inspection/Coordinator|Coordinator]]
