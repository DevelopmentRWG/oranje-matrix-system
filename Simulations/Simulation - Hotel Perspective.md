---
type: simulation
perspective: hotel
fictional_hotel: Hotel Riviera Maya Beach Resort
zone: Southeast
hierarchy: extended
tags:
  - simulation
  - hotel
  - full-cycle
aliases:
  - Hotel Simulation
---

# Full Simulation — Hotel Perspective

> [!abstract] Purpose
> This simulation narrates the complete lifecycle of a hotel within the Oranje system, from the moment it is identified as a commercial prospect through its daily operation with assigned staff. All data is fictional, but every action, status indicator transition, and business rule faithfully reflects the vault documentation.

## Simulation Characters

| Character | Role | Department |
|---|---|---|
| Carlos Méndez | [[General Manager]] (GM) | Hotel Riviera Maya Beach Resort |
| Laura Torres | [[Area Manager]] (GH) | Housekeeping |
| Pedro Ramírez | [[Supervisor]] (SUP) | Housekeeping |
| Sofía Vega | [[Business Developer]] (BD) | Sales — Oranje |
| Ricardo Luna | [[Business Developer Coordinator]] (BDC) | Sales — Oranje |
| Ana Martínez | [[Recruiter]] | Recruitment — Oranje |
| Miguel Ochoa | [[Inspector]] | Inspection — Oranje (Southeast zone) |
| María López | Associate | Housekeeper |
| Juan Hernández | Associate | Houseman |
| Elena Cruz | Associate | Housekeeper |
| Roberto Díaz | Associate (replacement) | Houseman |

---

## Phase 1 — Commercial Onboarding

> Reference: [[Onboarding Flow]] · [[Onboarding Status Indicator]]

### 1.1 — Hotel identification

Sofía Vega, [[Business Developer]] assigned to the Southeast zone, identifies **Hotel Riviera Maya Beach Resort** as a hotel with high housekeeping staff turnover and potential interest in staffing services.

Sofía creates the hotel profile in the system.

> [!info] Onboarding Status Indicator
> **Gray** → Hotel identified

### 1.2 — Contact and data collection

Sofía makes a cold visit to the hotel. She meets with Carlos Méndez (GM) and collects basic data: hotel name, address, main contact, number of rooms, active departments, and estimated staffing needs.

She records everything in the system profile.

> [!info] Onboarding Status Indicator
> Gray → **Light Blue** — Contact and data collection

### 1.3 — Proposal sent

Sofía prepares a [[Customized Proposal]] for Hotel Riviera Maya: staffing services for the Housekeeping department, covering Housekeepers, Housemen, and laundry staff. It includes a service description, operating model, and preliminary pricing proposal.

She sends the proposal by email to GM Carlos Méndez and follows up.

> [!info] Onboarding Status Indicator
> Light Blue → **Green** — Proposal sent

### 1.4 — Follow-up and terms

Carlos Méndez responds with interest. Sofía, with support from Ricardo Luna ([[Business Developer Coordinator]]), creates the [[Terms and Conditions Document]] with the commercial parameters:

| Parameter | Value |
|---|---|
| Pay rate (Housekeeper) | $180 MXN/hr |
| Pay rate (Houseman) | $160 MXN/hr |
| Bill rate (Housekeeper) | $280 MXN/hr |
| Bill rate (Houseman) | $250 MXN/hr |
| Overtime | 1.5× bill rate |
| Holidays | 2× bill rate |
| Week start | Monday |
| Week end | Sunday |

> [!info] Onboarding Status Indicator
> Green → **Yellow** — In follow-up after proposal

### 1.5 — Terms negotiation

Carlos requests an adjustment to the Houseman bill rate to $240 MXN/hr. Ricardo Luna (BDC) participates directly in the negotiation. After two rounds of adjustment, both parties reach an agreement. The [[Contract]] is signed.

> [!info] Onboarding Status Indicator
> Yellow → **Pink** — Terms negotiation

### 1.6 — Conversion to active client

Ricardo Luna (BDC) approves the conversion of Hotel Riviera Maya to active client. Only the BDC has authority for this action.

> [!tip] Automatic system actions — [[Automatic Conversion Trigger]]
> 1. The [[Hotel User]] is created in the system
> 2. The system sends a welcome email to the hotel
> 3. Sofía Vega (assigned BD) is notified
> 4. The hotel disappears from the prospect list

