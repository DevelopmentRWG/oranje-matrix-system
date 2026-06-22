---
tags:
  - modulo/core
aliases:
  - Requisition Flow
---

# Requisition Flow

Operational life cycle of a [[Requisition|Requisition]] and its positions: from when the [[Hotel/General Manager|General Manager]] (GM), the [[Hotel/Area Manager|Area Manager]] (GH) or the [[Hotel/Supervisor|Supervisor]] (SUP) create it, until it is **Covered** or deleted. This flow **consumes** collaborators from the [[Collaborator Pool|Collaborator Pool]]; it does not produce them.

> [!info] Meeting point with the [[Recruitment Flow|Recruitment Flow]]
> The [[Collaborator Pool|Collaborator Pool]] is the only point where both flows connect. The [[Recruitment Flow|Recruitment Flow]] runs **continuously** feeding the pool (whether or not there are requisitions); this flow **consumes** it when it needs to cover positions.

## Actors

- **GM — [[Hotel/General Manager|General Manager]]**: highest authority of the hotel. Can create, authorize and reject requisitions.
- **GH — [[Hotel/Area Manager|Area Manager]]**: can create, authorize and reject requisitions.
- **SUP — [[Hotel/Supervisor|Supervisor]]**: can create, modify and prepare the requisition. Cannot authorize.
- **Recruiters — [[Recruiter|Recruiters]] / [[Recruitment/Recruiters Group Leader|Group Leaders]]**: several **participating recruiters** can work the same requisition at once (collaborative model, RR-15) and execute the staffing assignment after authorization. There is no single owner.

## Access validation

At the start, the system validates whether the user is GM, GH or SUP.
- **No access** → message "You do not have access" → **END**.
- **With access** → continues to the operations menu (create, modify, authorize, delete).

---

## 1. Requisition creation

