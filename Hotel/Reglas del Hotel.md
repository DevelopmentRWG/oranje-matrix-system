---
tags:
  - module/hotel
aliases:
  - Hotel Business Rules
---

# Hotel Business Rules

Consolidation of all business rules that apply to Hotel roles within the Oranje system. Cross-reference with [[Reglas de Negocio]] (general system consolidation).

## Supported Hierarchies

The platform supports two organizational models for the hotel:

| Hierarchy | Structure |
|---|---|
| **Simple** | [[Hotel/Manager General\|Manager General]] (also operates as [[Hotel/Manager de Área\|Manager de Área]]) → [[Hotel/Supervisor\|SUP]] → Oranje Associates |
| **Extended** | [[Hotel/Manager General\|Manager General]] → [[Hotel/Manager de Área\|Manager de Área]] → [[Hotel/Supervisor\|Supervisor]] → Oranje Associates |

- In the simple hierarchy, the [[Hotel/Manager General|Manager General]] also operates as [[Hotel/Manager de Área|Manager de Área]] (same person, two roles).
- Hotel departments are: **Housekeeping, Food & Beverage, Maintenance, and Front Desk** (see [[Core/Catálogos/Departamentos del Hotel|Departamentos del Hotel]]).
- In the extended hierarchy, each department has its own Manager and Supervisor(s).

## Hotel Enablement

> [!important] The hotel can only generate requisitions when it reaches **Orange** status in the [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]].

- Before reaching Orange, the hotel is a commercial prospect managed by Sales.

## Requisitions — Creation and Authorization

### Module Access

- The [[Hotel/Manager General|Manager General]], the [[Hotel/Manager de Área|Manager de Área]], and the [[Hotel/Supervisor|Supervisor]] have access to the requisitions module.
- Users without access receive the message: **"You do not have access"**.

### Creation

- Any hotel role ([[Hotel/Manager General|Manager General]], [[Hotel/Manager de Área|Manager de Área]], or [[Hotel/Supervisor|Supervisor]]) creates the requisition (status **Apple Green** — In Progress in the [[Core/Módulos/Semáforos/Semáforo de Requisición|Semáforo de Requisición]]).
- The requisition number is automatically generated: `Year (4) + Month (2) + Day (2) + Hour (2, 24h) + Minutes (2) + Homoclave (2 alphanumeric)`. Example: `202604081632V1`.

### Authorization

> [!important] Only the [[Hotel/Manager de Área|Manager de Área]] or the [[Hotel/Manager General|Manager General]] can authorize a requisition. If the [[Hotel/Supervisor|Supervisor]] attempts to do so, the system blocks the action with the message: **"Only the hotel manager can authorize the requisition"**.

- To authorize, at least **one position** must be registered. If not: **"No positions registered. Please register at least one position and try again"**.
- Rejection returns the requisition to the creator with comments (status **In Progress**).

> [!info] Authorization by the [[Hotel/Manager de Área|Manager de Área]] or the [[Hotel/Manager General|Manager General]] is a **security layer** to prevent false or incorrect requisitions from reaching Recruitment.

## Automatic Effects Upon Authorization

When a requisition is authorized, the system automatically executes:

| Effect | Detail |
|---|---|
| Urgency calculation | Per position, according to the [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición\|urgency formula]]: `> 120h` → Dark Green (Normal), `72–120h` → Yellow (Medium), `< 72h` → Red (Urgent) |
| Position transition | From Gold to Orange in the [[Core/Módulos/Semáforos/Semáforo de Posiciones de la Requisición\|Semáforo de Posiciones]] |
| Schedule reflection | Positions appear in the [[Core/Módulos/Schedule\|Schedule]] for the week corresponding to their start date |
| Inspector assignment | The [[Inspector]] is automatically assigned based on the hotel's zone |

## Position Lifecycle

- Each position has a **start date but no defined end date**.
- The position ends when the [[Hotel/Manager de Área|Manager de Área]] or the [[Hotel/Supervisor|Supervisor]] places the associate on **Stand-by** (Pink status in the [[Semáforo del Colaborador]]).

## Requisition Deletion

- Upon confirming deletion, the system displays: **"By confirming the deletion of the requisition, the registered positions and the requisition will be permanently deleted"**.
- The **Purple** status is transversal: it is reached from any status when the requisition is deleted.
- If a requisition has no positions when exiting the editor → **automatic permanent deletion**.
- When deleting a requisition with positions → each position also moves to Purple with an individual journal entry.

## Assigned Staff Management

Responsibilities over assigned associates (all hotel roles):

| Action | Effect on [[Semáforo del Colaborador]] | Description |
|---|---|---|
| Generate QR code | — | Allows associates to punch in the [[Timesheet]] |
| Place on Stand-by | → **Pink** | Waiting on a hotel decision (vacation, low season). No end date; ends when any hotel role changes the status. The associate has no Schedule or Timesheet and cannot punch |
| Report associate | → **Red** | Initiates an investigation by the [[Inspector]] |
| Manage weekly Schedule | — | Administers the assignments in the hotel's [[Core/Módulos/Schedule\|Schedule]] |

> [!important] All hotel roles ([[Hotel/Manager General|Manager General]], [[Hotel/Manager de Área|Manager de Área]], and [[Hotel/Supervisor|Supervisor]]) can place an associate in Pink (Stand-by) status.

## Timesheet and Lunch Deduction

> [!info] Punching and Lunch deduction rules are also documented in [[Colaborador/Reglas del Colaborador|Reglas del Colaborador]] from the associate's perspective.

### Dependency

