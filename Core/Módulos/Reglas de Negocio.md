---
tags:
  - module/core
aliases:
  - Business Rules
  - System Rules
---

# Business Rules

Centralized document with the business rules that govern the Oranje system. Each rule references the module where it applies and the roles involved.

> [!info] The rules documented here are the source of truth. The status indicators and flows implement these rules, but this file defines them.

## Associate

> [!tip] For the complete reference, see [[Reglas del Colaborador]].

### 3-Phase Data Capture
- **Phase 1 — Initial interview:** the [[Reclutadora]] captures the candidate's basic data: full name, age, gender, address, and phone number
- **Phase 2 — App registration:** the Associate completes their personal information (SSN, ITIN, Position, English level, Experience level, Transportation type, Employment type)
- **Phase 3 — Emergency data:** the Associate completes from the app: emergency contact (name, phone, relationship), blood type, and allergies or medical conditions

### Associate Progression (Status Indicator)
- **White → Apple Green:** upon being assigned and attending Day 1. The [[Inspector]] verifies their arrival on-site
- **Apple Green → Light Blue:** when they punch in at the property on the third day. The [[Inspector]] delivers their uniform
- **Light Blue → Orange:** upon completing 7 days (automatic by system)
- **Orange → Dark Green:** when the associate becomes available (end of fixed assignment or reinstated)

### Yellow Status (Voluntary Available)
- Activated by the associate themselves during a rest period
- It is the only status the associate can activate on their own

### Temporary Assignment (Brown)
- The [[Reclutadora]] temporarily assigns the associate (→ Brown) and defines the duration in days at the time of assignment
- The status closes automatically when the assigned days expire; upon closing, returns to Dark Green or Orange depending on their prior state

### Pink Status (Stand-by)
- The [[Hotel/Manager General|General Manager]], the [[Hotel/Manager de Área|Area Manager]], or the [[Hotel/Supervisor|Supervisor]] can put an associate in Pink status
- Indicates the associate is on hold by hotel decision (vacation, low season)
- The position has no end date; it ends when the [[Hotel/Manager General|General Manager]], the [[Hotel/Manager de Área|Area Manager]], or the [[Hotel/Supervisor|Supervisor]] removes the associate from Pink status. Upon leaving Pink, the associate returns to Dark Green.

### Absence (Purple)
- The system marks Purple when the associate does not attend without justification
- Each absence is recorded individually

### 3-Absence Rule
- 3 accumulated absences → automatic [[Core/Módulos/Blacklist|Blacklist]] (Black status)
- Applies to the [[Semáforo del Colaborador]]
- Responsible: System (automatic)

### Report Resolution (Red)
- The hotel ([[Hotel/Manager General|General Manager]], [[Hotel/Manager de Área|Area Manager]], or [[Hotel/Supervisor|Supervisor]]) activates Red status (reported)
- The [[Inspector]] for the zone investigates the dispute and has **independent authority to decide** the outcome:
  - **Black** ([[Core/Módulos/Blacklist|Blacklist]]), if the dispute favors the hotel
  - **Dark Green** (reinstated), if the dispute favors the associate

### Work Accident Protection (Gray)
- Any active status → Gray when a work accident report is generated
- Protects the associate from the 3-absence rule; absences during disability do not count
- Gray → Dark Green: requires medical clearance + accident card closure by the [[Inspector]]
- Reference: [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Work Accident Flow]]

## Hotel Organizational Structure

### Two Supported Hierarchies
- The platform supports two hierarchical configurations for the hotel, based on its size and complexity:
  - **Simple hierarchy:** [[Hotel/Manager General|General Manager]] (also operates as [[Hotel/Manager de Área|Area Manager]]) → [[Hotel/Supervisor|SUP]] → Oranje Associates
  - **Extended hierarchy:** [[Hotel/Manager General|General Manager]] → [[Hotel/Manager de Área|Area Manager]] → [[Hotel/Supervisor|Supervisor]] → Oranje Associates

### Hotel Departments
- The [[Departamentos del Hotel]] are: Housekeeping, Food & Beverage, Maintenance, and Front Desk
- In the extended hierarchy, each department has its own Manager and Supervisor(s)
- The [[Posiciones]] requested in requisitions correspond to a specific hotel department

