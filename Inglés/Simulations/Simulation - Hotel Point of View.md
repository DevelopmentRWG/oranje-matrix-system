---
tipo: simulación
perspectiva: hotel
hotel_ficticio: Hotel Riviera Maya Beach Resort
zona: Sureste
jerarquía: extendida
tags:
  - simulación
  - hotel
  - ciclo-completo
aliases:
  - Hotel Simulation
---

# Complete simulation — Hotel Point of View

> [!abstract] Purpose
> This simulation narrates the complete life cycle of a hotel within the Oranje system, from the moment it is identified as a commercial prospect until its daily operation with assigned personnel. All data is fictitious, but every action, status light transition and business rule faithfully respects the vault documentation.

## Simulation characters

| Character | Role | Department |
|---|---|---|
| Carlos Méndez | [[General Manager|General Manager]] (GM) | Hotel Riviera Maya Beach Resort |
| Laura Torres | [[Area Manager|Area Manager]] (GH) | Housekeeping |
| Pedro Ramírez | [[Supervisor|Supervisor]] (SUP) | Housekeeping |
| Sofía Vega | [[Business Developer|Business Developer]] (BD) | Sales — Oranje |
| Ricardo Luna | [[Business Developer Coordinator|Business Developer Coordinator]] (BDC) | Sales — Oranje |
| Ana Martínez | [[Recruiter|Recruiter]] | Recruitment — Oranje |
| Miguel Ochoa | [[Inspector|Inspector]] | Inspection — Oranje (Sureste zone) |
| María López | Collaborator | Housekeeper |
| Juan Hernández | Collaborator | Houseman |
| Elena Cruz | Collaborator | Housekeeper |
| Roberto Díaz | Collaborator (replacement) | Houseman |

---

## Phase 1 — Commercial onboarding

> Reference: [[Onboarding Flow|Onboarding Flow]] · [[Onboarding Status Light|Onboarding Status Light]]

### 1.1 — Hotel identification

Sofía Vega, [[Business Developer|Business Developer]] assigned to the Sureste zone, identifies the **Hotel Riviera Maya Beach Resort** as a hotel with high turnover of housekeeping personnel and potential interest in staffing services.

Sofía creates the hotel profile in the system.

> [!info] Onboarding Status Light
> **Gray** → Hotel identified

### 1.2 — Contact and data collection

Sofía makes a cold visit to the hotel. She meets with Carlos Méndez (GM) and collects the basic data: hotel name, address, main contact, number of rooms, active departments and estimated personnel need.

She records everything in the system profile.

> [!info] Onboarding Status Light
> Gray → **Light Blue** — Contact and data collection

### 1.3 — Proposal sent

Sofía prepares a [[Personalized Proposal|Personalized Proposal]] for the Hotel Riviera Maya: staffing services for the Housekeeping department, with coverage of Housekeepers, Housemen and laundry personnel. It includes a description of services, operating model and preliminary pricing proposal.

She sends the proposal by email to GM Carlos Méndez and follows up.

> [!info] Onboarding Status Light
> Light Blue → **Green** — Proposal sent

### 1.4 — Follow-up and terms

Carlos Méndez responds with interest. Sofía, with the support of Ricardo Luna ([[Business Developer Coordinator|Business Developer Coordinator]]), creates the [[Terms and Conditions Document|Terms and Conditions Document]] with the commercial parameters:

| Parameter | Value |
|---|---|
| Pay rate (Housekeeper) | $180 MXN/hour |
| Pay rate (Houseman) | $160 MXN/hour |
| Bill rate (Housekeeper) | $280 MXN/hour |
| Bill rate (Houseman) | $250 MXN/hour |
| Overtime | 1.5x bill rate |
| Holidays | 2x bill rate |
| Start of week | Monday |
| End of week | Sunday |

> [!info] Onboarding Status Light
> Green → **Yellow** — In follow-up after proposal

### 1.5 — Terms negotiation

Carlos requests adjusting the Houseman bill rate to $240 MXN/hour. Ricardo Luna (BDC) participates directly in the negotiation. After two rounds of adjustment, both parties reach an agreement. The [[Contrato|Contract]] is signed.

