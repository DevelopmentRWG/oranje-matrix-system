---
tags:
  - module/inspection
aliases:
  - Inspection Rules
---

# Inspection Rules

Consolidation of all business rules that apply to the Inspection department within the Oranje system. Cross-reference with [[Reglas de Negocio]] (system-wide consolidated rules).

## Department Hierarchy

| Role | Function |
|---|---|
| [[Inspección/Coordinador\|Coordinator]] | Manager of Inspectors. Interdepartmental liaison and escalation of special cases |
| [[Inspector]] | Operational executor in the field, assigned by geographic zone |

## Zone Assignments

- The [[Inspección/Coordinador\|Coordinator]] assigns Inspectors to geographic [[Core/Catálogos/Zonas|Zones]].
- Each zone has a responsible [[Inspector]].
- Existing zones: **Center, South, East, West, Northwest, Southeast**.
- When a requisition is authorized, the [[Inspector]] is automatically assigned in the header based on the hotel's zone.

> [!important] The [[Inspector]] of the hotel's zone is responsible for following up on any dispute, accident, or verification that occurs at that hotel.

### Coverage During Unavailability

- If the [[Inspector]] assigned to a zone is unavailable (illness, vacation, or other cause), the [[Inspección/Coordinador|Coordinator]] temporarily reassigns another Inspector to that zone.
- The temporary reassignment does not modify the permanent zone assignment; it is coverage until the primary Inspector resumes.

## Arrival Verification and Uniform Delivery

The [[Inspector]] participates in two key transitions of the [[Semáforo del Colaborador]]:

| Event | Transition | Responsible |
|---|---|---|
| On-site arrival verification — Day 1 | White → **Apple Green** | [[Inspector]] (verifies on-site) |
| Uniform delivery — Day 3 | Apple Green → **Light Blue** | [[Inspector]] (delivers uniform) + System (associate punch) |

## Report Investigation (Red Status)

### Origin of Red Status

- The [[Hotel/Manager General\|General Manager]], [[Hotel/Manager de Área\|Area Manager]], or [[Hotel/Supervisor\|Supervisor]] activates **Red** status (Reported) in the [[Semáforo del Colaborador]].
- Accumulation of 3 absences does **not** go through Red; it goes directly to **Black** ([[Core/Módulos/Blacklist|Blacklist]]) automatically.

### Investigation and Resolution

The [[Inspector]] investigates cases of associates in Red status and issues the outcome:

| Outcome | Destination Status | Consequence |
|---|---|---|
| Dispute in favor of the hotel | → **Black** ([[Core/Módulos/Blacklist\|Blacklist]]) | Associate banned from the system |
| Dispute in favor of the associate | → **Dark Green** | Associate reinstated |

> [!note] Resulting Blacklist cases are reviewed by the [[Manager de Reclutamiento]]. The [[Inspector]] is the **only role** that can execute a manual Blacklist entry.

## Workplace Accident

The [[Inspector]] is the final party responsible for managing workplace accidents in their zone.

### Scenario A — Associate reports from the app

1. The associate generates the report from the app.
2. The signal arrives **simultaneously** to the [[Hotel/Supervisor\|SUP]] and the assigned zone [[Inspector]].
3. Both physically go to the incident location.

### Scenario B — Supervisor detects first

1. The [[Hotel/Supervisor\|SUP]] detects the accident at the property.
2. Creates the accident card from the app.
3. The signal reaches the zone [[Inspector]].

### Medical Follow-Up (Inspector)

The [[Inspector]] completes the accident card with:

| Field | Description |
|---|---|
| Transfer to medical center | If applicable, which center |
| Received diagnosis | Medical diagnosis |
| Days of incapacity | Number of days |
| Medical observations | Additional relevant information |

### Card Closure

> [!important] The [[Inspector]] is **always** the final party responsible for closing the accident card.

- **Gray → Dark Green** requires: medical discharge + accident card closure by the [[Inspector]].
- While the associate is in **Gray** status, absences **do not count** toward the 3-absence → Blacklist rule.
- After closure, the associate becomes available for reassignment.
- Reference: [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Workplace Accident Flow]].

## Extended Lunch Indicator

- **Visible to:** [[Inspector]] and [[Inspección/Coordinador\|Coordinator]].
- **Not visible to:** [[Hotel/Manager General\|General Manager]], [[Hotel/Manager de Área\|Area Manager]], or [[Hotel/Supervisor\|Supervisor]].
- Shows: associate, hotel, date, actual lunch duration.
- Activates automatically when lunch time exceeds 30 minutes.
- Purpose: Oranje's internal supervision; not automatically punitive.

> [!info] Also visible to the [[Manager de Reclutamiento]]. See [[Reclutamiento/Reglas de Reclutamiento\|Recruitment Rules]].

## Active Hotel Supervision

Once the hotel reaches **Orange** status in the [[Core/Módulos/Semáforos/Semáforo Onboarding\|Onboarding Status Indicator]] (signed agreement, active client hotel), the [[Inspector]] appears as operational responsible alongside the Recruiters.

## Quality Supervision (QA)

- A [[QA/Operador de QA\|QA Operator]] is permanently assigned to the Inspection department.
- QA does **not execute** Inspection operations; it only observes, measures, and provides feedback.
- The specific metrics that the QA Operator monitors for Inspection are defined in [[QA/Métricas y KPIs por Departamento#Inspección|Metrics and KPIs — Inspection]].
- If the [[Core/Módulos/Semáforos/Indicador de Calidad\|Quality Indicator]] of the department reaches **Red** status without improvement after notification, the QA Manager escalates to management.

## Responsibility Summary by Role

| Action | [[Inspector]] | [[Inspección/Coordinador\|Coordinator]] |
|---|---|---|
| Verify arrival Day 1 | Yes | No |
| Deliver uniform Day 3 | Yes | No |
| Investigate reports (Red) | Yes | No |
| Execute manual Blacklist | Yes | No |
| Receive accident notification | Yes | No |
| Complete and close accident card | Yes | No |
| Manage Gray → Dark Green transition | Yes | No |
| View Extended Lunch Indicator | Yes | Yes |
| Assign Inspectors to zones | No | Yes |
| Reassign Inspector due to unavailability | No | Yes |
| Supervise Inspectors | No | Yes |
| Interdepartmental liaison | No | Yes |
| Escalate special cases | No | Yes |

## Related

- [[Reglas de Negocio]]
- [[Inspector]]
- [[Inspección/Coordinador|Coordinator]]
- [[Core/Catálogos/Zonas|Zones]]
- [[Semáforo del Colaborador]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Workplace Accident]]
- [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Workplace Accident Flow]]
- [[Timesheet]]
- [[Core/Módulos/Requisicion/Requisición|Requisition]]
- [[Core/Módulos/Requisicion/Flujo de Requisición|Requisition Flow]]
- [[Core/Módulos/Semáforos/Semáforo Onboarding|Onboarding Status Indicator]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Core/Módulos/Semáforos/Indicador de Calidad|Quality Indicator]]
- [[Manager de Reclutamiento]]
- [[Hotel/Manager General|General Manager]]
- [[Hotel/Manager de Área|Area Manager]]
- [[Hotel/Supervisor|Supervisor]]
- [[Pool de Colaboradores]]