> [!info] Onboarding Status Indicator
> Pink → **Orange** — Agreement signed, hotel is an active client

> [!warning] Business Rule
> The hotel can only generate [[Requisition|requisitions]] from this point on. Before reaching Orange in the [[Onboarding Status Indicator]], the hotel is a commercial prospect with no operational access.

---

## Phase 2 — First Staffing Requisition

> Reference: [[Requisition Flow]] · [[Requisition Status Indicator]] · [[Requisition]]

### 2.1 — Requisition creation

It is Monday May 19, 2026. Pedro Ramírez ([[Supervisor|SUP]]) from the Housekeeping department needs staff. He opens the app and creates a requisition with the following positions:

| # | Position | Quantity | Modality | Start date | Schedule | English |
|---|---|---|---|---|---|---|
| 1 | Housekeeper | 2 | Full time | May 25, 2026 | 07:00–15:00 | Basic |
| 2 | Houseman | 1 | Full time | May 25, 2026 | 07:00–15:00 | Basic |

> [!tip] Automatic system action
> Requisition number generated: **202605190830A3**
> Format: `Year(4) + Month(2) + Day(2) + Hour(2) + Minutes(2) + Homoclave(2)`

> [!info] Requisition Status Indicator
> → **Apple Green** — In preparation

> [!info] Position Status Indicator
> Position 1 (Housekeeper ×2): → **Gold** — In preparation
> Position 2 (Houseman ×1): → **Gold** — In preparation

### 2.2 — Authorization

Laura Torres ([[Area Manager|GH]] of Housekeeping) reviews requisition `202605190830A3` in her inbox. She verifies positions, quantities, and dates. Everything is correct. She authorizes the requisition.

> [!warning] Business Rule
> Only the [[General Manager]] or the [[Area Manager]] can authorize a requisition. If Pedro (SUP) attempted to authorize it, the system would block with: *"Only the hotel manager can authorize the requisition."*

> [!tip] Automatic actions on authorization
> 1. **Requisition** moves to Green (Authorized)
> 2. **Positions** move from Gold to Orange (Authorized)
> 3. **Urgency calculation**: authorization date (May 19 08:45) vs. start date (May 25 07:00) = ~142 hours → **Dark Green** (Normal, >120h)
> 4. **Inspector assigned**: Miguel Ochoa — automatically based on the hotel's [[Zones|Southeast zone]]
> 5. **Positions reflected** in the [[Schedule]] for the week of May 25

> [!info] Requisition Status Indicator
> Apple Green → **Green** — Authorized

> [!info] Position Status Indicator
> Gold → **Orange** — Authorized

> [!info] Urgency Status Indicator
> → **Dark Green** — Normal (142 hours available)

### 2.3 — Self-Pick by Recruitment

Requisition `202605190830A3` appears in the shared [[Self-Pick]] queue, prioritized by urgency level. Ana Martínez ([[Recruiter]]) sees it and picks it up at 12:30 the same day.

> [!warning] Business Rule
> If no recruiter picks the requisition within 24 hours, the system automatically assigns it to the recruiter with the lowest workload.

> [!info] Requisition Status Indicator
> Green → **Yellow** — In process

### 2.4 — Coverage

Ana Martínez checks the [[Associate Pool]] and searches for candidates that match the requirements: position, compatible geographic zone, availability, and modality.

**Search results:**

| Associate | Position | Status Indicator | Match |
|---|---|---|---|
| María López | Housekeeper | Dark Green (Available) | Yes |
| Elena Cruz | Housekeeper | Dark Green (Available) | Yes |
| Juan Hernández | Houseman | Dark Green (Available) | Yes |

Ana assigns all three associates. She registers them in the hotel's [[Schedule]] for the week of May 25.

> [!info] Position Status Indicator
> **Position 1** (Housekeeper ×2): Orange → **Green** — 100% covered (2/2)
> **Position 2** (Houseman ×1): Orange → **Green** — 100% covered (1/1)

> [!warning] Business Rule
> Requisition = Light Blue **only if** ALL positions are Green. If any position closes in Yellow or Red, the requisition closes in Red.

> [!info] Requisition Status Indicator
> Yellow → **Light Blue** — Fully covered

