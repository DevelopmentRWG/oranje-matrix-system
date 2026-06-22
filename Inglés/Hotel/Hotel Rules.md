---
tags:
  - modulo/hotel
aliases:
  - Hotel Business Rules
---

# Hotel Business Rules

Consolidation of all the business rules that apply to the Hotel roles within the Oranje system. Cross-referenced with [[Business Rules|Business Rules]] (general system summary).

## Supported hierarchies

The platform supports two organizational models for the hotel:

| Hierarchy | Structure |
|---|---|
| **Simple** | [[Hotel/General Manager\|General Manager]] (also operates as [[Hotel/Area Manager\|Area Manager]]) → [[Hotel/Supervisor\|SUP]] → Oranje Collaborators |
| **Extended** | [[Hotel/General Manager\|General Manager]] → [[Hotel/Area Manager\|Area Manager]] → [[Hotel/Supervisor\|Supervisor]] → Oranje Collaborators |

- In the simple hierarchy, the [[Hotel/General Manager|General Manager]] also operates as [[Hotel/Area Manager|Area Manager]] (same person, two roles).
- The hotel departments are: **Housekeeping, Food, Maintenance and Front Desk** (see [[Core/Catalogs/Hotel Departments|Hotel Departments]]).
- In the extended hierarchy, each department has its own Manager and Supervisor(s).

## Hotel enablement

> [!important] The hotel can only generate requisitions when it reaches **Orange** status in the [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]].

- Before reaching Orange, the hotel is a commercial prospect managed by Sales.

## Requisitions — creation and authorization

### Module access

- The [[Hotel/General Manager|General Manager]], the [[Hotel/Area Manager|Area Manager]] and the [[Hotel/Supervisor|Supervisor]] have access to the requisitions module.
- Users without access receive the message: **"You do not have access"**.

### Creation

- Any hotel role ([[Hotel/General Manager|General Manager]], [[Hotel/Area Manager|Area Manager]] or [[Hotel/Supervisor|Supervisor]]) creates the requisition (**Apple Green** status — In progress in the [[Core/Modules/Status Lights/Requisition Status Light|Requisition Status Light]]).
- The requisition number is generated automatically: `Year (4) + Month (2) + Day (2) + Hour (2, 24h) + Minutes (2) + Check key (2 alphanumeric)`. Example: `202604081632V1`.

### Authorization

> [!important] Only the [[Hotel/Area Manager|Area Manager]] or the [[Hotel/General Manager|General Manager]] can authorize a requisition. If the [[Hotel/Supervisor|Supervisor]] tries to do so, the system blocks the action with the message: **"Only the hotel manager can authorize the requisition"**.

- To authorize, **at least one position** must be registered. If not: **"You have no positions registered, register at least one position and try again"**.
- The rejection returns the requisition to the creator with observations (**In progress** status).

> [!info] The authorization by the [[Hotel/Area Manager|Area Manager]] or the [[Hotel/General Manager|General Manager]] is a **security layer** to prevent false or incorrect requisitions from reaching Recruitment.

## Automatic effects upon authorization

When a requisition is authorized, the system automatically executes:

| Effect | Detail |
|---|---|
| Urgency calculation | Per position, according to the [[Core/Modules/Status Lights/Requisition Urgency Status Light\|urgency formula]]: `> 120h` → Strong Green (Normal), `72–120h` → Yellow (Medium), `< 72h` → Red (Urgent) |
| Position transition | From Gold to Orange in the [[Core/Modules/Status Lights/Requisition Positions Status Light\|Positions Status Light]] |
| Reflection in Schedule | The positions are placed in the [[Core/Modules/Schedule\|Schedule]] of the week corresponding to their start date |
| Inspector assignment | The [[Inspector]] is assigned automatically according to the hotel's zone |

## Position life cycle