### General Manager
- The [[Hotel/Manager General|General Manager]] is the highest authority at the hotel and **always exists** in both hierarchies
- In the simple hierarchy, also operates as [[Hotel/Manager de Área|Area Manager]] (same person, two roles)
- Can create, authorize, and reject requisitions
- Can generate QR for punching
- Has global visibility of the [[Core/Módulos/Schedule|Schedule]] and [[Timesheet]] across all departments
- Primary point of contact with Oranje at the executive level

## Requisition and Authorization

### System Access
- The [[Hotel/Manager General|General Manager]] (GM), the [[Hotel/Manager de Área|Area Manager]] (GH), and the [[Hotel/Supervisor|Supervisor]] (SUP) have access to the requisition module
- Users without access receive the message: "No access available"

### Creation and Drafting
- Any hotel role ([[Hotel/Manager General|General Manager]], [[Hotel/Manager de Área|Area Manager]], or [[Hotel/Supervisor|Supervisor]]) creates the requisition (Apple Green status — Being drafted by the hotel)
- The requisition number is generated automatically: Year (4 digits) + Month (2) + Day (2) + Hour (2, 24h format) + Minutes (2) + Homoclave (2 random alphanumeric characters). Example: `202604081632V1`
- The same format applies for the position number

### Requisition Authorization
- Only the [[Hotel/Manager General|General Manager]] (GM) or the [[Hotel/Manager de Área|Area Manager]] (GH) can authorize a requisition
- The SUP receives a blocking message: "Only the hotel manager can authorize the requisition"
- At least one position must exist to authorize; otherwise: "No positions registered, register at least one position and try again"
- Rejection returns the requisition to the creator with observations (status "Being drafted")

### Upon Authorization
- The system automatically calculates the urgency of each position
- Each position transitions from Gold to Orange and the system calculates its priority
- Authorized positions are reflected in the [[Core/Módulos/Schedule|Schedule]] for the week corresponding to their start date
- The [[Inspector]] in the header is automatically assigned according to the hotel's [[Core/Catálogos/Zonas|zone]]

### Urgency Formula
- Calculated per position: `requisition authorization date` vs `position start date`
- `> 120 hours` → Dark Green (Normal)
- `72 - 120 hours` → Yellow (Medium)
- `< 72 hours` → Red (Urgent)
- The system automatically re-evaluates and adjusts the color as time progresses
- Reference: [[Semáforo de Urgencia de Requisición]]

### Position Coverage
- Requisition = Light Blue only if ALL positions are Green (100% covered)
- Position in Yellow: up to 25% missing
- Position in Red: more than 25% missing
- If any position is in Yellow or Red → Requisition in Red
- Reference: [[Semáforo de Posiciones de la Requisición]]

### Assignment (Self-Pick)
- The authorized requisition is placed in the shared queue; a [[Reclutadora]] or [[Reclutamiento/Líder de Grupo de Reclutadoras|Team Lead]] picks it → the requisition transitions to Yellow (In process)
- If it has been more than 24h without being picked, the system automatically assigns it to the [[Reclutadora]] with the lowest active requisition load. The process is transparent (the [[Manager de Reclutamiento]] does not receive a notification)
- If there is no match in the [[Pool de Colaboradores]], the requisition remains on hold; the Recruitment Flow is always active

### Position Lifecycle
- The position has a start date but no defined end date
- It ends when the [[Hotel/Manager de Área|Area Manager]] or the [[Hotel/Supervisor|Supervisor]] puts the associate on Stand-by (Pink status in the [[Semáforo del Colaborador]])

### Deletion (Purple)
- Cross-cutting status: reached from any status when the requisition is deleted
- Requisition with no positions upon exiting the editor → automatic physical deletion
- The system executes ROUTINE Requisition Journal on every deletion
- When deleting a requisition with positions → each position also transitions to Purple with an individual journal entry

### Automatic Journals
- **ROUTINE Requisition Journal:** records Requisition, Hotel, General Manager / Area Manager, Recruiter, Inspector, Status, Note, Date and time of status
- **ROUTINE Position Journal:** records Requisition number, Position number, Position, Headcount, Start date, End date, Status, Date and time of status

## Blacklist

### Automatic Blacklist
- Triggered by the 3-absence rule
- Status: Black in [[Semáforo del Colaborador]]

### Manual Blacklist
- Triggered by a dispute resolved in favor of the hotel (Red status → [[Inspector]] investigation)
- The [[Inspector]] for the zone decides with independent authority; no validation from the [[Manager de Reclutamiento]] is required

### Permanence of Black Status
- Black is **PERMANENT**: there is no rehabilitation or appeal
- The record is preserved in the system marked as Black
- The associate does not appear in active searches; history is preserved for internal reference