1. The **Requisition number** is generated (see [[#RUTINA - Número de requisición automática]]).
2. Header data is recorded: Requisition number, Hotel, GM/GH, **Apple green Status** (Requisition in preparation by the hotel), date and time of the status.
3. The [[#RUTINA - Journal Requisición]] is run.

### 1.1 Add positions

For each position added:
1. An automatic **Position number** is generated (see [[#RUTINA - Número de posición automática]]).
2. The position data is captured:
   - Position (Housekeeper, Houseman, etc.)
   - Type (Temporary / Permanent)
   - Number of people
   - Start date
   - End date
   - Schedule
   - Language preference
   - Notes
3. **Gold Status** is assigned — Position in preparation by the hotel, with date and time of the status.
4. The [[#RUTINA - Journal Posición]] is run.

### 1.2 Modify position (before authorizing)

Select the position and modify any of the previous fields. Re-journal.

### 1.3 Delete position (before authorizing)

Upon confirming deletion → the position goes to **Purple Status** (physically deleted) and the journal is run.

---

## 2. Modify / Authorize existing requisition

1. All requisitions with **Apple green Status** (In preparation by the hotel) are shown.
2. The requisition in preparation is selected.
3. Its positions are shown.
4. An action is chosen: **Modify position**, **Delete position**, **Authorize requisition** or **Delete requisition**.

### 2.1 Authorize requisition

Rules:
- **Only the GM or GH can authorize.** If it is the SUP → message "Only the hotel manager can authorize the requisition".
- There must be **at least one registered position**. If not → message "You have no registered positions, register at least one position and try again".

If it complies:
1. The requisition changes to **Green Status** (Requisition authorized) + date/time.
2. The header [[Inspector]] is assigned automatically according to the hotel's [[Core/Catalogs/Zones|zone]].
3. The [[#RUTINA - Journal Requisición]] is run.
4. **For each position of the requisition**:
   - The [[#RUTINA - Prioridad de la posición automática]] is run using the authorization date and the position's start date.
   - The calculated priority is recorded (Green / Yellow / Red — see [[Requisition Urgency Status Light|Requisition Urgency Status Light]]).
   - The position changes to **Orange Status** (Position authorized) + date/time.
   - The [[#RUTINA - Journal Posición]] is run.

### 2.2 Reject requisition

If the GM or GH rejects the requisition:
1. The requisition returns to **Apple green Status** (In preparation) with the observations.
2. The [[#RUTINA - Journal Requisición]] is run.
3. The creator corrects the **same requisition** (same number/ID) and resubmits it for authorization.

> [!important] A new requisition is not generated after the rejection. The original requisition is modified and resubmitted with the same identifier.

---

## 3. Delete requisition

The message is shown: "Upon confirming the deletion of the requisition, the registered positions and the requisition will be physically deleted".

If confirmed:
- For each position → **Purple Status** (physically deleted) → position journal.
- The requisition → **Purple Status** (physically deleted) → requisition journal.

---

## 4. Leave the requisition

- If it has **one or more registered positions** → it is kept and exits.
- If it has **no** positions → the requisition is physically deleted (Purple Status) → journal.

---

## 5. Handover to Recruitment (post-authorization)

Once authorized (Green Status), the requisition's positions are reflected in the [[Core/Modules/Schedule|Schedule]] of the week corresponding to their start date. The requisition becomes available in the shared inbox, prioritized by the [[Core/Modules/Status Lights/Requisition Urgency Status Light|Urgency Status Light]].

**Collaborative taking (collaborative model, RR-15):** the requisition can have **several participating recruiters** working it at once; there is no single owner.
- A [[Recruiter|Recruiter]] or [[Recruitment/Recruiters Group Leader|Group Leader]] **takes** it from the inbox and the status goes to **Yellow** (In process). The [[#RUTINA - Journal Requisición]] is run with event `TOMO` + actor.
- When there are already recruiters working it, another recruiter can **join** (action "Join"): they are added as an additional participating recruiter **without displacing** the existing ones and **without reverting** the status light. The journal is run with event `SE_UNIO` + actor. No one "loses" the requisition.
- Any participating recruiter can **leave** (action "Leave"): only they are removed. If other recruiters remain, the requisition stays in **Yellow** (In process) and what others have already assigned **is not reset**. Only when the **last** recruiter leaves does the requisition return to **Green** (Authorized). The journal is run with event `SALIO` + actor.
- If none takes it within 24 hours, the system automatically assigns it to the [[Recruiter|Recruiter]] with the lowest load of active requisitions (they become the initial participating recruiter).

Coverage progress is **shared** among all participating recruiters. Each one consults the hotel's [[Core/Modules/Schedule|Schedule]] to see the demand and the positions pending coverage, and searches for a match in the [[Collaborator Pool|Collaborator Pool]]:
- **If there is a match** → assigns the [[Collaborator Pool|collaborator]] to the hotel and registers them in the [[Core/Modules/Schedule|Schedule]]. The [[#RUTINA - Journal Posición]] is run with event `ASIGNO_COLAB` + actor.
- **If there is no match** → the requisition is put on hold. The [[Recruitment Flow|Recruitment Flow]] runs continuously feeding the pool; priority can be escalated by zone/position, but recruitment is not "launched" — it is already always active.

> [!important] Lock at the position/slot level (not at the requisition level)
> The concurrency lock operates at the **position/slot** level, not the full requisition: two recruiters cannot assign the same collaborator to the same slot. If two try to cover the same position, **the first wins** and the second receives "position already covered". Taking an already-taken requisition **does not lock** — you join as a participating recruiter.

Closure:
- **Light Blue Status** — Fully covered. Journal with event `CAMBIO_STATUS` + actor (who closed it).
- **Red Status** — Partially covered. Journal with event `CAMBIO_STATUS` + actor (who closed it).

---

## States (status lights)

The requisition and its positions are governed by multiple status lights:

### Requisition (life cycle)
See [[Requisition Status Light|Requisition Status Light]]. States: Apple green → Green → Yellow → Light blue / Red. Purple = physically deleted.

### Position (life cycle)
- **Gold** — In preparation by the hotel.
- **Orange** — Authorized.
- **Purple** — Physically deleted.

### Position — coverage
See [[Requisition Positions Status Light|Requisition Positions Status Light]]. Green (100%), Yellow (75%), Red (<75%).

### Position — priority (time)
See [[Requisition Urgency Status Light|Requisition Urgency Status Light]]. Green (>120 h), Yellow (72–120 h), Red (<72 h).

---

## Auxiliary routines

### RUTINA - Número de requisición automática
Generates the identifier taking the day's date/time + a random check digit:
- Year (4 digits) + Month (2) + Day (2) + Hour (2, 24 h format) + Minutes (2) + Check digit (2 random alphanumeric characters: letters and/or digits).
- Example: `202604081632V1` — where `V1` is the check digit.

### RUTINA - Número de posición automática
Same format as the requisition number. Example: `202604081632V1`.

### RUTINA - Prioridad de la posición automática
Parameters: Requisition authorization date + Position start date.
- `> 120 hours` → **Green**.
- `72 – 120 hours` → **Yellow**.
- `< 72 hours` → **Red**.

### RUTINA - Journal Requisición
Records in the requisitions journal an **event per action** (not just status changes), each with its **actor** (role and name) and timestamp. Fields: Requisition, Hotel, General Manager / Area Manager, **Recruiters** (list of participating recruiters), Inspector, **Event type**, **Actor (role and name)**, Status, Note, Date and time of the event.

Event types recorded: `TOMO` (first recruiter takes the requisition), `SE_UNIO` (a recruiter joins as an additional participant), `SALIO` (a recruiter leaves), `CAMBIO_STATUS` (status-light change, includes closure). The journal is **immutable** and feeds the [[Requisition#Historial de la Requisición|Requisition History]] (RR-16).

### RUTINA - Journal Posición
Records in the positions journal an **event per action** on the position/slot, each with its **actor** (role and name) and timestamp. Fields: Requisition number, Position number, Position, Number of people, Start date, End date, **Event type**, **Actor (role and name)**, **Collaborator** (when applicable), Status, Date and time of the event.

Event types recorded: `ASIGNO_COLAB` (a recruiter assigns a collaborator to the position/slot), `REASIGNO` (unassigns/reassigns a collaborator), `CAMBIO_STATUS` (coverage change). The journal is **immutable** and feeds the [[Requisition#Historial de la Requisición|Requisition History]] (RR-16).

---

## Related

- [[Requisition|Requisition]]
- [[Collaborator Pool|Collaborator Pool]]
- [[Recruitment Flow|Recruitment Flow]]
- [[Hotel/General Manager|General Manager]] (GM)
- [[Hotel/Area Manager|Area Manager]] (GH)
- [[Hotel/Supervisor|Supervisor]] (SUP)
- [[Recruitment Manager|Recruitment Manager]]
- [[Recruiter|Recruiter]]
- [[Core/Modules/Schedule|Schedule]]
- [[Requisition Status Light|Requisition Status Light]]
- [[Requisition Urgency Status Light|Requisition Urgency Status Light]]
- [[Requisition Positions Status Light|Requisition Positions Status Light]]
