---
tags:
  - module/core
aliases:
  - Associate Status Indicator
  - Associate Status White
  - Associate Status Apple Green
  - Associate Status Light Blue
  - Associate Status Orange
  - Associate Status Dark Green
  - Associate Status Yellow
  - Associate Status Brown
  - Associate Status Pink
  - Associate Status Purple
  - Associate Status Red
  - Associate Status Gray
  - Associate Status Black
---

# Associate Status Indicator

Visual status system that represents the current situation of each associate within Oranje. Each color corresponds to a state with its own transition rules.

> [!info]
> This Status Indicator describes the **associate**. Requisition states are managed in other Status Indicators: [[Requisition Status Indicator]], [[Requisition Urgency Indicator]] and [[Requisition Position Indicator]].

## States

| Color       | State                    | Description                                                                                                                           |
| ----------- | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------- |
| White       | Pre-assignment           | Just uploaded their data, has not yet been assigned to any hotel.                                                                     |
| Apple Green | Day 1-2                  | New associate, first days, as long as they are attending. The [[Inspector]] verifies their arrival on day 1.                          |
| Light Blue  | Day 3+                   | Clocked in at the property on the third day. The [[Inspector]] delivers their uniform.                                                |
| Orange      | Fixed                    | Completed one week, ready to work as a fixed associate at the hotel.                                                                  |
| Dark Green  | Available                | Available for assignment (or reinstated after a dispute ruled in their favor).                                                        |
| Yellow      | Voluntary available      | On break from a hotel, makes themselves available for temporary assignment.                                                           |
| Brown       | Temporary assignment     | Temporarily assigned to cover a full shift or part of a shift.                                                                        |
| Pink        | Stand-by                 | The hotel sent them to rest (vacation, low season).                                                                                   |
| Purple      | Did not return           | Did not attend due to their own cause.                                                                                                |
| Red         | Reported                 | The hotel reported them; [[Inspector]] reviews the case.                                                                              |
| Gray        | Injured                  | The associate suffered a [[Core/Modules/Work Accident/Work Accident\|work accident]] and is on medical leave. Protected from [[Core/Modules/Blacklist\|Blacklist]]. |
| Black       | [[Core/Modules/Blacklist\|Blacklist]] | Dispute resolved in favor of the hotel, associate blocked.                                                               |

## Business Rules

### System entries

- **→ White**: when the associate registers their data, not yet assigned.
- **White → Apple Green**: when assigned and attending on day 1. The [[Inspector]] verifies their arrival on site.

### Fixed progression

- **Apple Green → Light Blue**: when they clock in at the property on the third day. At this point the [[Inspector]] delivers their uniform.
- **Light Blue → Orange**: upon completing 7 days (fixed by system).

### Availability and temporary assignments

- **Orange → Dark Green**: when the associate becomes free (end of fixed assignment or reinstated).
- **Yellow**: activated by the associate themselves from the app, without anyone's approval. It is self-service (voluntarily available during a break). Yellow is a declaration of availability, not an assignment; the associate has no [[Core/Modules/Schedule|Schedule]] or [[Timesheet]] and cannot punch in until assigned (→ Brown).
- **Dark Green → Brown**: the [[Recruiter]] temporarily assigns them (→ Brown). The [[Recruiter]] defines the duration (assigned days) at the time of assignment. The state closes automatically when those days expire; upon closing, returns to `Dark Green` or `Orange` based on their previous state.
- **Yellow → Brown**: same temporary assignment mechanism, but the associate reached the Pool through voluntary availability. When the assigned days expire, returns to `Yellow` if still in a rest period, or to `Dark Green` if not.

### Incidents

- **→ Purple**: the system marks this when the associate does not attend without justification.
- **3 absences → Black**: automatic [[Core/Modules/Blacklist|Blacklist]] by system.
- **Pink**: activated by the [[Hotel/General Manager|General Manager]], the [[Hotel/Area Manager|Area Manager]] or the [[Hotel/Supervisor|Supervisor]] when they send the associate to rest (vacation, low season). The associate has no active assignment, therefore has no [[Core/Modules/Schedule|Schedule]] or [[Timesheet]] and cannot punch in. Upon reactivation, returns to **Dark Green**.
- **Red**: set by the hotel ([[Hotel/General Manager|General Manager]], [[Hotel/Area Manager|Area Manager]] or [[Hotel/Supervisor|Supervisor]]). Then [[Inspector]] investigates the case and the outcome leads to:
	- **Black** ([[Core/Modules/Blacklist|Blacklist]]), or
	- **Dark Green** (reinstated).
- **[[Core/Modules/Blacklist|Blacklist]] cases**: reviewed by the [[Recruitment Manager]].

### Work accident

- **Any active state → Gray**: when a [[Core/Modules/Work Accident/Work Accident|Work Accident]] report is generated. The associate is removed from operations due to medical cause.
- **Gray → Dark Green**: upon receiving medical clearance and closing the accident ticket. The associate becomes available for reassignment.
- **Blacklist protection**: while the associate is in `Gray` state, absences **do not count** toward the 3-absences → Black rule.

## Related

- [[Requisition Status Indicator]]
- [[Requisition Urgency Indicator]]
- [[Requisition Position Indicator]]
- [[Recruitment Flow]]
- [[Recruitment Manager]]
- [[Recruiter]]
- [[Inspector]]
- [[Core/Modules/Blacklist|Blacklist]]
- [[Core/Modules/Work Accident/Work Accident|Work Accident]]
