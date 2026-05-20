---
tags:
  - module/core
aliases:
  - Requisition Flow
---

# Requisition Flow

Operational lifecycle of a [[Requisition]] and its positions: from the moment the [[Hotel/General Manager|General Manager]] (GM), the [[Hotel/Area Manager|Area Manager]] (GH), or the [[Hotel/Supervisor|Supervisor]] (SUP) creates it, until it is **Covered** or deleted. This flow **consumes** associates from the [[Associate Pool]]; it does not produce them.

> [!info] Meeting point with the [[Recruitment Flow]]
> The [[Associate Pool]] is the only point where both flows connect. The [[Recruitment Flow]] runs **continuously** feeding the pool (whether or not there are requisitions); this flow **consumes** from it when it needs to fill positions.

## Actors

- **GM — [[Hotel/General Manager|General Manager]]**: highest authority at the hotel. Can create, authorize, and reject requisitions.
- **GH — [[Hotel/Area Manager|Area Manager]]**: can create, authorize, and reject requisitions.
- **SUP — [[Hotel/Supervisor|Supervisor]]**: can create, modify, and prepare the requisition. Cannot authorize.
- **Recruiter — [[Recruiter]]**: executes personnel assignment after authorization.

## Access Validation

At the start, the system validates whether the user is a GM, GH, or SUP.
- **No access** → message "No access available" → **END**.
- **With access** → continues to the operations menu (create, modify, authorize, delete).

---

## 1. Requisition Creation