- The [[Timesheet]] is created from the [[Core/Módulos/Schedule|Schedule]]; it cannot exist independently.
- The hotel's week is defined by the contract (start and end of week).

### Shift

- The daily shift is **8 hours**.
- The work week is 7 days: **5 working + 2 rest days**.
- Total gross weekly: **40 hours** (8 hrs × 5 days).
- Total net payable weekly: **37.5 hours** (40 hrs − 30 min lunch × 5 shifts).

### Punching

- The associate punches via **QR** generated by the [[Hotel/Manager de Área|Manager de Área]] or the [[Hotel/Manager General|Manager General]].
- Punches are recorded in entry/exit pairs for each period (exactly six):
  - **Clock In** — start of shift
  - **Lunch Out** — leaves for lunch
  - **Lunch In** — returns from lunch
  - **Break Out** — leaves for break
  - **Break In** — returns from break
  - **Clock Out** — end of shift

### Lunch Deduction

> [!important] This rule applies to **all** associates without exception, on every shift.

| Scenario | Deduction applied |
|---|---|
| Lunch < 30 min | 30 min (mandatory minimum) |
| Lunch ≥ 30 min | Actual time taken |
| No lunch punch | 30 min (auto-deduction) |

- **Gross hours** = Clock Out − Clock In
- **Net hours** = Gross hours − Lunch Deduction − Actual Breaks
- After 6 continuous hours of work, the associate must take their lunch.

## Extended Lunch Indicator

> [!note] The [[Hotel/Manager General|Manager General]], the [[Hotel/Manager de Área|Manager de Área]], and the [[Hotel/Supervisor|Supervisor]] **do not have access** to the Extended Lunch Indicator. It is exclusive to Oranje's internal roles ([[Inspector]], [[Inspección/Coordinador|Coordinador]], [[Manager de Reclutamiento]]).

## Timesheet Compliance Indicator

The system automatically calculates a color-coded indicator (Green / Yellow / Red) that compares the associate's actual compliance against the hotel's contractual parameters, evaluated per week. See full reference: [[Core/Módulos/Semáforos/Indicador de Cumplimiento del Timesheet|Indicador de Cumplimiento del Timesheet]].

## Workplace Accident — Supervisor Responsibilities

The [[Hotel/Supervisor|Supervisor]] has an active role in reporting and capturing workplace accidents:

### Scenario A — Associate reports from the app

1. The associate generates the report from the app.
2. The signal arrives **simultaneously** to the [[Hotel/Supervisor|SUP]] and the assigned zone [[Inspector]].
3. The SUP goes to the location physically and captures: exact location, circumstances, witnesses, and immediate care provided.

### Scenario B — Supervisor detects first

1. The [[Hotel/Supervisor|SUP]] detects the accident on the property.
2. Creates the accident card from the app.
3. The signal reaches the zone [[Inspector]].

- In both scenarios, the associate moves to **Gray** status in the [[Semáforo del Colaborador]] (protection against the 3-absence rule).
- Reference: [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]].

## General Manager

The [[Hotel/Manager General|Manager General]] is the hotel's highest authority and **always exists** in both hierarchies:

- Has **global visibility** of the [[Core/Módulos/Schedule|Schedule]] and [[Timesheet]] across all departments.
- Can create, authorize, and reject requisitions.
- Can generate QR codes, place on Stand-by, report associates, and report workplace accidents.
- In the simple hierarchy, also operates as [[Hotel/Manager de Área|Manager de Área]] (same person).
- Primary point of contact with Oranje at the management level.

## Quality Supervision (QA)

- A [[QA/Operador de QA|Operador de QA]] is permanently assigned to the Hotel department.
- QA **does not execute** Hotel operations; it only observes, measures, and provides feedback.
- The specific metrics that the QA Operator monitors for Hotel are defined in [[QA/Métricas y KPIs por Departamento#Hotel|Métricas y KPIs — Hotel]].
- If the [[Core/Módulos/Semáforos/Indicador de Calidad|Indicador de Calidad]] for the department reaches **Red** status without improvement after notification, the QA Manager escalates to management.

## Responsibility Summary by Role

| Action | [[Hotel/Manager General\|Manager General]] | [[Hotel/Manager de Área\|Manager de Área]] | [[Hotel/Supervisor\|Supervisor]] |
|---|---|---|---|
| Create requisition | Yes | Yes | Yes |
| Authorize requisition | Yes | Yes | No |
| Reject requisition | Yes | Yes | No |
| Generate QR for punching | Yes | Yes | No |
| Place on Stand-by (Pink) | Yes | Yes | Yes |
| Report associate (Red) | Yes | Yes | Yes |
| Report workplace accident | Yes | Yes | Yes |
| Manage weekly Schedule | Global visibility | Yes (their department) | No |
| View Extended Lunch Indicator | No | No | No |
| Global Schedule/Timesheet visibility | Yes | No | Yes (their department) |

## Related

- [[Reglas de Negocio]]
- [[Hotel/Manager de Área|Manager de Área]]
- [[Hotel/Supervisor|Supervisor]]
- [[Hotel/Manager General|Manager General]]
- [[Core/Módulos/Requisicion/Flujo de Requisición|Flujo de Requisición]]
- [[Core/Módulos/Semáforos/Semáforo de Requisición|Semáforo de Requisición]]
- [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición|Semáforo de Urgencia de Requisición]]
- [[Core/Módulos/Semáforos/Semáforo de Posiciones de la Requisición|Semáforo de Posiciones de la Requisición]]
- [[Semáforo del Colaborador]]
- [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Timesheet]]
- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]]
- [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Core/Catálogos/Departamentos del Hotel|Departamentos del Hotel]]
- [[Pool de Colaboradores]]
