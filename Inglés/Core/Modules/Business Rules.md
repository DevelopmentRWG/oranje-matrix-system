---
tags:
  - modulo/core
aliases:
  - Business Rules
  - Reglas de Negocio
  - System Rules
---

# Business Rules

Centralized document with the business rules that govern the Oranje system. Each rule references the module where it applies and the roles involved.

> [!info] The rules documented here are the source of truth. The status lights and flows implement these rules, but this file defines them.

## Collaborator

> [!tip] For the complete reference, see [[Collaborator Rules|Collaborator Rules]].

### Data capture in 3 phases
- **Phase 1 — Initial interview:** the [[Recruiter|Recruiter]] captures the candidate's basic data: full name, age, gender, address and phone
- **Phase 2 — App sign-up:** the Collaborator themselves completes their personal information (SSN, ITIN, Position, English level, Experience level, Transportation type, Modality)
- **Phase 3 — Emergency data:** the Collaborator completes from the app: emergency contact (name, phone, relationship), blood type and allergies or medical conditions

### Collaborator progression (Status Light)
- **→ White:** when the collaborator completes their data in the app (Phase 2 + Phase 3) and is pending validation by the Recruiter. No access enabled, no assignment.
- **White → Strong Green:** when the Recruiter approves the validation (RF-08). Collaborator enabled in the Pool, available for assignment.
- **Strong Green → Apple Green:** upon being assigned to a position and showing up on Day 1. The [[Inspector]] verifies their arrival on site
- **Apple Green → Light Blue:** when they clock in at the property on the third day. The [[Inspector]] hands over their uniform
- **Light Blue → Orange:** upon completing 7 days (automatic by the system)
- **Orange → Strong Green:** when the collaborator becomes free (end of fixed assignment or reincorporated)

### Yellow state (Voluntarily available)
- Activated by the collaborator themselves during a break
- It is the only state the collaborator can activate on their own

### Temporary assignment (Brown)
- The [[Recruiter|Recruiter]] or the [[Recruitment/Recruiters Group Leader|Group Leader]] temporarily assigns the collaborator (→ Brown) and defines the duration in days at the moment of assignment
- The state closes automatically when the assigned days expire; upon closing, it returns to Strong Green or Yellow according to its previous state
- The Recruiter or the Group Leader can manually cancel the temporary assignment before its expiration; upon canceling, the collaborator immediately returns to their previous state (Strong Green or Yellow) and is released from the hotel's Schedule

### Pink state (Stand-by)
- The [[Hotel/General Manager|General Manager]], the [[Hotel/Area Manager|Area Manager]] or the [[Hotel/Supervisor|Supervisor]] can put a collaborator in the Pink state
- Indicates that the collaborator is on hold by the hotel's decision (vacation, low season)
- The position has no end date; it ends when the [[Hotel/General Manager|General Manager]], the [[Hotel/Area Manager|Area Manager]] or the [[Hotel/Supervisor|Supervisor]] removes the collaborator from the Pink state. Upon leaving Pink, the collaborator returns to Strong Green.

### No-show (Purple)
- The system marks Purple when the collaborator does not show up without justification
- Each no-show is recorded individually

### Rule of 3 no-shows
- 3 accumulated no-shows → automatic [[Core/Modules/Blacklist|Blacklist]] (Black state)
- Applies to the [[Collaborator Status Light|Collaborator Status Light]]
- Responsible: System (automatic)

### Report Resolution (Red)
- The hotel ([[Hotel/General Manager|General Manager]], [[Hotel/Area Manager|Area Manager]] or [[Hotel/Supervisor|Supervisor]]) activates the Red state (reported)
- The zone [[Inspector]] investigates the dispute and has **its own authority to decide** the outcome:
  - **Black** ([[Core/Modules/Blacklist|Blacklist]]), if the dispute is in favor of the hotel
  - **Strong Green** (reincorporated), if the dispute is in favor of the collaborator

### Protection by Workplace Accident (Gray)
- Any active state → Gray when a workplace accident report is generated
- Protects the collaborator from the rule of 3 no-shows; no-shows during disability do not count
- Gray → Strong Green: requires medical clearance + closure of the accident card by the [[Inspector]]
- Reference: [[Core/Modules/Workplace Accident/Workplace Accident Flow|Workplace Accident Flow]]