> [!info] Onboarding Status Light
> Yellow → **Pink** — Terms negotiation

### 1.6 — Conversion to active client

Ricardo Luna (BDC) approves the conversion of the Hotel Riviera Maya to an active client. Only the BDC has authority for this action.

> [!tip] Automatic system actions — [[Automatic Conversion Trigger|Automatic Conversion Trigger]]
> 1. The [[Hotel User|Hotel User]] is created in the system
> 2. The system sends a welcome email to the hotel
> 3. Sofía Vega (assigned BD) is notified
> 4. The hotel disappears from the prospect list

> [!info] Onboarding Status Light
> Pink → **Orange** — Agreement signed, active client hotel

> [!warning] Business rule
> The hotel can only generate [[Requisition|requisitions]] from this moment on. Before reaching Orange in the [[Onboarding Status Light|Onboarding Status Light]], the hotel is a commercial prospect without operational access.

---

## Phase 2 — First personnel requisition

> Reference: [[Requisition Flow|Requisition Flow]] · [[Requisition Status Light|Requisition Status Light]] · [[Requisition|Requisition]]

### 2.1 — Requisition creation

It is Monday, May 19, 2026. Pedro Ramírez ([[Supervisor|SUP]]) of the Housekeeping department needs personnel. He opens the app and creates a requisition with the following positions:

| # | Position | Quantity | Modality | Start date | Schedule | English |
|---|---|---|---|---|---|---|
| 1 | Housekeeper | 2 | Full time | May 25, 2026 | 07:00–15:00 | Basic |
| 2 | Houseman | 1 | Full time | May 25, 2026 | 07:00–15:00 | Basic |

> [!tip] Automatic system action
> The requisition number is generated: **202605190830A3**
> Format: `Year(4) + Month(2) + Day(2) + Hour(2) + Minutes(2) + Homoclave(2)`

> [!info] Requisition Status Light
> → **Apple Green** — In preparation

> [!info] Requisition Positions Status Light
> Position 1 (Housekeeper ×2): → **Gold** — In preparation
> Position 2 (Houseman ×1): → **Gold** — In preparation

### 2.2 — Authorization

Laura Torres ([[Area Manager|GH]] of Housekeeping) reviews requisition `202605190830A3` in her inbox. She verifies the positions, quantities and dates. Everything is correct. She authorizes the requisition.

> [!warning] Business rule
> Only the [[General Manager|General Manager]] or the [[Area Manager|Area Manager]] can authorize a requisition. If Pedro (SUP) tried to authorize, the system would block with: *"Only the hotel manager can authorize the requisition"*.

> [!tip] Automatic actions upon authorization
> 1. **Requisition** moves to Green (Authorized)
> 2. **Positions** move from Gold to Orange (Authorized)
> 3. **Urgency calculation**: authorization date (May 19, 08:45) vs start date (May 25, 07:00) = ~142 hours → **Strong Green** (Normal, >120h)
> 4. **Assigned inspector**: Miguel Ochoa — automatic according to the hotel's [[Zones|Sureste zone]]
> 5. **Positions reflected** in the [[Schedule|Schedule]] for the week of May 25

> [!info] Requisition Status Light
> Apple Green → **Green** — Authorized

> [!info] Requisition Positions Status Light
> Gold → **Orange** — Authorized

> [!info] Requisition Urgency Status Light
> → **Strong Green** — Normal (142 hours available)

### 2.3 — Self-Pick by Recruitment

Requisition `202605190830A3` appears in the shared inbox of [[Requisition Self-Pick|Requisition Self-Pick]], prioritized by urgency level. Ana Martínez ([[Recruiter|Recruiter]]) sees it and picks it up at 12:30 the same day.

> [!warning] Business rule
> If no recruiter picks up the requisition within 24 hours, the system automatically assigns it to the recruiter with the lowest workload.

> [!info] Requisition Status Light
> Green → **Yellow** — In process

### 2.4 — Coverage