### Mandatory Check
- The [[Reclutadora]] must check the [[Core/Módulos/Blacklist|Blacklist]] before recruiting a candidate, to avoid re-recruiting someone who has been banned

## Work Accident

### Gray Status Activation
- The accident report activates Gray status in [[Semáforo del Colaborador]] from any active status
- **Scenario A:** the Associate reports from the app; the notification reaches the SUP and the assigned zone [[Inspector]] simultaneously
- **Scenario B:** the SUP ([[Hotel/Supervisor|Supervisor]]) reports; the notification reaches the Inspector
- An automatic report number is generated (same pattern as requisition: date/time + homoclave)

### Card Closure
- The [[Inspector]] is always the final person responsible for closing the accident card
- Gray → Dark Green: requires medical clearance + card closure by the Inspector
- The associate becomes available for reassignment after closure

### Accident Journal
- Each status change generates a record with: Report number, Hotel, Associate, Reported by, Status, Note, Date and time of status

## Onboarding and Sales

### Hotel Enablement
- The hotel can only generate requisitions when it reaches Orange Status in the [[Semáforo Onboarding]]
- Before Orange, the hotel is a commercial prospect managed by [[Ventas/Ventas|Sales]]

### Prospect-to-Client Conversion
- Only the [[Ventas/Roles/Business Developer Coordinator|Business Developer Coordinator]] (BDC) can approve the conversion
- **Precondition:** creation of the [[Ventas/Onboarding-Hotel/Conceptos/Usuario del Hotel|Hotel User Account]] in the system
- Upon approval, the [[Ventas/Onboarding-Hotel/Conceptos/Trigger Automático de Conversión|Automatic Conversion Trigger]] fires with parallel actions:
  - System sends welcome email to the hotel
  - System notifies the assigned Business Developer
  - Hotel disappears from the prospect list

### Terms and Conditions Document
- Created at Onboarding Yellow Status by the BD or the BDC
- Negotiated at Onboarding Pink Status
- Contents: Pay rate, Bill rate, Overtime, Holidays, Calendar
- Final validation: [[Ventas/Roles/Business Developer Coordinator|Business Developer Coordinator]] before closing the [[Contrato]]

### Customized Proposal
- Prepared and sent at Onboarding Green Status
- Adjusted/resumed from Onboarding Brown Status when there is stagnation

### Status Reactivation
- Red, Black, and Brown always reactivate toward Light Blue
- Brown is not a terminal status: it is an unblocking bridge operated by the BDC

### Traceability
- Every status change in Onboarding is recorded with date, responsible party, and comment

## Quality Indicator / QA

### Fundamental Principle
- [[QA/QA|QA]] does not execute the operations of any department; it only observes, measures, and provides feedback

### Team Structure
- There are 6 [[QA/Operador de QA|QA Operators]], one per supervised department: Inspection, Hotel, Associate, Sales, Recruitment, and [[Customer Service/Customer Service|Customer Service]]
- Each operator is permanently assigned to a single department

### Indicator Update
- The [[QA/Operador de QA|QA Operator]] proposes the status change based on metrics
- The [[QA/Manager de QA|QA Manager]] validates and approves the update
- Only the QA Manager can formally update each department's [[Indicador de Calidad]]
- Each department has its own independent Indicator; initial status is Green

### Indicator Transitions
- **→ Green:** initial status when QA begins supervising a department
- **Green → Yellow:** when the Operator detects out-of-range metrics or issues unaddressed observations
- **Yellow → Red:** when observations persist without attention or metrics deteriorate significantly
- **Red → Yellow:** when the department begins addressing observations and shows improvement
- **Yellow → Green:** when all observations are resolved and metrics return to parameters

### Escalation
- Department in Red with no improvement after notification → the [[QA/Manager de QA|QA Manager]] escalates to management

### Metrics and KPIs by Department
- Each department has between 5 and 6 concrete KPIs that the [[QA/Operador de QA|QA Operator]] monitors
- Each KPI has defined thresholds (Target / At Risk / Critical) that feed the [[Indicador de Calidad]]
- Full reference: [[QA/Métricas y KPIs por Departamento|Metrics and KPIs by Department]]

## Recruitment and Pool

### Nature of the Flow
- The [[Reclutamiento/Flujo de Reclutamiento|Recruitment Flow]] is continuous: Recruitment is always hiring, whether or not there are open requisitions
- Requisitions without a match may accelerate or prioritize certain positions/zones, but they are not a condition to start the flow

