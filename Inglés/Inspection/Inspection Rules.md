---
tags:
  - modulo/inspeccion
aliases:
  - Inspection Rules
---

# Inspection Rules

Consolidation of all the business rules that apply to the Inspection department within the Oranje system. Cross-reference with [[Business Rules|Business Rules]] (general system summary).

## Department hierarchy

| Role | Function |
|---|---|
| [[Inspection/Coordinator\|Coordinator]] | Head of the Inspectors. Interdepartmental liaison and escalation of special cases |
| [[Inspector]] | Operational executor in the field, assigned by geographic zone |

## Zone assignment

- The [[Inspection/Coordinator\|Coordinator]] assigns Inspectors to the geographic [[Core/Catalogs/Zones|Zones]].
- Each zone has a responsible [[Inspector]].
- Existing zones: **Centro, Sur, Este, Oeste, Noroeste, Sureste**.
- When a requisition is authorized, the [[Inspector]] is automatically assigned in the header according to the hotel's zone.

> [!important] The [[Inspector]] of the hotel's zone is responsible for following up on any dispute, accident or verification that occurs at that hotel.

### Coverage due to unavailability

- If the [[Inspector]] assigned to a zone is not available (illness, vacation or another cause), the [[Inspection/Coordinator|Coordinator]] temporarily reassigns another Inspector to that zone.
- The temporary reassignment does not modify the permanent zone assignment; it is coverage until the titular Inspector returns.

## Arrival verification and uniform delivery

The [[Inspector]] participates in two key transitions of the [[Collaborator Status Light|Collaborator Status Light]]:

| Event | Transition | Responsible |
|---|---|---|
| On-site arrival verification — Day 1 | Strong Green → **Apple Green** | [[Inspector]] (verifies on site) |
| Uniform delivery — Day 3 | Apple Green → **Light Blue** | [[Inspector]] (delivers uniform) + System (collaborator's punch) |

## Report investigation (Red state)

### Origin of the Red state

- The [[Hotel/General Manager\|General Manager]], [[Hotel/Area Manager\|Area Manager]] or [[Hotel/Supervisor\|Supervisor]] activates the **Red** (Reported) state in the [[Collaborator Status Light|Collaborator Status Light]].
- The accumulation of 3 absences does **not** go through Red; it goes directly to **Black** ([[Core/Modules/Blacklist|Blacklist]]) automatically.

### Investigation and resolution

The [[Inspector]] investigates the cases of collaborators in the Red state and issues the result:

| Result | Destination state | Consequence |
|---|---|---|
| Dispute in favor of the hotel | → **Black** ([[Core/Modules/Blacklist\|Blacklist]]) | Collaborator banned from the system |
| Dispute in favor of the collaborator | → **Strong Green** | Collaborator reinstated |

> [!note] The resulting Blacklist cases are reviewed by the [[Recruitment Manager|Recruitment Manager]]. The [[Inspector]] is the **only role** that can execute the manual entry to Blacklist.

## Workplace Accident

The [[Inspector]] is the final party responsible for the management of workplace accidents in their zone.

### Scenario A — Collaborator reports from the app

1. The collaborator generates the report from the app.
2. The signal arrives **simultaneously** to the [[Hotel/Supervisor\|SUP]] and the assigned zone [[Inspector]].
3. Both physically go to the location of the incident.

### Scenario B — Supervisor detects first

1. The [[Hotel/Supervisor\|SUP]] detects the accident at the property.
2. Creates the accident card from the app.
3. The signal arrives to the zone [[Inspector]].

### Medical follow-up (Inspector)

The [[Inspector]] completes the accident card with:

| Field | Description |
|---|---|
| Transfer to medical center | If applicable, which center |
| Diagnosis received | Medical diagnosis |
| Days of disability | Number of days |
| Medical observations | Additional relevant information |

### Card closure

> [!important] The [[Inspector]] is **always** the final party responsible for closing the accident card.

- **Gray → Strong Green** requires: medical discharge + closure of the accident card by the [[Inspector]].
- While the collaborator is in the **Gray** state, absences do **not** count toward the 3-absences → Blacklist rule.
- After closure, the collaborator becomes available for reassignment.
- Reference: [[Core/Modules/Workplace Accident/Workplace Accident Flow|Workplace Accident Flow]].

## Extended Lunch Indicator

- **Visible to:** [[Inspector]] and [[Inspection/Coordinator\|Coordinator]].
- **Not visible to:** [[Hotel/General Manager\|General Manager]], [[Hotel/Area Manager\|Area Manager]] nor [[Hotel/Supervisor\|Supervisor]].
- Shows: collaborator, hotel, date, real lunch time.
- It is activated automatically when the lunch time exceeds 30 minutes.
- Purpose: internal Oranje supervision; it is not automatically punitive.

> [!info] It is also visible to the [[Recruitment Manager|Recruitment Manager]]. See [[Recruitment/Recruitment Rules\|Recruitment Rules]].

## Active hotel supervision

Once the hotel reaches the **Orange** status in the [[Core/Modules/Status Lights/Onboarding Status Light\|Onboarding Status Light]] (agreement signed, active client hotel), the [[Inspector]] appears as the operational party responsible along with the Recruiters.

## Quality Supervision (QA)

- A [[QA/QA Operator\|QA Operator]] is permanently assigned to the Inspection department.
- QA does **not execute** the Inspection operation; it only observes, measures and provides feedback.
- The specific metrics that the QA Operator monitors for Inspection are defined in [[QA/Metrics and KPIs by Department#Inspección|Metrics and KPIs — Inspection]].
- If the department's [[Core/Modules/Status Lights/Quality Indicator\|Quality Indicator]] reaches the **Red** state without improvement after notification, the QA Manager escalates to management.

## Summary of responsibilities by role

| Action | [[Inspector]] | [[Inspection/Coordinator\|Coordinator]] |
|---|---|---|
| Verify Day 1 arrival | Yes | No |
| Deliver Day 3 uniform | Yes | No |
| Investigate reports (Red) | Yes | No |
| Execute manual Blacklist | Yes | No |
| Receive accident notification | Yes | No |
| Complete and close accident card | Yes | No |
| Manage Gray → Strong Green transition | Yes | No |
| View Extended Lunch Indicator | Yes | Yes |
| Assign Inspectors to zones | No | Yes |
| Reassign Inspector due to unavailability | No | Yes |
| Supervise Inspectors | No | Yes |
| Interdepartmental liaison | No | Yes |
| Escalate special cases | No | Yes |

## Related

- [[Business Rules|Business Rules]]
- [[Inspector]]
- [[Inspection/Coordinator|Coordinator]]
- [[Core/Catalogs/Zones|Zones]]
- [[Collaborator Status Light|Collaborator Status Light]]
- [[Core/Modules/Blacklist|Blacklist]]
- [[Core/Modules/Workplace Accident/Workplace Accident|Workplace Accident]]
- [[Core/Modules/Workplace Accident/Workplace Accident Flow|Workplace Accident Flow]]
- [[Timesheet]]
- [[Core/Modules/Requisition/Requisition|Requisition]]
- [[Core/Modules/Requisition/Requisition Flow|Requisition Flow]]
- [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]]
- [[Core/Modules/Schedule|Schedule]]
- [[Core/Modules/Status Lights/Quality Indicator|Quality Indicator]]
- [[Recruitment Manager|Recruitment Manager]]
- [[Hotel/General Manager|General Manager]]
- [[Hotel/Area Manager|Area Manager]]
- [[Hotel/Supervisor|Supervisor]]
- [[Collaborator Pool|Collaborator Pool]]