1. A **Requisition number** is generated (see [[#ROUTINE - Automatic requisition number]]).
2. Header data is recorded: Requisition number, Hotel, GM/GH, **Status Apple Green** (Requisition being drafted by the hotel), date and time of status.
3. [[#ROUTINE - Requisition Journal]] is executed.

### 1.1 Add Positions

For each position added:
1. An automatic **Position number** is generated (see [[#ROUTINE - Automatic position number]]).
2. Position data is captured:
   - Position (Housekeeper, Houseman, etc.)
   - Type (Temporary / Permanent)
   - Headcount
   - Start date
   - End date
   - Schedule
   - Language preference
   - Notes
3. **Status Gold** is assigned — Position being prepared/drafted by the hotel, with date and time of status.
4. [[#ROUTINE - Position Journal]] is executed.

### 1.2 Modify Position (before authorization)

Select the position and modify any of the above fields. Re-journal.

### 1.3 Delete Position (before authorization)

Upon confirming deletion → the position transitions to **Status Purple** (physically deleted) and the journal is executed.

---

## 2. Modify / Authorize Existing Requisition

1. All requisitions with **Status Apple Green** (Being drafted by the hotel) are displayed.
2. The requisition being drafted is selected.
3. Its positions are displayed.
4. An action is chosen: **Modify position**, **Delete position**, **Authorize requisition**, or **Delete requisition**.

### 2.1 Authorize Requisition

Rules:
- **Only the GM or GH can authorize.** If SUP → message "Only the hotel manager can authorize the requisition".
- There must be **at least one registered position**. If not → message "No positions registered, register at least one position and try again".

If conditions are met:
1. The requisition changes to **Status Green** (Requisition authorized) + date/time.
2. The [[Inspector]] in the header is automatically assigned according to the hotel's [[Core/Catalogs/Zones|zone]].
3. [[#ROUTINE - Requisition Journal]] is executed.
4. **For each position in the requisition**:
   - [[#ROUTINE - Automatic position priority]] is executed using the authorization date and the position's start date.
   - The calculated priority is recorded (Green / Yellow / Red — see [[Requisition Urgency Indicator]]).
   - The position changes to **Status Orange** (Position authorized) + date/time.
   - [[#ROUTINE - Position Journal]] is executed.

### 2.2 Reject Requisition

If the GM or GH rejects the requisition:
1. The requisition returns to **Status Apple Green** (Being drafted) with observations.
2. [[#ROUTINE - Requisition Journal]] is executed.
3. The creator corrects the **same requisition** (same number/ID) and resubmits for authorization.

> [!important] A new requisition is not generated after rejection. The original requisition with the same identifier is modified and resubmitted.

---

## 3. Delete Requisition

The message is displayed: "Upon confirming the deletion of the requisition, the registered positions and the requisition will be physically deleted".

If confirmed:
- For each position → **Status Purple** (physically deleted) → position journal.
- The requisition → **Status Purple** (physically deleted) → requisition journal.

---

## 4. Exit Requisition

- If it has **one or more registered positions** → it is saved and exited.
- If it has **no** positions → the requisition is physically deleted (Status Purple) → journal.

---

## 5. Handoff to Recruitment (post-authorization)

Once authorized (Status Green), the requisition's positions are reflected in the [[Core/Modules/Schedule|Schedule]] for the week corresponding to their start date. The requisition becomes available in the shared queue, prioritized by the [[Core/Modules/Status Indicators/Requisition Urgency Indicator|Urgency Indicator]]. A [[Recruiter]] or [[Recruitment/Recruiter Team Lead|Team Lead]] picks it from the queue and the status changes to **Yellow** (Personnel assignment in process by recruiter). If no one picks it within 24 hours, the system automatically assigns it to the [[Recruiter]] with the lowest active requisition load.

The recruiter checks the hotel's [[Core/Modules/Schedule|Schedule]] to see demand and positions pending coverage, and searches for a match in the [[Associate Pool]]:
- **If there is a match** → assigns the associate to the hotel and registers them in the [[Core/Modules/Schedule|Schedule]].
- **If there is no match** → the requisition remains on hold. The [[Recruitment Flow]] runs continuously feeding the pool; priority can be escalated by zone/position, but recruitment is not "launched" — it is always active.

Closure:
- **Status Light Blue** — Fully covered by the recruiter.
- **Status Red** — Partially covered by the recruiter.

---

## Statuses (status indicators)

The requisition and its positions are governed by multiple status indicators:

### Requisition (lifecycle)
See [[Requisition Status Indicator]]. Statuses: Apple Green → Green → Yellow → Light Blue / Red. Purple = physically deleted.

### Position (lifecycle)
- **Gold** — Being prepared/drafted by the hotel.
- **Orange** — Authorized.
- **Purple** — Physically deleted.

### Position — coverage
See [[Requisition Position Indicator]]. Green (100%), Yellow (75%), Red (<75%).

### Position — priority (time)
See [[Requisition Urgency Indicator]]. Green (>120 h), Yellow (72-120 h), Red (<72 h).

---

## Auxiliary Routines

### ROUTINE - Automatic requisition number
Generates the identifier using the date/time of the day + random homoclave:
- Year (4 digits) + Month (2) + Day (2) + Hour (2, 24h format) + Minutes (2) + Homoclave (2 random alphanumeric characters: letters and/or digits).
- Example: `202604081632V1` — where `V1` is the homoclave.

### ROUTINE - Automatic position number
Same format as the requisition number. Example: `202604081632V1`.

### ROUTINE - Automatic position priority
Parameters: Requisition authorization date + Position start date.
- `> 120 hours` → **Green**.
- `72 - 120 hours` → **Yellow**.
- `< 72 hours` → **Red**.

### ROUTINE - Requisition Journal
Records in the requisition journal: Requisition, Hotel, General Manager / Area Manager, Recruiter, Inspector, Status, Note, Date and time of status.

### ROUTINE - Position Journal
Records in the position journal: Requisition number, Position number, Position, Headcount, Start date, End date, Status, Date and time of status.

---

## Related

- [[Requisition]]
- [[Associate Pool]]
- [[Recruitment Flow]]
- [[Hotel/General Manager|General Manager]] (GM)
- [[Hotel/Area Manager|Area Manager]] (GH)
- [[Hotel/Supervisor|Supervisor]] (SUP)
- [[Recruitment Manager]]
- [[Recruiter]]
- [[Core/Modules/Schedule|Schedule]]
- [[Requisition Status Indicator]]
- [[Requisition Urgency Indicator]]
- [[Requisition Position Indicator]]