> [!info] Associate Status Indicator
> María López: Dark Green → **White** (Pre-assignment)
> Elena Cruz: Dark Green → **White** (Pre-assignment)
> Juan Hernández: Dark Green → **White** (Pre-assignment)

---

## Phase 3 — Day 1: Associate Arrival

> Reference: [[Inspection Rules]] · [[Associate Status Indicator]] · [[Inspector]]

### 3.1 — Arrival verification

It is Sunday May 25, 2026, 06:45 AM. María López, Juan Hernández, and Elena Cruz arrive at Hotel Riviera Maya Beach Resort.

Miguel Ochoa ([[Inspector]] for the Southeast zone) arrives at the property. He verifies the arrival of each associate in person: confirms identity, records arrival time, and validates that they are at the correct location.

> [!info] Associate Status Indicator
> María López: White → **Apple Green** (Day 1-2)
> Juan Hernández: White → **Apple Green** (Day 1-2)
> Elena Cruz: White → **Apple Green** (Day 1-2)

### 3.2 — First clock-in

Laura Torres ([[Area Manager|GH]]) generates the punch QR code from the app. The three associates clock in for their first day of work.

María López punch record — Day 1 (May 25):

| Event | Time |
|---|---|
| Clock In | 07:00 |
| Lunch Out | 11:30 |
| Lunch In | 12:00 |
| Break Out | 14:00 |
| Break In | 14:15 |
| Clock Out | 15:00 |

> [!warning] Business Rule — Lunch deduction
> Lunch taken: 30 min (12:00 − 11:30). Since it is exactly 30 min (mandatory minimum), 30 min are deducted. If it had been less than 30 min, 30 min would be deducted anyway. If it had been more, the actual time would be deducted.

> [!tip] Automatic system calculation — [[Timesheet]]
> - Gross hours: 15:00 − 07:00 = 8:00
> - Lunch deduction: 0:30
> - Break deduction: 0:15
> - **Net payable hours: 7:15**

---

## Phase 4 — Day 3: Uniform Delivery

> Reference: [[Inspection Rules]] · [[Inspector]]

### 4.1 — Uniform delivery

It is Tuesday May 27, 2026. Miguel Ochoa ([[Inspector]]) returns to Hotel Riviera Maya to deliver the Oranje uniforms to the three associates.

Miguel personally delivers the uniform to María López, Juan Hernández, and Elena Cruz. He records the delivery in the app.

> [!info] Associate Status Indicator
> María López: Apple Green → **Light Blue** (Day 3+)
> Juan Hernández: Apple Green → **Light Blue** (Day 3+)
> Elena Cruz: Apple Green → **Light Blue** (Day 3+)

From this point on, the three associates operate normally: they clock in daily, their [[Timesheet]] is generated from the [[Schedule]], and their work is recorded in the system.

---

## Phase 5 — Normal Weekly Operations

> Reference: [[Timesheet]] · [[Schedule]] · [[Timesheet Compliance Indicator]]

### 5.1 — Full work week

The first full week passes without incidents. The three associates work 5 shifts (Monday through Friday) with 2 rest days (Saturday and Sunday).

**[[Timesheet]] summary for María López — Week of May 26 to June 1:**

| Day | Clock In | Clock Out | Lunch | Break | Net hours |
|---|---|---|---|---|---|
| Mon 26 | 07:00 | 15:00 | 30 min | 15 min | 7:15 |
| Tue 27 | 07:00 | 15:00 | 30 min | 15 min | 7:15 |
| Wed 28 | 07:00 | 15:00 | 35 min | 15 min | 7:10 |
| Thu 29 | 07:00 | 15:00 | 30 min | 15 min | 7:15 |
| Fri 30 | 07:00 | 15:00 | 30 min | 15 min | 7:15 |
| **Total** | | | | | **36:10** |

> [!warning] Rule — Weekly schedule
> Daily shift: 8 gross hours. Work week: 7 days (5 work + 2 rest). Weekly gross total: 40 hours. Expected weekly net payable total: 37.5 hours (40 hrs − 30 min lunch × 5 shifts, not counting breaks). María records 36:10 net hours due to the 15-min daily breaks.

### 5.2 — Extended Lunch Indicator

On Wednesday the 28th, Juan Hernández takes a 45-minute lunch instead of the standard 30 minutes.