## Hotel organizational structure

### Two supported hierarchies
- The platform supports two hierarchical configurations for the hotel, according to its size and complexity:
  - **Simple hierarchy:** [[Hotel/General Manager|General Manager]] (also operates as [[Hotel/Area Manager|Area Manager]]) → [[Hotel/Supervisor|SUP]] → Oranje Collaborators
  - **Extended hierarchy:** [[Hotel/General Manager|General Manager]] → [[Hotel/Area Manager|Area Manager]] → [[Hotel/Supervisor|Supervisor]] → Oranje Collaborators

### Hotel departments
- The [[Hotel Departments|Hotel Departments]] are: Housekeeping, Food, Maintenance and Front Desk
- In the extended hierarchy, each department has its own Manager and Supervisor(s)
- The [[Posiciones|Positions]] requested in requisitions correspond to a specific department of the hotel

### General Manager
- The [[Hotel/General Manager|General Manager]] is the highest authority of the hotel and **always exists** in both hierarchies
- In a simple hierarchy, they also operate as [[Hotel/Area Manager|Area Manager]] (same person, two roles)
- Can create, authorize and reject requisitions
- Can generate QR for clock-in
- Has global visibility of the [[Core/Modules/Schedule|Schedule]] and [[Timesheet]] of all departments
- Main point of contact with Oranje at the executive level

## Requisition and Authorization

### System access
- The [[Hotel/General Manager|General Manager]] (GM), the [[Hotel/Area Manager|Area Manager]] (GH) and the [[Hotel/Supervisor|Supervisor]] (SUP) have access to the requisitions module
- Users without access receive the message: "You do not have access"

### Creation and preparation
- Any hotel role ([[Hotel/General Manager|General Manager]], [[Hotel/Area Manager|Area Manager]] or [[Hotel/Supervisor|Supervisor]]) creates the requisition (Apple Green state — In preparation)
- The requisition number is generated automatically: Year (4 digits) + Month (2) + Day (2) + Hour (2, 24h format) + Minutes (2) + Check digit (2 random alphanumeric characters). Example: `202604081632V1`
- The same format applies to the position number

### Requisition Authorization
- Only the [[Hotel/General Manager|General Manager]] (GM) or the [[Hotel/Area Manager|Area Manager]] (GH) can authorize a requisition
- The SUP receives a block message: "Only the hotel manager can authorize the requisition"
- At least one position must exist in order to authorize; otherwise: "You have no registered positions, register at least one position and try again"
- A rejection returns the requisition to the creator with observations ("In preparation" state)

### Upon authorization
- The system automatically calculates the urgency of each position
- Each position goes from Gold to Orange and the system calculates its priority
- Authorized positions are reflected in the [[Core/Modules/Schedule|Schedule]] of the week corresponding to their start date
- The [[Inspector]] in the header is assigned automatically according to the hotel's [[Core/Catalogs/Zones|zone]]

### Urgency Formula
- Calculated per position: `requisition authorization date` vs `position start date`
- `> 120 hours` → Strong Green (Normal)
- `72 – 120 hours` → Yellow (Medium)
- `< 72 hours` → Red (Urgent)
- The system automatically reevaluates and adjusts the color as time advances
- Reference: [[Requisition Urgency Status Light|Requisition Urgency Status Light]]

### Position Coverage
- Requisition = Light Blue only if ALL positions are Green (100% covered)
- Position in Yellow: up to 25% missing
- Position in Red: more than 25% missing
- If any position is in Yellow or Red → Requisition in Red
- Reference: [[Requisition Positions Status Light|Requisition Positions Status Light]]