### Requisition Distribution (Self-Pick)
- Authorized requisitions are made available in a shared queue, prioritized by the [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición|Urgency Indicator]]
- [[Reclutadora|Recruiters]] and [[Reclutamiento/Líder de Grupo de Reclutadoras|Team Leads]] freely pick requisitions from the queue
- If a requisition has been in the queue for more than 24 hours without being picked, the system automatically assigns it to the [[Reclutadora]] with the lowest active requisition load. The process is transparent (the [[Manager de Reclutamiento]] does not receive a notification)

### Associate Approval
- The [[Reclutadora]] validates and approves the associate after they complete their app registration
- The Recruiter enables the associate's access to the panels
- An approved associate enters the [[Pool de Colaboradores]] with [[Semáforo del Colaborador]] in White status

### Pool Eligibility
- Only associates who passed the screening and were approved by Recruitment enter the Pool

## Schedule and Timesheet

### Schedule Configuration
- The hotel's week is defined by the contract (week start and end)
- When a requisition is created with a start date within the week, its positions are reflected in the [[Core/Módulos/Schedule|Schedule]] for that week

### Work Day

- The daily shift is **8 hours**
- The work week is 7 days: **5 working + 2 rest**
- Gross weekly total: **40 hours** (8 hrs x 5 days)
- Net payable weekly total: **37.5 hours** (40 hrs - 30 min lunch x 5 shifts)

### Schedule Assignment
- When assigning an associate from the [[Pool de Colaboradores]], they are registered in the hotel's schedule

### Timesheet Dependency
- The [[Timesheet]] is created from the [[Core/Módulos/Schedule|Schedule]]; it cannot exist independently
- If the [[Core/Módulos/Schedule|Schedule]] is modified after the [[Timesheet]] was created, the Timesheet is automatically updated to reflect the changes

### Punching Mechanism
- The associate punches via QR generated by the [[Hotel/Manager General|General Manager]] or the [[Hotel/Manager de Área|Area Manager]]
- Punches are recorded in entry/exit pairs for each period:
  - **Clock In** — shift start
  - **Lunch Out** — leaves for lunch
  - **Lunch In** — returns from lunch
  - **Break Out** — leaves for break
  - **Break In** — returns from break
  - **Clock Out** — shift end
- This tracks the associate's worked time

### Punching Restriction by Associate Status

- Punching is only possible when the associate has an active [[Timesheet]], which requires being enrolled in a hotel's [[Core/Módulos/Schedule|Schedule]]
- Without an active assignment (fixed or temporary) there is no Schedule, without a Schedule there is no Timesheet, and without a Timesheet there is no punching
- Statuses that **do not allow punching**: Pink (Stand-by) and Yellow (Voluntary Available), because neither has an active assignment
- The only path for a resting associate to log hours is the complete route: **Pink → Yellow → Brown**, where the [[Reclutadora]] temporarily assigns them and the corresponding Schedule/Timesheet is generated

### Lunch Deduction

> [!important] This rule applies to **all** associates without exception, every shift.

- The system deducts lunch time from the associate's [[Timesheet]]:
  - **Lunch less than 30 min:** 30 minutes deducted (mandatory minimum)
  - **Lunch more than 30 min:** actual time taken is deducted
  - **No Lunch punch:** 30 minutes auto-deducted
- The lunch deduction directly impacts the payable hours computation in the [[Timesheet]]

### Break Deduction

- Breaks are also deducted from payable time in the [[Timesheet]]
- The deducted time is the actual time recorded with the **Break Out / Break In** pair
- The number and duration of breaks is defined by each hotel

### Payable Hours Formula

- **Net hours** = (Clock Out - Clock In) - Actual lunch - Actual breaks

### Extended Lunch Indicator

- The system automatically identifies associates whose lunch time exceeds 30 minutes
- **Restricted visibility** — internal Oranje roles only:
  - [[Inspector]]
  - [[Inspección/Coordinador|Coordinator]]
  - [[Manager de Reclutamiento]]
- **Not visible to the hotel:** the [[Hotel/Manager General|General Manager]], the [[Hotel/Manager de Área|Area Manager]], and the [[Hotel/Supervisor|Supervisor]] do not have access to this indicator
- **Purpose:** internal supervision tool for detecting patterns and taking operational actions; it is not automatically punitive