Ana Martínez consults the [[Collaborator Pool|Collaborator Pool]] and searches for candidates that match the requirements: position, compatible geographic zone, availability and modality.

**Search result:**

| Collaborator | Position | Status in status light | Match |
|---|---|---|---|
| María López | Housekeeper | Strong Green (Available) | Yes |
| Elena Cruz | Housekeeper | Strong Green (Available) | Yes |
| Juan Hernández | Houseman | Strong Green (Available) | Yes |

Ana assigns the three collaborators. She registers them in the hotel's [[Schedule|Schedule]] for the week of May 25.

> [!info] Requisition Positions Status Light
> **Position 1** (Housekeeper ×2): Orange → **Green** — 100% covered (2/2)
> **Position 2** (Houseman ×1): Orange → **Green** — 100% covered (1/1)

> [!warning] Business rule
> Requisition = Light Blue **only if** ALL positions are in Green. If any position closes in Yellow or Red, the requisition closes in Red.

> [!info] Requisition Status Light
> Yellow → **Light Blue** — Fully covered

> [!info] Collaborator Status Light
> María López: Strong Green → **White** (Pre-assignment)
> Elena Cruz: Strong Green → **White** (Pre-assignment)
> Juan Hernández: Strong Green → **White** (Pre-assignment)

---

## Phase 3 — Day 1: collaborators' arrival

> Reference: [[Inspection Rules|Inspection Rules]] · [[Collaborator Status Light|Collaborator Status Light]] · [[Inspector|Inspector]]

### 3.1 — Arrival verification

It is Sunday, May 25, 2026, 06:45 AM. María López, Juan Hernández and Elena Cruz arrive at the Hotel Riviera Maya Beach Resort.

Miguel Ochoa ([[Inspector|Inspector]] of the Sureste zone) shows up at the property. He verifies in person the arrival of each collaborator: confirms identity, records the arrival time and validates that they are in the correct place.

> [!info] Collaborator Status Light
> María López: White → **Apple Green** (Day 1-2)
> Juan Hernández: White → **Apple Green** (Day 1-2)
> Elena Cruz: White → **Apple Green** (Day 1-2)

### 3.2 — First clock-in

Laura Torres ([[Area Manager|GH]]) generates the clock-in QR code from the app. The three collaborators clock in their first day of work.

María López's clock-in record — Day 1 (May 25):

| Event | Time |
|---|---|
| Clock-in | 07:00 |
| Lunch out | 11:30 |
| Lunch in | 12:00 |
| Break out | 14:00 |
| Break in | 14:15 |
| Clock-out | 15:00 |

> [!warning] Business rule — Lunch deduction
> Lunch taken: 30 min (12:00 − 11:30). Since it is exactly 30 min (mandatory minimum), 30 min is deducted. If it had been less than 30 min, 30 min would be deducted anyway. If it had been more, the actual time would be deducted.

> [!tip] Automatic system calculation — [[Timesheet|Timesheet]]
> - Gross hours: 15:00 − 07:00 = 8:00
> - Lunch deduction: 0:30
> - Break deduction: 0:15
> - **Net payable hours: 7:15**

---

## Phase 4 — Day 3: uniform delivery

> Reference: [[Inspection Rules|Inspection Rules]] · [[Inspector|Inspector]]

### 4.1 — Uniform delivery

It is Tuesday, May 27, 2026. Miguel Ochoa ([[Inspector|Inspector]]) returns to the Hotel Riviera Maya to deliver the Oranje uniforms to the three collaborators.

Miguel personally delivers the uniform to María López, Juan Hernández and Elena Cruz. He records the delivery in the app.

> [!info] Collaborator Status Light
> María López: Apple Green → **Light Blue** (Day 3+)
> Juan Hernández: Apple Green → **Light Blue** (Day 3+)
> Elena Cruz: Apple Green → **Light Blue** (Day 3+)

From this moment on, the three collaborators operate normally: they clock in daily, their [[Timesheet|Timesheet]] is generated from the [[Schedule|Schedule]], and their work is recorded in the system.

---

## Phase 5 — Normal weekly operation