- Each position has a **start date but no defined end date**.
- The position ends when the [[Hotel/Area Manager|Area Manager]] or the [[Hotel/Supervisor|Supervisor]] puts the collaborator on **Stand-by** (Pink status in the [[Collaborator Status Light|Collaborator Status Light]]).

## Requisition deletion

- Upon confirming the deletion, the system shows: **"Upon confirming the deletion of the requisition, the registered positions and the requisition will be physically deleted"**.
- The **Purple** status is transversal: it is reached from any status when the requisition is deleted.
- If a requisition has no positions when leaving the editor → **automatic physical deletion**.
- When deleting a requisition with positions → each position also transitions to Purple with an individual journal.

## Management of assigned staff

Responsibilities over the assigned collaborators (all hotel roles):

| Action | Effect on [[Collaborator Status Light\|Collaborator Status Light]] | Description |
|---|---|---|
| Generate QR code | — | Allows collaborators to clock in on the [[Timesheet]] |
| Put on Stand-by | → **Pink** | Awaiting a hotel decision (vacation, low season). No end date; ends when any hotel role changes the status. The collaborator is left without Schedule or Timesheet and cannot clock in |
| Report collaborator | → **Red** | Starts an investigation by the [[Inspector]] |
| Manage weekly Schedule | — | Administers the assignments of the hotel's [[Core/Modules/Schedule\|Schedule]] |

> [!important] All hotel roles ([[Hotel/General Manager|General Manager]], [[Hotel/Area Manager|Area Manager]] and [[Hotel/Supervisor|Supervisor]]) can put a collaborator in Pink status (Stand-by).

## Timesheet and Lunch deduction

> [!info] The clock-in and Lunch deduction rules are also documented in [[Collaborator/Collaborator Rules|Collaborator Business Rules]] from the collaborator's perspective.

### Dependency

- The [[Timesheet]] is created from the [[Core/Modules/Schedule|Schedule]]; it cannot exist independently.
- The hotel's week is defined by the contract (start and end of the week).

### Workday

- The daily workday is **8 hours**
- The work week is 7 days: **5 working + 2 of rest**
- Gross weekly total: **40 hours** (8 hrs × 5 days)
- Net payable weekly total: **37.5 hours** (40 hrs − 30 min of lunch × 5 workdays)

### Clock-in

- The collaborator clocks in via **QR** generated by the [[Hotel/Area Manager|Area Manager]] or the [[Hotel/General Manager|General Manager]].
- Clock-ins are recorded in entry/exit pairs for each period (exactly six):
  - **Entry** — start of workday
  - **Lunch Out** — leaves to eat
  - **Lunch In** — returns from eating
  - **Break Out** — leaves for break
  - **Break In** — returns from break
  - **Exit** — end of workday

### Lunch deduction

> [!important] This rule applies to **all** collaborators without exception, on every workday.

| Scenario | Deduction applied |
|---|---|
| Lunch < 30 min | 30 min (mandatory minimum) |
| Lunch ≥ 30 min | Actual time taken |
| No Lunch clock-in | 30 min (auto-deduction) |

- **Gross hours** = Exit − Entry
- **Net hours** = Gross hours − Lunch deduction − actual Breaks
- After 6 continuous hours of work, the collaborator must take their lunch.

## Extended Lunch Indicator

> [!note] The [[Hotel/General Manager|General Manager]], the [[Hotel/Area Manager|Area Manager]] and the [[Hotel/Supervisor|Supervisor]] **do not have access** to the Extended Lunch Indicator. It is exclusive to internal Oranje roles ([[Inspector]], [[Inspection/Coordinator|Coordinator]], [[Recruitment Manager|Recruitment Manager]]).

## Timesheet Compliance Indicator

The system automatically calculates a status-light indicator (Green / Yellow / Red) that compares the collaborator's actual compliance against the hotel's contractual parameters, evaluated weekly. See full reference: [[Core/Modules/Status Lights/Timesheet Compliance Indicator|Timesheet Compliance Indicator]].

## Workplace Accident — Supervisor responsibilities