### Assignment (Collaborative Self-Pick)
- **Collaborative model (RR-15):** a requisition can have **N participating recruiters** working it at once; there is no single owner. Taking an already-taken requisition **does not transfer or lock it**: the recruiter **joins** as an additional participant (action "Join") without displacing the existing ones or reverting the status light
- The authorized requisition stays in the shared inbox; a [[Recruiter|Recruiter]] or [[Recruitment/Recruiters Group Leader|Group Leader]] takes it → the requisition goes to Yellow (In process)
- **Leave (not release):** a participating recruiter can **leave**; only they are removed. The requisition stays in Yellow (In process) if other recruiters remain and what others have already assigned **is not reset**; it only returns to Green (Authorized) when the **last** recruiter leaves
- **Shared progress + lock per position/slot:** coverage progress is shared among all participating recruiters; each one can search the [[Collaborator Pool|pool]] and assign collaborators. The concurrency lock operates at the **position/slot** level (two recruiters do not assign the same collaborator to the same position; the first wins, the second sees "position already covered"), **not** at the level of the full requisition
- If it goes >24h without being taken, the system automatically assigns it to the [[Recruiter|Recruiter]] with the lowest load of active requisitions. The process is transparent (the [[Recruitment Manager|Recruitment Manager]] does not receive a notification)
- If there is no match in the [[Collaborator Pool|pool]], the requisition is put on hold; the Recruitment Flow is already always active
- **History (RR-16):** each action (take, join, leave, assign/unassign collaborator, status change, closure) is recorded in an immutable chronological timeline with actor and timestamp, visible to the participating recruiters, the Group Leader and the Recruitment Manager

### Position life cycle
- The position has a start date but no defined end date
- It ends when the [[Hotel/Area Manager|Area Manager]] or the [[Hotel/Supervisor|Supervisor]] puts the collaborator in Stand-by (Pink state in the [[Collaborator Status Light|Collaborator Status Light]])

### Deletion (Purple)
- Cross-cutting state: reached from any state when the requisition is deleted
- Requisition with no positions upon leaving the editor → automatic physical deletion
- The system runs the Requisition Journal ROUTINE on every deletion
- When deleting a requisition with positions → each position also goes to Purple with an individual journal