> Reference: [[Timesheet|Timesheet]] · [[Schedule|Schedule]] · [[Timesheet Compliance Indicator|Timesheet Compliance Indicator]]

### 5.1 — Full week of work

The first full week passes without incident. The three collaborators work 5 shifts (Monday to Friday) with 2 days of rest (Saturday and Sunday).

**Summary of María López's [[Timesheet|Timesheet]] — Week of May 26 to June 1:**

| Day | Clock-in | Clock-out | Lunch | Break | Net hours |
|---|---|---|---|---|---|
| Mon 26 | 07:00 | 15:00 | 30 min | 15 min | 7:15 |
| Tue 27 | 07:00 | 15:00 | 30 min | 15 min | 7:15 |
| Wed 28 | 07:00 | 15:00 | 35 min | 15 min | 7:10 |
| Thu 29 | 07:00 | 15:00 | 30 min | 15 min | 7:15 |
| Fri 30 | 07:00 | 15:00 | 30 min | 15 min | 7:15 |
| **Total** | | | | | **36:10** |

> [!warning] Rule — Weekly shift
> Daily shift: 8 gross hours. Work week: 7 days (5 work + 2 rest). Gross weekly total: 40 hours. Expected net payable weekly total: 37.5 hours (40 hrs − 30 min lunch × 5 shifts, not counting breaks). María records 36:10 net hours due to the daily 15 min breaks.

### 5.2 — Extended Lunch Indicator

On Wednesday 28, Juan Hernández takes a 45-minute lunch instead of the regulatory 30.

> [!tip] Automatic system action
> The **Extended Lunch Indicator** is activated for Juan Hernández on Wednesday 28. The actual time (45 min) is deducted instead of the 30 min minimum.

> [!warning] Visibility rule
> The Extended Lunch Indicator is visible **only** to: Miguel Ochoa ([[Inspector|Inspector]]), the [[Coordinator|Coordinator]] and the [[Recruitment Manager|Recruitment Manager]].
> **It is not visible** to: Carlos Méndez (GM), Laura Torres (GH) or Pedro Ramírez (SUP).
> It is not automatically punitive — it is an internal supervision tool of Oranje.

### 5.3 — Transition to Fixed

Upon completing 7 days of continuous operation, the system automatically transitions the three collaborators to the Orange (Fixed) state.

> [!info] Collaborator Status Light
> María López: Light Blue → **Orange** (Fixed)
> Juan Hernández: Light Blue → **Orange** (Fixed)
> Elena Cruz: Light Blue → **Orange** (Fixed)

---

## Phase 6 — Incident: collaborator report

> Reference: [[Collaborator Status Light|Collaborator Status Light]] · [[Inspection Rules|Inspection Rules]] · [[Blacklist|Blacklist]]

### 6.1 — Report from the hotel

It is Thursday, June 5, 2026. Juan Hernández has arrived late three days in the week and his performance has dropped significantly. Pedro Ramírez ([[Supervisor|SUP]]) decides to report him from the app.

> [!info] Collaborator Status Light
> Juan Hernández: Orange → **Red** (Reported)

> [!warning] Business rule
> The Red state can be activated by: [[General Manager|General Manager]], [[Area Manager|Area Manager]] or [[Supervisor|Supervisor]]. The accumulation of 3 absences does **not** go through Red; it goes directly to Black (automatic [[Blacklist|Blacklist]]).

### 6.2 — Inspector investigation

Miguel Ochoa ([[Inspector|Inspector]]) receives the report notification. He shows up at the hotel, interviews Pedro (SUP) and Laura (GH), reviews Juan's clock-in records and documents the situation.

After his investigation, Miguel determines that the dispute **favors the hotel**: the late arrivals are documented in the [[Timesheet|Timesheet]] and there is no valid justification from the collaborator.

> [!warning] Rule — Inspector authority
> The [[Inspector|Inspector]] has their own authority to decide the outcome:
> - Dispute in favor of the hotel → **Black** ([[Blacklist|Blacklist]])
> - Dispute in favor of the collaborator → **Strong Green** (reinstated)