> [!tip] Automatic system action
> The **Extended Lunch Indicator** is activated for Juan Hernández on Wednesday the 28th. The actual time (45 min) is deducted instead of the 30-min minimum.

> [!warning] Visibility rule
> The Extended Lunch Indicator is visible **only** to: Miguel Ochoa ([[Inspector]]), the [[Coordinator]], and the [[Recruitment Manager]].
> **Not visible** to: Carlos Méndez (GM), Laura Torres (GH), or Pedro Ramírez (SUP).
> It is not automatically punitive — it is an internal Oranje supervision tool.

### 5.3 — Transition to Fixed

Upon completing 7 days of continuous operation, the system automatically transitions all three associates to Orange (Fixed) status.

> [!info] Associate Status Indicator
> María López: Light Blue → **Orange** (Fixed)
> Juan Hernández: Light Blue → **Orange** (Fixed)
> Elena Cruz: Light Blue → **Orange** (Fixed)

---

## Phase 6 — Incident: Associate Report

> Reference: [[Associate Status Indicator]] · [[Inspection Rules]] · [[Blacklist]]

### 6.1 — Report by the hotel

It is Thursday June 5, 2026. Juan Hernández has arrived late three days this week and his performance has dropped significantly. Pedro Ramírez ([[Supervisor|SUP]]) decides to report him through the app.

> [!info] Associate Status Indicator
> Juan Hernández: Orange → **Red** (Reported)

> [!warning] Business Rule
> Red status can be activated by: [[General Manager]], [[Area Manager]], or [[Supervisor]]. Accumulation of 3 absences does **not** go through Red; it goes directly to Black (automatic [[Blacklist]]).

### 6.2 — Inspector investigation

Miguel Ochoa ([[Inspector]]) receives the report notification. He arrives at the hotel, interviews Pedro (SUP) and Laura (GH), reviews Juan's punch records, and documents the situation.

After his investigation, Miguel determines that the dispute **favors the hotel**: the late arrivals are documented in the [[Timesheet]] and there is no valid justification from the associate.

> [!warning] Rule — Inspector authority
> The [[Inspector]] has autonomous authority to decide the outcome:
> - Dispute in favor of the hotel → **Black** ([[Blacklist]])
> - Dispute in favor of the associate → **Dark Green** (reinstated)

> [!info] Associate Status Indicator
> Juan Hernández: Red → **Black** (Blacklist)

Juan Hernández is **permanently banned** from the Oranje system. He cannot be assigned to any hotel.

### 6.3 — Replacement requisition

Laura Torres ([[Area Manager|GH]]) needs to fill the vacancy left by Juan. She creates a new requisition from the app:

| # | Position | Quantity | Modality | Start date | Schedule | English |
|---|---|---|---|---|---|---|
| 1 | Houseman | 1 | Full time | June 7, 2026 | 07:00–15:00 | Basic |

> [!tip] Automatic system action
> Requisition number generated: **202606050915B7**

Laura herself authorizes the requisition (as GH she has the authority to do so).

> [!tip] Automatic actions on authorization
> 1. Requisition → **Green** (Authorized)
> 2. Position → **Orange** (Authorized)
> 3. Urgency: authorization date (June 5 09:15) vs. start date (June 7 07:00) = ~46 hours → **Red** (Urgent, <72h)
> 4. Inspector Miguel Ochoa automatically assigned

> [!info] Urgency Status Indicator
> → **Red** — Urgent (<72 hours)

### 6.4 — Urgent coverage

The urgent requisition appears in the [[Self-Pick]] queue highlighted by its Red urgency level. Ana Martínez ([[Recruiter]]) picks it up immediately.

Ana searches the [[Associate Pool]] and finds Roberto Díaz (Houseman, Dark Green status — Available, Southeast zone). She assigns him to the position.

> [!info] Position Status Indicator
> Position 1 (Houseman ×1): Orange → **Green** — 100% covered

> [!info] Requisition Status Indicator
> Yellow → **Light Blue** — Fully covered

Roberto Díaz starts the standard process: arrival verified by Miguel (Inspector) on Day 1, uniform delivery on Day 3, and transition to Orange (Fixed) after Day 7.

---

## Phase 7 — Contingency: Workplace Accident