### Automatic journals
- Journals record an **event per action with actor** (role and name) and timestamp, not just status changes. They are **immutable** and feed the [[Core/Modules/Requisition/Requisition#Historial de la Requisición|Requisition History]] (RR-16)
- **Requisition Journal ROUTINE:** records Requisition, Hotel, General Manager / Area Manager, **Recruiters** (list of participants), Inspector, **Event type** (`TOMO` / `SE_UNIO` / `SALIO` / `CAMBIO_STATUS`), **Actor**, Status, Note, Date and time of the event
- **Position Journal ROUTINE:** records Requisition number, Position number, Position, Number of people, Start date, End date, **Event type** (`ASIGNO_COLAB` / `REASIGNO` / `CAMBIO_STATUS`), **Actor**, **Collaborator** (when applicable), Status, Date and time of the event

## Blacklist

### Automatic Blacklist
- Triggered by the rule of 3 no-shows
- State: Black in the [[Collaborator Status Light|Collaborator Status Light]]

### Manual Blacklist
- Triggered by a dispute resolved in favor of the hotel (Red state → [[Inspector]] investigation)
- The zone [[Inspector]] decides with their own authority; it does not require validation from the [[Recruitment Manager|Recruitment Manager]]

### Permanence of the Black state
- Black is **PERMANENT**: there is no rehabilitation or appeal
- The record is kept in the system marked as Black
- The collaborator does not appear in active searches; the history is kept for internal consultation

### Mandatory consultation
- The [[Recruiter|Recruiter]] must consult the [[Core/Modules/Blacklist|Blacklist]] before recruiting a candidate, to avoid recruiting someone who has been banned again

## Workplace Accident

### Activation of the Gray state
- The accident report activates the Gray state in the [[Collaborator Status Light|Collaborator Status Light]] from any active state
- **Scenario A:** the Collaborator reports from the app; the signal reaches the SUP and the assigned zone [[Inspector]] simultaneously
- **Scenario B:** the SUP ([[Hotel/Supervisor|Supervisor]]) reports; the signal reaches the Inspector
- An automatic report number is generated (same pattern as a requisition: date/time + check digit)

### Card closure
- The [[Inspector]] is always the final party responsible for closing the accident card
- Gray → Strong Green: requires medical clearance + closure of the card by the Inspector
- The collaborator becomes available for reassignment after the closure

### Accident journal
- Each status change generates a record with: Report number, Hotel, Collaborator, Reported by, Status, Note, Date and time of the status

## Onboarding and Sales

### Hotel enablement
- The hotel can only generate requisitions when it reaches the Orange Status in the [[Onboarding Status Light|Onboarding Status Light]]
- Before Orange, the hotel is a commercial prospect managed by [[Sales/Sales|Sales]]

### Prospect-to-client conversion
- Only the [[Sales/Roles/Business Developer Coordinator|Business Developer Coordinator]] (BDC) can approve the conversion
- **Precondition:** creation of the [[Sales/Hotel Onboarding/Concepts/Hotel User|Hotel User]] in the system
- Upon approval, the [[Sales/Hotel Onboarding/Concepts/Automatic Conversion Trigger|Automatic Conversion Trigger]] is fired with parallel actions:
  - System sends a welcome email to the hotel
  - System notifies the assigned Business Developer
  - Hotel disappears from the prospect list

### Terms and Conditions Document
- Created in Onboarding Yellow Status by the BD or the BDC
- Negotiated in Onboarding Pink Status
- Content: Pay rate, Bill rate, Overtime, Holidays, Calendar
- Final validation: [[Sales/Roles/Business Developer Coordinator|Business Developer Coordinator]] before closing the [[Contrato|Contract]]

### Custom Proposal
- Prepared and sent in Onboarding Green Status
- Adjusted/resumed from Onboarding Brown Status when there is a stall

### Reactivation of states
- Red, Black and Brown always reactivate toward Light Blue
- Brown is not a terminal status: it is an unblocking bridge operated by the BDC

### Traceability
- Every status change in Onboarding is recorded with date, responsible party and comment

## Quality Indicator / QA

### Fundamental principle
- [[QA/QA|QA]] does not execute the operation of any department; it only observes, measures and gives feedback

### Team structure
- There are 6 [[QA/QA Operator|QA Operators]], one for each supervised department: Inspection, Hotel, Collaborator, Sales, Recruitment and [[Customer Service/Customer Service|Customer Service]]
- Each operator is fixedly assigned to a single department

### Indicator update
- The [[QA/QA Operator|QA Operator]] proposes the state change based on metrics
- The [[QA/QA Manager|QA Manager]] validates and approves the update
- Only the QA Manager can formally update the [[Quality Indicator|Quality Indicator]] of each department
- Each department has its own independent Indicator; the initial state is Green

### Indicator transitions
- **→ Green:** initial state when QA begins to supervise a department
- **Green → Yellow:** when the Operator detects metrics out of range or issues observations that are not addressed
- **Yellow → Red:** when the observations persist without attention or the metrics deteriorate significantly
- **Red → Yellow:** when the department begins to address observations and shows improvement
- **Yellow → Green:** when all observations are resolved and the metrics return to parameters

### Escalation
- Department in Red without improvement after notification → the [[QA/QA Manager|QA Manager]] escalates to management

### Metrics and KPIs per department
- Each department has between 5 and 6 concrete KPIs that the [[QA/QA Operator|QA Operator]] monitors
- Each KPI has defined thresholds (Target / At risk / Critical) that feed the [[Quality Indicator|Quality Indicator]]
- Complete reference: [[QA/Metrics and KPIs by Department|Metrics and KPIs per Department]]

## Recruitment and Pool

### Nature of the flow
- The [[Recruitment/Recruitment Flow|Recruitment Flow]] is continuous: Recruitment is always hiring, whether or not there are open requisitions
- Requisitions without a match can accelerate or prioritize certain positions/zones, but they are not a condition for starting the flow

### Requisition distribution (Self-Pick)
- Authorized requisitions become available in a shared inbox, prioritized by the [[Core/Modules/Status Lights/Requisition Urgency Status Light|Urgency Status Light]]
- [[Recruiter|Recruiters]] and [[Recruitment/Recruiters Group Leader|Group Leaders]] freely take requisitions from the inbox
- If a requisition has gone more than 24 hours without being taken, the system automatically assigns it to the [[Recruiter|Recruiter]] with the lowest load of active requisitions. The process is transparent (the [[Recruitment Manager|Recruitment Manager]] does not receive a notification)

### Collaborator approval
- The [[Recruiter|Recruiter]] validates and approves the collaborator after they complete their sign-up in the app
- The Recruiter enables the collaborator's access to the panels
- An approved collaborator enters the [[Collaborator Pool|Collaborator Pool]] with the [[Collaborator Status Light|Collaborator Status Light]] in the Strong Green state (Available)

### Pool eligibility
- Only collaborators who passed the filter and were approved by Recruitment enter the Pool

## Schedule and Timesheet

### Schedule configuration
- The hotel's week is defined by the contract (start and end of week)
- When a requisition is created with a start date within the week, its positions are reflected in the [[Core/Modules/Schedule|Schedule]] of that week

### Work shift

- The daily shift is **8 hours**
- The work week is 7 days: **5 working + 2 days off**
- Gross weekly total: **40 hours** (8 hrs × 5 days)
- Net payable weekly total: **37.5 hours** (40 hrs − 30 min of lunch × 5 shifts)

### Assignment in the Schedule
- Upon assigning a collaborator from the [[Collaborator Pool|Collaborator Pool]], they are registered in the hotel's schedule

### Timesheet dependency
- The [[Timesheet]] is created from the [[Core/Modules/Schedule|Schedule]]; it cannot exist independently
- If the [[Core/Modules/Schedule|Schedule]] is modified after the [[Timesheet]] was created, the Timesheet is automatically updated to reflect the changes

### Clock-in mechanism
- The collaborator clocks in via QR generated by the [[Hotel/General Manager|General Manager]] or the [[Hotel/Area Manager|Area Manager]]
- Clock-ins are recorded in entry/exit pairs for each period:
  - **Clock In** — start of shift
  - **Lunch Out** — leaves for lunch
  - **Lunch In** — returns from lunch
  - **Break Out** — leaves for break
  - **Break In** — returns from break
  - **Clock Out** — end of shift
- This counts the collaborator's worked time

### Clock-in restriction by collaborator state

- Clock-in is only possible when the collaborator has an active [[Timesheet]], which requires being enrolled in a hotel's [[Core/Modules/Schedule|Schedule]]
- Without an active assignment (fixed or temporary) there is no Schedule, without a Schedule there is no Timesheet, and without a Timesheet there is no clock-in
- States that **do not allow clock-in**: Pink (Stand-by) and Yellow (Voluntarily available), because in neither of them is there an active assignment
- The only path for a collaborator on break to record hours is the complete route: **Pink → Yellow → Brown**, where the [[Recruiter|Recruiter]] temporarily assigns them and the corresponding Schedule/Timesheet is generated

### Lunch Deduction

> [!important] This rule applies to **all** collaborators without exception, on every shift.

- The system deducts lunch time from the collaborator's [[Timesheet]]:
  - **Lunch under 30 min:** 30 minutes are deducted (mandatory minimum)
  - **Lunch over 30 min:** the actual time taken is deducted
  - **No Lunch clock-in:** 30 minutes are auto-deducted
- The lunch deduction directly impacts the computation of payable hours in the [[Timesheet]]

### Break Deduction

- Breaks are also deducted from payable time in the [[Timesheet]]
- The deducted time is the actual time recorded with the **Break Out / Break In** pair
- The number and duration of breaks is defined by each hotel

### Payable hours formula

- **Net hours** = (Clock Out − Clock In) − actual Lunch − actual Breaks

### Extended Lunch Indicator

- The system automatically identifies collaborators whose lunch time exceeds 30 minutes
- **Restricted visibility** — only internal Oranje roles:
  - [[Inspector]]
  - [[Inspection/Coordinator|Coordinator]]
  - [[Recruitment Manager|Recruitment Manager]]
- **Not visible to the hotel:** the [[Hotel/General Manager|General Manager]], the [[Hotel/Area Manager|Area Manager]] and the [[Hotel/Supervisor|Supervisor]] do not have access to this indicator
- **Purpose:** an internal supervision tool to detect patterns and take operational actions; it is not automatically punitive

### Timesheet Compliance Indicator

- The system automatically calculates a status-light indicator that compares the collaborator's actual compliance against the hotel's contractual parameters
- **Input:** [[Core/Modules/Contrato|Contract]] parameters + [[Timesheet]] data
- **Weekly evaluation:** the structure is Year → Weeks (numbered according to the calendar and the hotel's start/end of week)
- **Comparison:** days worked/required, days off, hours worked/required
- **Mid-week entry:** the system automatically prorates the remaining days of the cycle; the days prior to sign-up are marked in Gray
- Complete reference: [[Core/Modules/Status Lights/Timesheet Compliance Indicator|Timesheet Compliance Indicator]]

### Weekly Consolidation and Payment to the Collaborator

- The system automatically generates a [[Accounting/Collaborator Weekly Summary|Weekly Consolidation]] per collaborator at the end of each week
- The consolidation groups the [[Timesheet|Timesheets]] of all the hotels where the collaborator worked that week
- The calculation applies the pay rate of each hotel's [[Core/Modules/Contrato|Contract]] separately
- Overtime is calculated **per hotel**, according to the policy agreed in each contract
- The payment period is **weekly**
- **Oranje pays the collaborator**; each hotel pays Oranje according to its bill rate
- The [[Accountant|Accountant]] reviews and the [[Accounting Manager|Accounting Manager]] approves the Consolidation before executing the payment
- The overtime threshold is **40 gross hours per week** per hotel

## Inspection and Zones

### Assignment by zone
- Each hotel belongs to a geographic [[Core/Catalogs/Zones|zone]]
- Each zone corresponds to an [[Inspector]] assigned by the [[Inspection/Coordinator|Coordinator]]
- The Inspector of the hotel's zone is responsible for following up on any dispute in that hotel

### Inspector responsibilities
- **Day 1:** verifies the collaborator's arrival at the property (Strong Green → Apple Green transition)
- **Day 3:** hands over the uniform to the collaborator (→ Light Blue transition)
- **Reports:** investigates disputes (Red state) and resolves toward Black or Strong Green
- **Accidents:** final party responsible for closing the accident card; manages the Gray → Strong Green transition

### Coordinator
- The [[Inspection/Coordinator|Coordinator]] assigns inspectors to the geographic zones and supervises their field work

## Error handling

### Clock-in failure
- If the system fails to record a clock-in, the collaborator can retry.
- If the failure persists, the system notifies the [[Hotel/Supervisor|Supervisor]] so they can take manual action.

### ID collision (check digit)
- If, when generating a requisition, position or report number, a check-digit collision (duplicate) occurs, the system automatically regenerates the check digit until it obtains a unique value.

### Disconnection during operation
- If the user loses connection while performing an operation (data capture, form filling, etc.), the operation is automatically saved as a draft.
- The draft can be resumed and completed when the connection is restored.

## Related

- [[Collaborator Status Light|Collaborator Status Light]]
- [[Requisition Status Light|Requisition Status Light]]
- [[Requisition Urgency Status Light|Requisition Urgency Status Light]]
- [[Requisition Positions Status Light|Requisition Positions Status Light]]
- [[Onboarding Status Light|Onboarding Status Light]]
- [[Quality Indicator|Quality Indicator]]
- [[Core/Modules/Status Lights/Timesheet Compliance Indicator|Timesheet Compliance Indicator]]
- [[Core/Modules/Requisition/Requisition Flow|Requisition Flow]]
- [[Core/Modules/Workplace Accident/Workplace Accident Flow|Workplace Accident Flow]]
- [[Recruitment/Recruitment Flow|Recruitment Flow]]
- [[Sales/Hotel Onboarding/Onboarding Flow|Onboarding Flow]]
- [[Core/Modules/Blacklist|Blacklist]]
- [[Collaborator Pool|Collaborator Pool]]
- [[Core/Modules/Schedule|Schedule]]
- [[Timesheet]]
- [[Hotel/General Manager|General Manager]]
- [[Hotel/Area Manager|Area Manager]]
- [[Hotel/Supervisor|Supervisor]]
- [[Inspector]]
- [[Inspection/Coordinator|Coordinator]]
- [[Recruiter|Recruiter]]
- [[Recruitment Manager|Recruitment Manager]]
- [[QA/QA|QA]]
- [[QA/QA Manager|QA Manager]]
- [[QA/QA Operator|QA Operator]]
- [[Sales/Roles/Business Developer Coordinator|Business Developer Coordinator]]
- [[Sales/Hotel Onboarding/Concepts/Hotel User|Hotel User]]
- [[Sales/Hotel Onboarding/Concepts/Automatic Conversion Trigger|Automatic Conversion Trigger]]
- [[Sales/Hotel Onboarding/Concepts/Terms and Conditions Document|Terms and Conditions Document]]
- [[Core/Catalogs/Zones|Zones]]