> [!info] Collaborator Status Light
> Juan Hernández: Red → **Black** (Blacklist)

Juan Hernández is **permanently banned** from the Oranje system. He cannot be assigned to any hotel.

### 6.3 — Replacement requisition

Laura Torres ([[Area Manager|GH]]) needs to fill the vacancy left by Juan. She creates a new requisition from the app:

| # | Position | Quantity | Modality | Start date | Schedule | English |
|---|---|---|---|---|---|---|
| 1 | Houseman | 1 | Full time | June 7, 2026 | 07:00–15:00 | Basic |

> [!tip] Automatic system action
> Generated requisition number: **202606050915B7**

Laura herself authorizes the requisition (as GH she has the authority to do so).

> [!tip] Automatic actions upon authorization
> 1. Requisition → **Green** (Authorized)
> 2. Position → **Orange** (Authorized)
> 3. Urgency: authorization date (June 5, 09:15) vs start date (June 7, 07:00) = ~46 hours → **Red** (Urgent, <72h)
> 4. Inspector Miguel Ochoa assigned automatically

> [!info] Requisition Urgency Status Light
> → **Red** — Urgent (<72 hours)

### 6.4 — Urgent coverage

The urgent requisition appears in the [[Requisition Self-Pick|Requisition Self-Pick]] inbox highlighted by its Red urgency level. Ana Martínez ([[Recruiter|Recruiter]]) picks it up immediately.

Ana searches the [[Collaborator Pool|Collaborator Pool]] and finds Roberto Díaz (Houseman, Strong Green state — Available, Sureste zone). She assigns him to the position.

> [!info] Requisition Positions Status Light
> Position 1 (Houseman ×1): Orange → **Green** — 100% covered

> [!info] Requisition Status Light
> Yellow → **Light Blue** — Fully covered

Roberto Díaz starts the standard process: arrival verified by Miguel (Inspector) on Day 1, uniform delivery on Day 3, and transition to Orange (Fixed) after Day 7.

---

## Phase 7 — Contingency: workplace accident

> Reference: [[Workplace Accident Flow|Workplace Accident Flow]] · [[Workplace Accident|Workplace Accident]] · [[Inspection Rules|Inspection Rules]]

### 7.1 — Accident report (Scenario A)

It is Wednesday, June 18, 2026, 10:20 AM. María López suffers a fall in the hotel's laundry area while moving a cart of clothes. She injures her right ankle.

María opens the Oranje app and generates an accident report from her phone.

> [!tip] Automatic system actions
> 1. A **workplace accident card** is generated with an automatic number
> 2. María López transitions to the **Gray** state (Injured) in the [[Collaborator Status Light|Collaborator Status Light]]
> 3. The signal reaches **simultaneously** Pedro Ramírez (SUP) and Miguel Ochoa (Inspector of the Sureste zone)

> [!info] Collaborator Status Light
> María López: Orange → **Gray** (Injured)

> [!warning] Protection rule
> While María is in the Gray state, her absences do **not** count toward the rule of 3 absences → [[Blacklist|Blacklist]]. The Gray state protects the injured collaborator.

### 7.2 — In-person information from the Supervisor

Pedro Ramírez ([[Supervisor|SUP]]) receives the notification and physically goes to the laundry area. He captures the in-person information on the accident card:

| Field | Captured information |
|---|---|
| Exact location | Laundry area, aisle between industrial washers and ironing station |
| Circumstances | The collaborator slipped on a wet floor while moving a cart of dirty clothes |
| Witnesses | Elena Cruz (shift coworker) |
| Immediate care | Ice was applied to the ankle, the collaborator was seated in the rest area |

### 7.3 — Medical follow-up by the Inspector

Miguel Ochoa ([[Inspector|Inspector]]) receives the notification in the app and travels to the hotel. He assesses the situation and decides to transfer María to the nearest medical center.

Miguel complements the accident card with the medical information:

| Field | Captured information |
|---|---|
| Transfer | Centro Médico del Sureste, arrival 11:45 AM |
| Diagnosis | Grade I ankle sprain |
| Days of disability | 5 days (from June 18 to 22) |
| Medical observations | Complete rest, no weight bearing, follow-up review on the 23rd |