> Reference: [[Work Accident Flow]] · [[Work Accident]] · [[Inspection Rules]]

### 7.1 — Accident report (Scenario A)

It is Wednesday June 18, 2026, 10:20 AM. María López suffers a fall in the hotel's laundry area while transporting a linen cart. She injures her right ankle.

María opens the Oranje app and generates an accident report from her phone.

> [!tip] Automatic system actions
> 1. A **workplace accident card** is generated with an automatic number
> 2. María López transitions to **Gray** (Injured) in the [[Associate Status Indicator]]
> 3. The signal reaches Pedro Ramírez (SUP) and Miguel Ochoa (Southeast zone Inspector) **simultaneously**

> [!info] Associate Status Indicator
> María López: Orange → **Gray** (Injured)

> [!warning] Protection rule
> While María is in Gray status, her absences **do not count** toward the 3-absences → [[Blacklist]] rule. Gray status protects the injured associate.

### 7.2 — On-site information from the Supervisor

Pedro Ramírez ([[Supervisor|SUP]]) receives the notification and goes physically to the laundry area. He captures the on-site information in the accident card:

| Field | Captured information |
|---|---|
| Exact location | Laundry area, hallway between industrial washers and ironing station |
| Circumstances | Associate slipped on wet floor while transporting dirty linen cart |
| Witnesses | Elena Cruz (shift partner) |
| Immediate care | Ice applied to ankle, associate seated in rest area |

### 7.3 — Medical follow-up by the Inspector

Miguel Ochoa ([[Inspector]]) receives the notification in the app and travels to the hotel. He assesses the situation and decides to transfer María to the nearest medical center.

Miguel completes the accident card with medical information:

| Field | Captured information |
|---|---|
| Transfer | Southeast Medical Center, arrival 11:45 AM |
| Diagnosis | Grade I ankle sprain |
| Days of incapacity | 5 days (June 18–22) |
| Medical notes | Complete rest, no weight bearing, follow-up review on June 23 |

### 7.4 — Card closure

On Monday June 23, María López receives medical discharge. Miguel Ochoa ([[Inspector]]) closes the accident card in the system.

> [!warning] Business Rule
> The [[Inspector]] is **always** the final party responsible for closing the accident card. No exceptions. Closure requires documented medical discharge.

> [!info] Associate Status Indicator
> María López: Gray → **Dark Green** (Available)

María is available in the [[Associate Pool]] to be reassigned. Ana Martínez ([[Recruiter]]) reassigns her to Hotel Riviera Maya to continue her Housekeeper position.

---

## Phase 8 — Stand-by

> Reference: [[Associate Status Indicator]] · [[Hotel Rules]]

### 8.1 — Stand-by activation

It is July 2026. The low season significantly reduces hotel occupancy. Laura Torres ([[Area Manager|GH]]) decides she does not need both Housekeepers simultaneously.

Laura puts Elena Cruz on **Stand-by** from the app.

> [!info] Associate Status Indicator
> Elena Cruz: Orange → **Pink** (Stand-by)

> [!warning] Stand-by rules
> - Elena has **no** [[Schedule]] or [[Timesheet]] while in Pink
> - Elena **cannot** clock in
> - **No defined end date** — the status is maintained until any hotel role changes it
> - The action can be executed by: [[General Manager]], [[Area Manager]], or [[Supervisor]]

### 8.2 — Reactivation

Three weeks later, hotel occupancy picks back up. Laura Torres reactivates Elena Cruz from the app, changing her status back to operational.

> [!info] Associate Status Indicator
> Elena Cruz: Pink → operational status

Elena reappears in the hotel's [[Schedule]] and can clock in again. Her [[Timesheet]] is generated from the reactivation week onward.

---

## Phase 9 — Weekly Billing

> Reference: [[Hotel Invoice]] · [[Payroll Flow]] · [[Contract]]

### 9.1 — Automatic invoice generation

At the close of the week of May 26 through June 1, the system automatically generates the invoice for Hotel Riviera Maya Beach Resort.

**Invoice — Week of May 26 to June 1, 2026**

| Associate | Position | Regular hours | Authorized OT hours | Bill rate | Subtotal |
|---|---|---|---|---|---|
| María López | Housekeeper | 36.17 | 0 | $280/hr | $10,127.60 |
| Juan Hernández | Houseman | 35.75 | 0 | $240/hr | $8,580.00 |
| Elena Cruz | Housekeeper | 36.17 | 0 | $280/hr | $10,127.60 |