### Timesheet Compliance Indicator

- The system automatically calculates a color-coded indicator that compares the associate's actual compliance against the hotel's contractual parameters
- **Input:** [[Core/Módulos/Contrato|Contract]] parameters + [[Timesheet]] data
- **Weekly evaluation:** the structure is Year → Weeks (numbered per calendar and hotel's week start/end)
- **Comparison:** days worked/required, rest days, hours worked/required
- **Mid-week entry:** the system automatically prorates the remaining days of the cycle; days prior to registration are marked in Gray
- Full reference: [[Core/Módulos/Semáforos/Indicador de Cumplimiento del Timesheet|Timesheet Compliance Indicator]]

### Weekly Summary and Associate Payment

- The system automatically generates a [[Contabilidad/Consolidado Semanal del Colaborador|Weekly Summary]] per associate at the end of each week
- The summary aggregates [[Timesheet|Timesheets]] from all hotels where the associate worked that week
- The calculation applies the pay rate from each hotel's [[Core/Módulos/Contrato|Contract]] separately
- Overtime is calculated **per hotel**, according to the policy agreed in each contract
- The pay period is **weekly**
- **Oranje pays the associate**; each hotel pays Oranje according to its bill rate
- The [[Contadora]] reviews and the [[Manager de Contabilidad]] approves the Summary before executing payment
- The overtime threshold is **40 gross weekly hours** per hotel

## Inspection and Zones

### Zone Assignment
- Each hotel belongs to a geographic [[Core/Catálogos/Zonas|zone]]
- Each zone has a corresponding [[Inspector]] assigned by the [[Inspección/Coordinador|Coordinator]]
- The Inspector for the hotel's zone is responsible for following up on any dispute at that hotel

### Inspector Responsibilities
- **Day 1:** verifies the associate's arrival at the property (White → Apple Green transition)
- **Day 3:** delivers the uniform to the associate (→ Light Blue transition)
- **Reports:** investigates disputes (Red status) and resolves toward Black or Dark Green
- **Accidents:** final person responsible for closing the accident card; manages the Gray → Dark Green transition

### Coordinator
- The [[Inspección/Coordinador|Coordinator]] assigns inspectors to geographic zones and supervises their fieldwork

## Error Handling

### Punch Failure
- If the system fails to record a punch, the associate can retry.
- If the failure persists, the system notifies the [[Hotel/Supervisor|Supervisor]] to take manual action.

### ID Collision (homoclave)
- If generating a requisition, position, or report number produces a homoclave collision (duplicate), the system automatically regenerates the homoclave until a unique value is obtained.

### Disconnection During Operation
- If the user loses connection while performing an operation (data entry, form filling, etc.), the operation is automatically saved as a draft.
- The draft can be resumed and completed when the connection is restored.

## Related

- [[Semáforo del Colaborador]]
- [[Semáforo de Requisición]]
- [[Semáforo de Urgencia de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
- [[Semáforo Onboarding]]
- [[Indicador de Calidad]]
- [[Core/Módulos/Semáforos/Indicador de Cumplimiento del Timesheet|Timesheet Compliance Indicator]]
- [[Core/Módulos/Requisicion/Flujo de Requisición|Requisition Flow]]
- [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Work Accident Flow]]
- [[Reclutamiento/Flujo de Reclutamiento|Recruitment Flow]]
- [[Ventas/Onboarding-Hotel/Flujo de Onboarding|Onboarding Flow]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Pool de Colaboradores]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Timesheet]]
- [[Hotel/Manager General|General Manager]]
- [[Hotel/Manager de Área|Area Manager]]
- [[Hotel/Supervisor|Supervisor]]
- [[Inspector]]
- [[Inspección/Coordinador|Coordinator]]
- [[Reclutadora]]
- [[Manager de Reclutamiento]]
- [[QA/QA|QA]]
- [[QA/Manager de QA|QA Manager]]
- [[QA/Operador de QA|QA Operator]]
- [[Ventas/Roles/Business Developer Coordinator|Business Developer Coordinator]]
- [[Ventas/Onboarding-Hotel/Conceptos/Usuario del Hotel|Hotel User Account]]
- [[Ventas/Onboarding-Hotel/Conceptos/Trigger Automático de Conversión|Automatic Conversion Trigger]]
- [[Ventas/Onboarding-Hotel/Conceptos/Documento de Términos y Condiciones|Terms and Conditions Document]]
- [[Core/Catálogos/Zonas|Zones]]