### 7.4 — Card closure

On Monday, June 23, María López is medically discharged. Miguel Ochoa ([[Inspector|Inspector]]) closes the accident card in the system.

> [!warning] Business rule
> The [[Inspector|Inspector]] is **always** the final party responsible for closing the accident card. Without exception. Closure requires documented medical discharge.

> [!info] Collaborator Status Light
> María López: Gray → **Strong Green** (Available)

María becomes available in the [[Collaborator Pool|Collaborator Pool]] to be reassigned. Ana Martínez ([[Recruiter|Recruiter]]) reassigns her to the Hotel Riviera Maya to continue her Housekeeper position.

---

## Phase 8 — Stand-by

> Reference: [[Collaborator Status Light|Collaborator Status Light]] · [[Hotel Rules|Hotel Rules]]

### 8.1 — Stand-by activation

It is July 2026. The low season significantly reduces the hotel's occupancy. Laura Torres ([[Area Manager|GH]]) decides that she does not need both Housekeepers at the same time.

Laura puts Elena Cruz on **Stand-by** from the app.

> [!info] Collaborator Status Light
> Elena Cruz: Orange → **Pink** (Stand-by)

> [!warning] Stand-by Rules
> - Elena does **not have** a [[Schedule|Schedule]] or [[Timesheet|Timesheet]] while she is in Pink
> - Elena **cannot** clock in
> - **No defined end date** — the state is maintained until any hotel role changes it
> - The action can be executed by: [[General Manager|General Manager]], [[Area Manager|Area Manager]] or [[Supervisor|Supervisor]]

### 8.2 — Reactivation

Three weeks later, the hotel's occupancy rebounds. Laura Torres reactivates Elena Cruz from the app, changing her state back to operational.

> [!info] Collaborator Status Light
> Elena Cruz: Pink → operational state

Elena reappears in the hotel's [[Schedule|Schedule]] and can clock in again. Her [[Timesheet|Timesheet]] is generated starting from the reactivation week.

---

## Phase 9 — Weekly billing

> Reference: [[Hotel Invoicing|Hotel Billing]] · [[Payroll Flow|Payroll Flow]] · [[Contrato|Contract]]

### 9.1 — Automatic invoice generation

At the close of the week of May 26 to June 1, the system automatically generates the invoice for the Hotel Riviera Maya Beach Resort.

**Invoice — Week of May 26 to June 1, 2026**

| Collaborator | Position | Regular hours | Authorized OT hours | Bill rate | Subtotal |
|---|---|---|---|---|---|
| María López | Housekeeper | 36.17 | 0 | $280/hr | $10,127.60 |
| Juan Hernández | Houseman | 35.75 | 0 | $240/hr | $8,580.00 |
| Elena Cruz | Housekeeper | 36.17 | 0 | $280/hr | $10,127.60 |

| Concept | Amount |
|---|---|
| Services subtotal | $28,835.20 |
| Credits | $0.00 |
| **Total to charge** | **$28,835.20** |

> [!warning] Billing rules
> - The **bill rate** of the [[Contrato|Contract]] is used exclusively. The pay rate (what Oranje pays the collaborator) is never reflected in the invoice.
> - Only **overtime authorized** by the hotel is billed. Unauthorized overtime hours are not included.
> - If the week crossed a month change and the contract indicates "Invoice split by month: yes", the system would generate two separate invoices.

> [!tip] Automatic system action
> The invoice is generated with a unique folio assigned by Oranje. It is sent to the hotel as a fiscal document.

---

## Phase 10 — Quality supervision (QA)

> Reference: [[Quality Indicator|Quality Indicator]] · [[QA Operator|QA Operator]] · [[QA Manager|QA Manager]]

### 10.1 — Continuous monitoring

A [[QA Operator|QA Operator]] is permanently assigned to the Hotel department. This operator continuously monitors the quality indicators of the staffing service that Oranje provides to the Hotel Riviera Maya and to all client hotels.