| Concept | Amount |
|---|---|
| Services subtotal | $28,835.20 |
| Credits | $0.00 |
| **Total due** | **$28,835.20** |

> [!warning] Billing rules
> - Only the **bill rate** from the [[Contract]] is used. The pay rate (what Oranje pays the associate) is never reflected in the invoice.
> - Only **hotel-authorized overtime** is billed. Unauthorized extra hours are not included.
> - If the week crossed a month boundary and the contract specifies "Split invoice by month: yes," the system would generate two separate invoices.

> [!tip] Automatic system action
> The invoice is generated with a unique folio assigned by Oranje. It is sent to the hotel as a fiscal document.

---

## Phase 10 — Quality Supervision (QA)

> Reference: [[Quality Indicator]] · [[QA Operator]] · [[QA Manager]]

### 10.1 — Ongoing monitoring

A [[QA Operator]] is permanently assigned to the Hotel department. This operator continuously monitors the quality indicators of the staffing service that Oranje provides to Hotel Riviera Maya and all hotel clients.

The [[Quality Indicator]] for the Hotel department remains **Green** (Optimal quality) during the first weeks of operation.

> [!warning] Escalation rule
> If the [[Quality Indicator]] reaches **Red** (Critical quality) without improvement after notification, the [[QA Manager]] escalates to management. QA does not execute Hotel operations; it only observes, measures, and provides feedback.

---

## Status Indicator Transition Summary

### [[Onboarding Status Indicator]]
```
Gray → Light Blue → Green → Yellow → Pink → Orange (active client)
```

### [[Requisition Status Indicator]] (Requisition 202605190830A3)
```
Apple Green → Green → Yellow → Light Blue (fully covered)
```

### [[Requisition Position Status Indicator]]
```
Gold → Orange → Green (100% covered)
```

### [[Associate Status Indicator]] — María López
```
Dark Green → White → Apple Green → Light Blue → Orange → Gray → Dark Green
```

### [[Associate Status Indicator]] — Juan Hernández
```
Dark Green → White → Apple Green → Light Blue → Orange → Red → Black (Blacklist)
```

### [[Associate Status Indicator]] — Elena Cruz
```
Dark Green → White → Apple Green → Light Blue → Orange → Pink (Stand-by) → reactivated
```

---

## Modules and Referenced Concepts

| Module | Reference |
|---|---|
| Hotel as client | [[Hotel]] · [[Hotel Rules]] |
| Hotel roles | [[General Manager]] · [[Area Manager]] · [[Supervisor]] |
| Commercial onboarding | [[Onboarding Flow]] · [[Onboarding Status Indicator]] · [[Customized Proposal]] · [[Terms and Conditions Document]] · [[Contract]] |
| Requisitions | [[Requisition]] · [[Requisition Flow]] · [[Requisition Status Indicator]] · [[Requisition Position Status Indicator]] · [[Requisition Urgency Indicator]] |
| Staffing assignment | [[Associate Pool]] · [[Recruiter]] · [[Self-Pick]] |
| Daily operations | [[Schedule]] · [[Timesheet]] · [[Associate Status Indicator]] |
| Inspection | [[Inspector]] · [[Coordinator]] · [[Inspection Rules]] |
| Contingencies | [[Work Accident]] · [[Work Accident Flow]] · [[Blacklist]] |
| Billing | [[Hotel Invoice]] · [[Payroll Flow]] |
| Quality | [[Quality Indicator]] · [[Timesheet Compliance Indicator]] · [[QA Operator]] · [[QA Manager]] |

---

## Related Simulations

- [[Simulation - Sales Point of View]] — Details the commercial onboarding process from the BD and BDC perspective through the hotel's conversion to an active client.
- [[Simulation - Inspection Perspective]] — Shows the Inspector's field operation: Day 1 and Day 3 verification, reports, and accidents from their perspective.
- [[Simulation - Recruitment Perspective]] — Covers the recruitment and staffing assignment process the hotel requests through requisitions.
- [[Simulation - Associate Lifecycle]] — Narrates the complete experience of the associate assigned to the hotel, including states and transitions that affect daily operations.