The [[Hotel/Supervisor|Supervisor]] has an active role in the reporting and capture of workplace accidents:

### Scenario A — Collaborator reports from the app

1. The collaborator generates the report from the app.
2. The signal reaches the [[Hotel/Supervisor|SUP]] and the assigned zone [[Inspector]] **simultaneously**.
3. The SUP physically goes and captures: exact location, circumstances, witnesses and immediate care provided.

### Scenario B — Supervisor detects first

1. The [[Hotel/Supervisor|SUP]] detects the accident on the property.
2. Creates the accident card from the app.
3. The signal reaches the zone [[Inspector]].

- In both scenarios, the collaborator transitions to **Gray** status in the [[Collaborator Status Light|Collaborator Status Light]] (protection against the 3-absences rule).
- Reference: [[Core/Modules/Workplace Accident/Workplace Accident Flow|Workplace Accident Flow]].

## General Manager

The [[Hotel/General Manager|General Manager]] is the highest authority of the hotel and **always exists** in both hierarchies:

- Has **global visibility** of the [[Core/Modules/Schedule|Schedule]] and [[Timesheet]] of all departments.
- Can create, authorize and reject requisitions.
- Can generate QR, put on Stand-by, report collaborators and report workplace accidents.
- In a simple hierarchy, also operates as [[Hotel/Area Manager|Area Manager]] (same person).
- Main point of contact with Oranje at the executive level.

## Quality Supervision (QA)

- A [[QA/QA Operator|QA Operator]] is permanently assigned to the Hotel department.
- QA **does not execute** the Hotel operation; it only observes, measures and gives feedback.
- The specific metrics that the QA Operator monitors for Hotel are defined in [[QA/Metrics and KPIs by Department#Hotel|Metrics and KPIs — Hotel]].
- If the department's [[Core/Modules/Status Lights/Quality Indicator|Quality Indicator]] reaches **Red** status without improvement after notification, the QA Manager escalates to management.

## Summary of responsibilities by role

| Action | [[Hotel/General Manager\|General Manager]] | [[Hotel/Area Manager\|Area Manager]] | [[Hotel/Supervisor\|Supervisor]] |
|---|---|---|---|
| Create requisition | Yes | Yes | Yes |
| Authorize requisition | Yes | Yes | No |
| Reject requisition | Yes | Yes | No |
| Generate QR for clock-in | Yes | Yes | No |
| Put on Stand-by (Pink) | Yes | Yes | Yes |
| Report collaborator (Red) | Yes | Yes | Yes |
| Report workplace accident | Yes | Yes | Yes |
| Manage weekly Schedule | Global visibility | Yes (its department) | No |
| View Extended Lunch Indicator | No | No | No |
| Global Schedule/Timesheet visibility | Yes | No | Yes (its department) |

## Related

- [[Business Rules|Business Rules]]
- [[Hotel/Area Manager|Area Manager]]
- [[Hotel/Supervisor|Supervisor]]
- [[Hotel/General Manager|General Manager]]
- [[Core/Modules/Requisition/Requisition Flow|Requisition Flow]]
- [[Core/Modules/Status Lights/Requisition Status Light|Requisition Status Light]]
- [[Core/Modules/Status Lights/Requisition Urgency Status Light|Requisition Urgency Status Light]]
- [[Core/Modules/Status Lights/Requisition Positions Status Light|Requisition Positions Status Light]]
- [[Collaborator Status Light|Collaborator Status Light]]
- [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]]
- [[Core/Modules/Schedule|Schedule]]
- [[Timesheet]]
- [[Core/Modules/Workplace Accident/Workplace Accident|Workplace Accident]]
- [[Core/Modules/Workplace Accident/Workplace Accident Flow|Workplace Accident Flow]]
- [[Core/Modules/Blacklist|Blacklist]]
- [[Core/Catalogs/Hotel Departments|Hotel Departments]]
- [[Collaborator Pool|Collaborator Pool]]