The Hotel department's [[Quality Indicator|Quality Indicator]] remains in **Green** (Optimal quality) during the first weeks of operation.

> [!warning] Escalation rule
> If the [[Quality Indicator|Quality Indicator]] reaches the **Red** state (Critical quality) without improvement after the notification, the [[QA Manager|QA Manager]] escalates to management. QA does not execute the Hotel's operation; it only observes, measures and gives feedback.

---

## Summary of status light transitions

### [[Onboarding Status Light|Onboarding Status Light]]
```
Gray → Light Blue → Green → Yellow → Pink → Orange (active client)
```

### [[Requisition Status Light|Requisition Status Light]] (Requisition 202605190830A3)
```
Apple Green → Green → Yellow → Light Blue (fully covered)
```

### [[Requisition Positions Status Light|Requisition Positions Status Light]]
```
Gold → Orange → Green (100% covered)
```

### [[Collaborator Status Light|Collaborator Status Light]] — María López
```
Strong Green → White → Apple Green → Light Blue → Orange → Gray → Strong Green
```

### [[Collaborator Status Light|Collaborator Status Light]] — Juan Hernández
```
Strong Green → White → Apple Green → Light Blue → Orange → Red → Black (Blacklist)
```

### [[Collaborator Status Light|Collaborator Status Light]] — Elena Cruz
```
Strong Green → White → Apple Green → Light Blue → Orange → Pink (Stand-by) → reactivated
```

---

## Referenced modules and concepts

| Module | Reference |
|---|---|
| Hotel as client | [[Hotel|Hotel]] · [[Hotel Rules|Hotel Rules]] |
| Hotel roles | [[General Manager|General Manager]] · [[Area Manager|Area Manager]] · [[Supervisor|Supervisor]] |
| Commercial onboarding | [[Onboarding Flow|Onboarding Flow]] · [[Onboarding Status Light|Onboarding Status Light]] · [[Personalized Proposal|Personalized Proposal]] · [[Terms and Conditions Document|Terms and Conditions Document]] · [[Contrato|Contract]] |
| Requisitions | [[Requisition|Requisition]] · [[Requisition Flow|Requisition Flow]] · [[Requisition Status Light|Requisition Status Light]] · [[Requisition Positions Status Light|Requisition Positions Status Light]] · [[Requisition Urgency Status Light|Requisition Urgency Status Light]] |
| Personnel assignment | [[Collaborator Pool|Collaborator Pool]] · [[Recruiter|Recruiter]] · [[Requisition Self-Pick|Requisition Self-Pick]] |
| Daily operation | [[Schedule|Schedule]] · [[Timesheet|Timesheet]] · [[Collaborator Status Light|Collaborator Status Light]] |
| Inspection | [[Inspector|Inspector]] · [[Coordinator|Coordinator]] · [[Inspection Rules|Inspection Rules]] |
| Contingencies | [[Workplace Accident|Workplace Accident]] · [[Workplace Accident Flow|Workplace Accident Flow]] · [[Blacklist|Blacklist]] |
| Billing | [[Hotel Invoicing|Hotel Billing]] · [[Payroll Flow|Payroll Flow]] |
| Quality | [[Quality Indicator|Quality Indicator]] · [[Timesheet Compliance Indicator|Timesheet Compliance Indicator]] · [[QA Operator|QA Operator]] · [[QA Manager|QA Manager]] |

---

## Related simulations

- [[Simulation - Sales Point of View|Simulation - Sales Point of View]] — Details the commercial onboarding process from the perspective of the BD and BDC up to the conversion of the hotel to an active client.
- [[Simulation - Inspection Point of View|Simulation - Inspection Point of View]] — Shows the Inspector's field operation: Day 1 and Day 3 verification, reports and accidents from their perspective.
- [[Simulation - Recruitment Point of View|Simulation - Recruitment Point of View]] — Covers the recruitment and personnel assignment process that the hotel requests through requisitions.
- [[Simulation - Collaborator Life Cycle|Simulation - Collaborator Life Cycle]] — Narrates the complete experience of the collaborator assigned to the hotel, including states and transitions that affect daily operation.
