---
tags:
  - modulo/core
aliases:
  - Collaborator Status Light
  - Collaborator Status White
  - Collaborator Status Apple Green
  - Collaborator Status Light Blue
  - Collaborator Status Orange
  - Collaborator Status Strong Green
  - Collaborator Status Yellow
  - Collaborator Status Brown
  - Collaborator Status Pink
  - Collaborator Status Purple
  - Collaborator Status Red
  - Collaborator Status Gray
  - Collaborator Status Black
---

# Collaborator Status Light

System of visual states that represents the current situation of each collaborator within Oranje. Each color corresponds to a state with its own transition rules.

> [!info]
> This status light describes the **collaborator**. The requisition states are handled in other status lights: [[Requisition Status Light|Requisition Status Light]], [[Requisition Urgency Status Light|Requisition Urgency Status Light]] and [[Requisition Positions Status Light|Requisition Positions Status Light]].

## States

| Color        | State                                 | Description                                                                                                                                                                        |
| ------------ | ------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| White        | Pre-assignment                        | The collaborator uploaded their data in the app but has not yet been validated by the Recruiter. Pre-validation state: no access enabled, no assignment.                          |
| Apple Green  | Day 1-2                               | New collaborator, first days, as long as they are attending. The [[Inspector]] verifies their arrival on day 1.                                                                    |
| Light Blue   | Day 3+                                | Punched in at the property on the third day. The [[Inspector]] hands over their uniform.                                                                                           |
| Orange       | Permanent                             | A week passed, ready to collaborate permanently at the hotel.                                                                                                                      |
| Strong Green | Available                             | Available for assignment. Applies to: (1) collaborator just validated by the Recruiter (Phase 2 approved, belongs to Oranje); (2) collaborator reinstated after the end of a permanent assignment, a dispute in their favor or medical discharge. |
| Yellow       | Voluntarily available                 | On rest from a hotel, makes themselves available for temporary assignment.                                                                                                         |
| Brown        | Temporary assignment                  | Temporarily assigned to cover the full shift or part of the shift.                                                                                                                 |
| Pink         | Stand-by                              | The hotel sent them to rest (vacation, low season).                                                                                                                               |
| Purple       | Did not return                        | Did not attend due to their own cause.                                                                                                                                            |
| Red          | Reported                              | The hotel reported them; [[Inspector]] reviews the case.                                                                                                                          |
| Gray         | Injured                               | The collaborator suffered a [[Core/Modules/Workplace Accident/Workplace Accident\|work accident]] and is on medical leave. Protected from [[Core/Modules/Blacklist\|Blacklist]]. |
| Black        | [[Core/Modules/Blacklist\|Blacklist]] | Dispute resolved in favor of the hotel, collaborator blocked.                                                                                                                     |

## Key rules

### Entries into the system

- **→ White**: when the collaborator completes their data in the app (Phase 2 + Phase 3) and is pending validation by the Recruiter. No access enabled, no assignment.
- **White → Strong Green**: when the Recruiter approves the validation (RF-08). The collaborator is enabled in the Pool, with access propagated, available for assignment.
- **Strong Green → Apple Green**: when assigned to a position and attending on day 1. The [[Inspector]] verifies their arrival on site.

### Progression as permanent

- **Apple Green → Light Blue**: when they punch in at the property on the third day. At this moment the [[Inspector]] hands over their uniform.
- **Light Blue → Orange**: upon completing 7 days (permanent by system).

### Availability and temporary assignments

- **Orange → Strong Green**: when the collaborator becomes free (end of permanent assignment or reinstated).
- **Yellow**: activated by the collaborator themselves from the app, without anyone's approval. It is self-service (voluntarily available during a rest period). Yellow is a declaration of availability, not an assignment; the collaborator has no [[Core/Modules/Schedule|Schedule]] or [[Timesheet]] and cannot punch until assigned (→ Brown).
- **Strong Green → Brown**: the [[Recruiter|Recruiter]] or the [[Recruitment/Recruiters Group Leader|Group Leader]] assigns them temporarily (→ Brown). The duration (assigned days) is defined at the moment of assignment. The state closes automatically when those days expire; upon closing, it returns to `Strong Green`.
- **Yellow → Brown**: same temporary assignment mechanism, but the collaborator reached the Pool through voluntary availability. When the assigned days expire, it returns to `Yellow` if still in a rest period, or to `Strong Green` if no longer.
- **Brown → Strong Green / Yellow (manual cancellation)**: the [[Recruiter|Recruiter]] or the [[Recruitment/Recruiters Group Leader|Group Leader]] can manually cancel the temporary assignment before the days expire. Upon cancellation, the collaborator returns immediately to their previous state (`Strong Green` or `Yellow`) and is released from the hotel's Schedule.

### Incidents

- **→ Purple**: the system marks them when the collaborator does not attend without justification.
- **3 absences → Black**: automatic [[Core/Modules/Blacklist|Blacklist]] by the system.
- **Pink**: activated by the [[Hotel/General Manager|General Manager]], the [[Hotel/Area Manager|Area Manager]] or the [[Hotel/Supervisor|Supervisor]] when they send the collaborator to rest (vacation, low season). The collaborator has no active assignment, therefore has no [[Core/Modules/Schedule|Schedule]] or [[Timesheet]] and cannot punch. Upon reactivation, it returns to **Strong Green**.
- **Red**: set by the hotel ([[Hotel/General Manager|General Manager]], [[Hotel/Area Manager|Area Manager]] or [[Hotel/Supervisor|Supervisor]]). Then [[Inspector]] investigates the case and the result leads to:
	- **Black** ([[Core/Modules/Blacklist|Blacklist]]), or
	- **Strong Green** (reinstated).
- **[[Core/Modules/Blacklist|Blacklist]] cases**: reviewed by the [[Recruitment Manager|Recruitment Manager]].

### Work accident

- **Any active state → Gray**: when a [[Core/Modules/Workplace Accident/Workplace Accident|Work Accident]] report is generated. The collaborator is out of operation due to medical cause.
- **Gray → Strong Green**: upon receiving medical discharge and the accident card being closed. The collaborator becomes available for reassignment.
- **Blacklist protection**: while the collaborator is in `Gray` state, absences **do not count** toward the rule of 3 absences → Black.

## Related

- [[Requisition Status Light|Requisition Status Light]]
- [[Requisition Urgency Status Light|Requisition Urgency Status Light]]
- [[Requisition Positions Status Light|Requisition Positions Status Light]]
- [[Recruitment Flow|Recruitment Flow]]
- [[Recruitment Manager|Recruitment Manager]]
- [[Recruiter|Recruiter]]
- [[Inspector]]
- [[Core/Modules/Blacklist|Blacklist]]
- [[Core/Modules/Workplace Accident/Workplace Accident|Work Accident]]
