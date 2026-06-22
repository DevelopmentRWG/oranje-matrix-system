---
tipo: simulación
perspectiva: ventas
hotel_ficticio: Hotel Costa Esmeralda
zona: Noroeste
jerarquía: comercial
tags:
  - simulación
  - ventas
  - ciclo-completo
aliases:
  - Sales Simulation
---

# Complete Simulation — Sales Point of View

> [!abstract] Purpose
> This simulation narrates the complete commercial cycle of a hotel within the Oranje system, from the perspective of the Sales team: the [[Business Developer]] (BD) and the [[Business Developer Coordinator]] (BDC). It walks through all the stages of the [[Onboarding Status Light|Onboarding Status Light]], including a rejection and reactivation branch, up to the operational handoff. All data is fictitious, but every action, transition, and rule faithfully respects the vault documentation.

## Simulation characters

| Character | Role | Department |
|---|---|---|
| Sofía Méndez | [[Business Developer]] (BD) | Sales — Oranje |
| Ricardo Fuentes | [[Business Developer Coordinator]] (BDC) | Sales — Oranje |
| Operator 4 | [[QA Operator|QA Operator]] (permanently assigned to Sales) | QA — Oranje |
| Daniel Ortega | [[Inspector|Inspector]] (Noroeste zone) | Inspection — Oranje |
| Mariana Vega | Operations Manager | Hotel Costa Esmeralda |
| Carlos Navarro | General Director (new) | Hotel Costa Esmeralda |

---

## Phase 1 — Prospecting

> Reference: [[Onboarding Flow|Onboarding Flow]] · [[Onboarding Status Light|Onboarding Status Light]]

### 1.1 — Hotel identification (Gray)

It is Monday, June 2, 2026. Sofía Méndez, [[Business Developer]] assigned to the Noroeste zone, reviews her territory route. She identifies **Hotel Costa Esmeralda** as a 120-room hotel with high seasonal occupancy and no external staffing provider.

Sofía creates the hotel record as a prospect in the system.

> [!info] Onboarding Status Light
> → **Gray** — Hotel identified
> **Date:** 2026-06-02 · **Responsible:** Sofía Méndez (BD) · **Comment:** "Hotel identified on the Noroeste Zone route. 120 rooms, no current staffing provider."

> [!tip] QA — Operator 4 observes
> Operator 4 records the start of the onboarding cycle for Hotel Costa Esmeralda. From this moment, the **Average onboarding cycle** begins to count (target: ≤ 45 days). — [[Metrics and KPIs by Department#Ventas|KPI 2]]

---

## Phase 2 — Contact and data collection

> Reference: [[Onboarding Status Light#Azul Claro — Contacto y recopilación de datos|Light Blue — Contact and data collection]] · [[Onboarding Flow|Onboarding Flow]]

### 2.1 — First phone contact

Tuesday, June 3. Sofía calls Hotel Costa Esmeralda. She speaks with Mariana Vega, Operations Manager, who confirms that the Housekeeping department is undersized for the high season starting in July. She schedules an on-site visit for Thursday the 5th.

### 2.2 — Cold visit

Thursday, June 5. Sofía shows up at the hotel. She tours the facilities with Mariana, visits the Housekeeping and Laundry areas, meets the current team, and evaluates the operation.

**Identified need:** the hotel requires 5 Housekeepers and 2 Housemen to cover the high season, under full-time modality.

Sofía creates the hotel profile in the system with the collected data:

| Field | Value |
|---|---|
| Hotel name | Hotel Costa Esmeralda |
| Zone | [[Zones\|Noroeste]] |
| Email | operaciones@costaesmeralda.com |
| Phone | +52 311 555 0200 |
| Main contact | Mariana Vega |
| Title | Operations Manager |
| Need | [[Hotel Departments\|Housekeeping]] staff: 5 [[Posiciones\|Housekeeper]], 2 [[Posiciones\|Houseman]] |

> [!info] Onboarding Status Light
> Gray → **Light Blue** — Contact and data collection
> **Date:** 2026-06-05 · **Responsible:** Sofía Méndez (BD) · **Comment:** "Cold visit completed. Profile created. Need: 5 HK + 2 HM for high season."

> [!warning] Business rule
> Mandatory actions in Light Blue: create the hotel profile, collect data (name, email, phone, contact, need), perform a cold visit. — [[Onboarding Status Light#Azul Claro — Contacto y recopilación de datos|Light Blue — Contact and data collection]]

---

## Phase 3 — First proposal

> Reference: [[Onboarding Status Light#Verde — Propuesta enviada|Green — Proposal sent]] · [[Personalized Proposal|Personalized Proposal]]

### 3.1 — Drafting the Personalized Proposal

Friday, June 6. Sofía drafts the [[Personalized Proposal|Personalized Proposal]] for Hotel Costa Esmeralda:

| Component | Detail |
|---|---|
| Services offered | Housekeeping staffing: Housekeepers and Housemen |
| Operation model | Oranje recruits, assigns, and supervises. Zone inspector present on Day 1 and Day 3 |
| Tentative prices (pay rate) | $12.00/hr (HK), $10.50/hr (HM) |
| Tentative prices (bill rate) | $18.00/hr (HK), $16.00/hr (HM) |
| General conditions | Overtime at 1.5x, holidays at 2x, uniforms included |

Sofía sends the proposal by email to Mariana Vega and delivers a physical copy during a brief visit to the hotel.

### 3.2 — Follow-up

Sofía records each contact attempt in the system:

| Date | Type | Result |
|---|---|---|
| June 9 | Call | Mariana says "I'm reviewing it with the director" |
| June 10 | Follow-up email | No response |
| June 11 | Call | Mariana reports that the director rejected the proposal |

> [!info] Onboarding Status Light
> Light Blue → **Green** — Proposal sent
> **Date:** 2026-06-06 · **Responsible:** Sofía Méndez (BD) · **Comment:** "Personalized Proposal sent by email and delivered in person."

> [!warning] Business rule
> Actions in Green: draft personalized proposal (services, prices, conditions), send to the hotel, record contact attempts and responses, follow up. — [[Onboarding Status Light#Verde — Propuesta enviada|Green — Proposal sent]]

---

## Phase 4 — Rejection (alternate branch)

> Reference: [[Onboarding Status Light#Rojo — Rechazo o no interés|Red — Rejection or no interest]] · [[Sales Rules#Reactivaciones|Sales Rules#Reactivations]]

### 4.1 — The hotel rejects the proposal

Wednesday, June 11. Mariana Vega informs Sofía that the hotel's General Director decided not to hire an external service for the time being — he considers that the budget does not allow it during this quarter.

Sofía evaluates the case: the hotel showed genuine interest during the visit, the operational need is real. The rejection stems from a budgetary decision by the director, not from a lack of need. Sofía decides to mark the prospect as rejected but with reactivation potential.

> [!info] Onboarding Status Light
> Green → **Red** — Rejection or no interest
> **Date:** 2026-06-11 · **Responsible:** Sofía Méndez (BD) · **Comment:** "Hotel director rejected due to budget. Operational need confirmed. High reactivation potential."

> [!warning] Business rule
> The [[Business Developer]] manages the Red status. Evaluates whether the hotel is archived or reactivated. — [[Onboarding Status Light#Rojo — Rechazo o no interés|Red — Rejection or no interest]]

> [!tip] QA — Operator 4 observes
> Transition to Red recorded. It feeds the **Loss rate** KPI (hotels in Red or Black without reactivation / total managed). Target: ≤ 20%. This hotel does not yet count as a definitive loss because Sofía recorded reactivation potential. — [[Metrics and KPIs by Department#Ventas|KPI 4]]

---

## Phase 5 — Reactivation

> Reference: [[Sales Rules#Reactivaciones|Sales Rules#Reactivations]] · [[Onboarding Status Light#Azul Claro — Contacto y recopilación de datos|Light Blue — Contact and data collection]]

### 5.1 — Change of circumstances

Wednesday, June 25. 14 days have passed. Sofía receives information through a contact in the zone that the General Director of Hotel Costa Esmeralda was replaced. The new director, **Carlos Navarro**, comes from a hotel chain that already worked with staffing services and is open to exploring the proposal.

Sofía decides to reactivate the prospect.

> [!info] Onboarding Status Light
> Red → **Light Blue** — Reactivation
> **Date:** 2026-06-25 · **Responsible:** Sofía Méndez (BD) · **Comment:** "New director (Carlos Navarro) open to staffing services. Restarting contact."

> [!warning] Business rule
> Red, Black, and Brown **always** reactivate toward Light Blue. Responsible for reactivation from Red: [[Business Developer]]. — [[Sales Rules#Reactivaciones|Sales Rules#Reactivations]]

> [!tip] QA — Operator 4 observes
> Reactivation from Red initiated. By advancing beyond Green, it will feed the **Successful reactivation rate** KPI (target: ≥ 40%). — [[Metrics and KPIs by Department#Ventas|KPI 5]]

---

## Phase 6 — Second cycle: contact and proposal

> Reference: [[Onboarding Status Light#Azul Claro — Contacto y recopilación de datos|Light Blue — Contact and data collection]] · [[Onboarding Status Light#Verde — Propuesta enviada|Green — Proposal sent]] · [[Personalized Proposal|Personalized Proposal]]

### 6.1 — New contact (Light Blue)

Thursday, June 26. Sofía calls the hotel and speaks directly with Carlos Navarro. He confirms immediate interest. Sofía schedules a visit for Friday the 27th.

Friday, June 27. Sofía visits the hotel with Carlos and Mariana. The needs have grown: they now require **8 Housekeepers, 3 Housemen, and 2 Laundry staff** to cover the full high season.

Sofía updates the hotel profile with the new contact (Carlos Navarro, General Director) and the expanded needs.

> [!info] Onboarding Status Light
> Light Blue (maintained) — Second contact and visit
> **Date:** 2026-06-27 · **Responsible:** Sofía Méndez (BD) · **Comment:** "Second visit completed. New director confirms interest. Needs updated: 8 HK, 3 HM, 2 LN."

### 6.2 — Second proposal (Green)

Saturday, June 28. Sofía drafts a new [[Personalized Proposal|Personalized Proposal]] with the updated demand:

| Component | Detail |
|---|---|
| Services offered | Housekeeping and Laundry staffing |
| Positions | 8 [[Posiciones\|Housekeeper]], 3 [[Posiciones\|Houseman]], 2 [[Posiciones\|Laundry]] |
| Operation model | Recruitment, assignment, supervision by Oranje |
| Tentative prices (pay rate) | $12.50/hr (HK), $11.00/hr (HM), $11.50/hr (LN) |
| Tentative prices (bill rate) | $19.00/hr (HK), $16.50/hr (HM), $17.00/hr (LN) |
| General conditions | Overtime at 1.5x, holidays at 2x, uniforms included |

Sofía sends the proposal. Carlos responds on Tuesday, July 1: **"We're interested. Let's move forward with the formal terms."**

> [!info] Onboarding Status Light
> Light Blue → **Green** — Second proposal sent
> **Date:** 2026-06-28 · **Responsible:** Sofía Méndez (BD) · **Comment:** "Second Personalized Proposal with updated demand sent to new director."

> [!info] Onboarding Status Light
> Green → advance due to confirmed interest
> **Date:** 2026-07-01 · **Responsible:** Sofía Méndez (BD) · **Comment:** "Director accepts proposal in principle. Requests to negotiate specific terms."

---

## Phase 7 — Follow-up and T&C Document

> Reference: [[Onboarding Status Light#Amarillo — En seguimiento tras propuesta|Yellow — In follow-up after proposal]] · [[Terms and Conditions Document|Terms and Conditions Document (T&C)]]

### 7.1 — Creating the Terms and Conditions Document (Yellow)

Wednesday, July 2. Sofía, with support from Ricardo Fuentes ([[Business Developer Coordinator]]), creates the [[Terms and Conditions Document|Terms and Conditions Document (T&C)]] with the proposed commercial parameters:

| Field | Proposed value |
|---|---|
| Pay rate (Housekeeper) | $12.50/hr |
| Pay rate (Houseman) | $11.00/hr |
| Pay rate (Laundry) | $11.50/hr |
| Bill rate (Housekeeper) | $19.00/hr |
| Bill rate (Houseman) | $16.50/hr |
| Bill rate (Laundry) | $17.00/hr |
| Overtime | 1.5x bill rate after 40 gross weekly hours |
| Holidays | 2x bill rate on federal holidays |
| Week start | Monday |
| Week end | Sunday |
| Tentative start date | July 21, 2026 |

> [!info] Onboarding Status Light
> Green → **Yellow** — In follow-up after proposal
> **Date:** 2026-07-02 · **Responsible:** Sofía Méndez (BD) · **Comment:** "T&C Document drafted with support from the BDC. Pending presentation to the hotel."

> [!warning] Business rule
> In Yellow, the BD or BDC creates the [[Terms and Conditions Document|Terms and Conditions Document (T&C)]] with the mandatory fields: pay rate, bill rate, overtime, holidays, calendar. The BDC supports but does not yet have the exclusive decision-making role — that comes in Pink. — [[Onboarding Status Light#Amarillo — En seguimiento tras propuesta|Yellow — In follow-up after proposal]]

---

## Phase 8 — Terms negotiation

> Reference: [[Onboarding Status Light#Rosa — Negociación de términos|Pink — Terms negotiation]] · [[Sales Rules#Conversión de prospecto a cliente|Sales Rules#Prospect-to-client conversion]] · [[Automatic Conversion Trigger|Automatic Conversion Trigger]] · [[Contrato|Contract]]

### 8.1 — Start of formal negotiation (Pink)

Monday, July 7. Sofía and Ricardo (BDC) meet with Carlos Navarro and Mariana Vega at Hotel Costa Esmeralda to present and negotiate the T&C Document.

> [!info] Onboarding Status Light
> Yellow → **Pink** — Terms negotiation
> **Date:** 2026-07-07 · **Responsible:** Sofía Méndez (BD) · **Comment:** "T&C Document presented to the hotel. Formal negotiation begins."

### 8.2 — Negotiation rounds

**Round 1 — July 7:**
Carlos objects to the Housekeepers' bill rate: $19.00/hr seems high compared to his budget. He requests $17.00/hr. The other rates are accepted.

**Internal analysis — July 8:**
Ricardo (BDC) analyzes the margins. With a pay rate of $12.50/hr, the minimum viable bill rate for Housekeepers is $18.00/hr. Ricardo prepares a counteroffer.

**Round 2 — July 9:**
Sofía and Ricardo present the counteroffer: $18.25/hr for Housekeepers. Carlos accepts. All terms are agreed upon.

### 8.3 — Final terms

| Field | Final value |
|---|---|
| Pay rate (Housekeeper) | $12.50/hr |
| Pay rate (Houseman) | $11.00/hr |
| Pay rate (Laundry) | $11.50/hr |
| Bill rate (Housekeeper) | $18.25/hr |
| Bill rate (Houseman) | $16.50/hr |
| Bill rate (Laundry) | $17.00/hr |
| Overtime | 1.5x bill rate after 40 gross weekly hrs |
| Holidays | 2x bill rate on federal holidays |
| Week start | Monday |
| Week end | Sunday |
| Validity | July 21, 2026 — July 20, 2027 (1 year) |
| Renewal | Automatic for annual periods unless notice 30 days prior |

Ricardo (BDC) validates the T&C Document: all mandatory fields are complete, the margins are viable.

> [!warning] Business rule
> The [[Business Developer Coordinator]] validates the terms of the [[Terms and Conditions Document|Terms and Conditions Document (T&C)]] before closing. — [[Sales Rules#Documento de Términos y Condiciones|Sales Rules#Terms and Conditions Document]]

### 8.4 — Creating the Hotel User

Thursday, July 10. Before approving the conversion, Ricardo (BDC) creates the [[Hotel User|Hotel User]] in the system:

| Field | Value |
|---|---|
| Hotel | Hotel Costa Esmeralda |
| Zone | Noroeste |
| General Director | Carlos Navarro |
| Operations Manager | Mariana Vega |
| Access email | operaciones@costaesmeralda.com |

> [!warning] Business rule — Mandatory precondition
> The [[Hotel User|Hotel User]] **must** be created in the system **before** triggering the conversion. Without this step, the Automatic Trigger cannot execute. — [[Sales Rules#Conversión de prospecto a cliente|Sales Rules#Prospect-to-client conversion]]

### 8.5 — Conversion approval by the BDC

Friday, July 11. Ricardo Fuentes (BDC) gives the **final yes**. He approves the conversion of Hotel Costa Esmeralda from prospect to active client.

> [!warning] Business rule — BDC exclusivity
> **Only** the [[Business Developer Coordinator]] can approve the conversion of a prospect to a client. No other role has this authority. — [[Sales Rules#Conversión de prospecto a cliente|Sales Rules#Prospect-to-client conversion]]

### 8.6 — Automatic Conversion Trigger

Upon approving the conversion, the system executes the [[Automatic Conversion Trigger|Automatic Conversion Trigger]] — three actions in parallel:

> [!tip] Automatic system actions — [[Automatic Conversion Trigger|Automatic Conversion Trigger]]
> 1. **Welcome email** sent to operaciones@costaesmeralda.com
> 2. **Notification to the BD:** Sofía Méndez receives the alert "Hotel Costa Esmeralda converted to active client"
> 3. **Prospect list:** Hotel Costa Esmeralda disappears from the prospect list

### 8.7 — Contract formalization

The [[Contrato|Contract]] is formalized from the T&C Document. Each field has a direct effect on the system:

| Contract field | Value | Effect on the system |
|---|---|---|
| Pay rate | $12.50 / $11.00 / $11.50 | Calculation of payments to the collaborator |
| Bill rate | $18.25 / $16.50 / $17.00 | Calculation of [[Hotel Invoicing|Hotel Billing]] |
| Overtime | 1.5x bill rate | Overtime rules in [[Timesheet]] |
| Holidays | 2x bill rate | Holiday calendar |
| Week start/end | Monday — Sunday | Weekly [[Schedule]] structure |
| Validity | Jul 21, 2026 — Jul 20, 2027 | Validity period |
| Renewal | Automatic annual, 30-day notice | Renewal terms |

> [!info] Onboarding Status Light
> Pink → **Orange** — Agreement signed, hotel active client
> **Date:** 2026-07-11 · **Responsible:** Ricardo Fuentes (BDC) · **Comment:** "Conversion approved. Hotel User created. Automatic trigger executed. Contract formalized."

---

## Phase 9 — Active hotel and handoff to operations

> Reference: [[Onboarding Status Light#Naranja — Acuerdo firmado, hotel cliente activo|Orange — Agreement signed, hotel active client]] · [[Sales Rules#Transición a Operaciones (Naranja)|Sales Rules#Transition to Operations (Orange)]] · [[Requisition Flow|Requisition Flow]]

### 9.1 — Change of responsibility (Orange)

With Hotel Costa Esmeralda in **Orange** status, responsibility is redistributed:

| Scope | Responsible | Role |
|---|---|---|
| Operational | Daniel Ortega | [[Inspector|Inspector]] of the Noroeste zone |
| Operational | Recruiters | [[Recruiter\|Recruiters]] (staff assignment) |
| Commercial (reference) | Sofía Méndez | assigned [[Business Developer]] |
| Commercial (reference) | Ricardo Fuentes | supervising [[Business Developer Coordinator]] |

Sofía and Ricardo no longer execute operations for this hotel. Their role is to maintain the commercial relationship and remain available for renegotiations or contractual disputes.

> [!warning] Business rule
> **Orange is the only status of the [[Onboarding Status Light|Onboarding Status Light]] that enables the hotel to generate [[Requisition\|requisitions]].** Before this status, the hotel is a commercial prospect with no operational access. — [[Sales Rules#Transición a Operaciones (Naranja)|Sales Rules#Transition to Operations (Orange)]]

### 9.2 — The first requisition

Monday, July 14. Mariana Vega, now with system access as the hotel's [[Supervisor]], creates the first staffing requisition:

| # Position | Position | Quantity | Modality | Start date | Schedule | English |
|---|---|---|---|---|---|---|
| 1 | [[Posiciones\|Housekeeper]] | 5 | [[Employment Types\|Full time]] | Jul 21, 2026 | 07:00–15:00 | Basic |
| 2 | [[Posiciones\|Houseman]] | 3 | [[Employment Types\|Full time]] | Jul 21, 2026 | 07:00–15:00 | Basic |
| 3 | [[Posiciones\|Laundry]] | 2 | [[Employment Types\|Full time]] | Jul 21, 2026 | 06:00–14:00 | Not required |

> [!tip] Automatic system actions
> - The requisition number is generated: **202607141015A3**
> - Carlos Navarro (General Director) authorizes the requisition
> - **Urgency calculation:** authorization date (Jul 14, 10:30) vs start date (Jul 21, 07:00) ≈ 165 hours → **Strong Green** (Normal, >120h) — [[Requisition Urgency Status Light|Requisition Urgency Status Light]]
> - **Inspector assigned:** Daniel Ortega — automatic according to the Noroeste zone
> - The requisition appears in the [[Requisition Self-Pick|Requisition Self-Pick]] inbox, prioritized by urgency

> [!info] Connection to the operational cycle
> The requisition now follows the [[Requisition Flow|Requisition Flow]]. A [[Recruiter|Recruiter]] will take it from the inbox via [[Requisition Self-Pick|Requisition Self-Pick]] and fill the positions with collaborators from the [[Collaborator Pool|Collaborator Pool]].
>
> **The Sales cycle has fulfilled its function: the hotel is active and generating requisitions.**

---

## Phase 10 — QA supervision: closing the cycle

> Reference: [[Metrics and KPIs by Department#Ventas|Metrics and KPIs by Department#Sales]] · [[Quality Indicator|Quality Indicator]] · [[Sales Rules#Supervisión de Calidad (QA)|Sales Rules#Quality Supervision (QA)]]

The [[QA Operator|QA Operator]] (Operator 4), permanently assigned to the [[Sales/Sales|Sales]] department, has observed the entire cycle without executing any operational action. His role is exclusively observation, measurement, and feedback.

### Summary of measured KPIs

| # | KPI | Result in this simulation | Target | Status |
|---|---|---|---|---|
| 1 | **Conversion rate** | +1 hotel converted in the period | ≥ 25% | ✓ Contributes to target |
| 2 | **Average onboarding cycle** | 39 days (Jun 2 — Jul 11), includes 14 days in Red | ≤ 45 days | ✓ Within target |
| 3 | **Stagnation rate** | 0 days in Brown | ≤ 10% | ✓ No stagnation |
| 4 | **Loss rate** | Hotel reactivated from Red — does not count as a definitive loss | ≤ 20% | ✓ Recovered |
| 5 | **Successful reactivation rate** | Hotel reactivated from Red and converted to Orange (surpassed Green) | ≥ 40% | ✓ Successful reactivation |

> [!warning] Business rule
> QA does not execute the Sales operation; it only observes, measures, and provides feedback. If the department's [[Quality Indicator|Quality Indicator]] reaches Red without improvement, the [[QA Manager|QA Manager]] escalates to management. — [[Sales Rules#Supervisión de Calidad (QA)|Sales Rules#Quality Supervision (QA)]]

The Sales department's [[Quality Indicator|Quality Indicator]] remains **Green** (Optimal quality). No formal observations are issued.

---

## Summary of Onboarding Status Light transitions

| Date | Status | Action | Responsible |
|---|---|---|---|
| Jun 2, 2026 | **Gray** | Hotel identified in the Noroeste zone | Sofía (BD) |
| Jun 5, 2026 | **Light Blue** | Cold visit, profile created | Sofía (BD) |
| Jun 6, 2026 | **Green** | Personalized Proposal sent | Sofía (BD) |
| Jun 11, 2026 | **Red** | Hotel rejects proposal | Sofía (BD) |
| Jun 25, 2026 | **Light Blue** | Reactivation due to change of director | Sofía (BD) |
| Jun 28, 2026 | **Green** | Second proposal sent | Sofía (BD) |
| Jul 2, 2026 | **Yellow** | T&C Document drafted | Sofía (BD) + Ricardo (BDC) |
| Jul 7, 2026 | **Pink** | Formal negotiation begins | Sofía (BD) + Ricardo (BDC) |
| Jul 11, 2026 | **Orange** | Conversion approved, hotel active | Ricardo (BDC) |

```mermaid
graph LR
    Gris -->|BD identifies| AC1[Light Blue]
    AC1 -->|Proposal sent| V1[Green]
    V1 -->|Hotel rejects| Rojo[Red]
    Rojo -->|Reactivation| AC2[Light Blue]
    AC2 -->|2nd proposal| V2[Green]
    V2 -->|Hotel interested| Amarillo[Yellow]
    Amarillo -->|Formal negotiation| Rosa[Pink]
    Rosa -->|BDC approves conversion| Naranja[Orange]

    style Gris fill:#808080,color:#fff
    style AC1 fill:#87CEEB,color:#000
    style AC2 fill:#87CEEB,color:#000
    style V1 fill:#228B22,color:#fff
    style V2 fill:#228B22,color:#fff
    style Rojo fill:#DC143C,color:#fff
    style Amarillo fill:#FFD700,color:#000
    style Rosa fill:#FF69B4,color:#fff
    style Naranja fill:#FF8C00,color:#fff
```

---

## Referenced modules and concepts

| Module | Reference |
|---|---|
| Sales | [[Sales/Sales\|Sales]] · [[Sales Rules|Sales Rules]] |
| Sales roles | [[Business Developer]] · [[Business Developer Coordinator]] |
| Onboarding | [[Onboarding Flow|Onboarding Flow]] · [[Onboarding Status Light|Onboarding Status Light]] |
| Proposal and closing | [[Personalized Proposal|Personalized Proposal]] · [[Terms and Conditions Document|Terms and Conditions Document (T&C)]] · [[Automatic Conversion Trigger|Automatic Conversion Trigger]] · [[Hotel User|Hotel User]] · [[Contrato|Contract]] |
| Quality | [[QA Operator|QA Operator]] · [[QA Manager|QA Manager]] · [[Quality Indicator|Quality Indicator]] · [[Metrics and KPIs by Department|Metrics and KPIs by Department]] |
| Catalogs | [[Zones|Zones]] · [[Posiciones|Positions]] · [[Hotel Departments|Hotel Departments]] · [[Employment Types|Employment Modalities]] |
| Operations (handoff) | [[Inspector|Inspector]] · [[Recruiter|Recruiter]] · [[Requisition|Requisition]] · [[Requisition Flow|Requisition Flow]] · [[Requisition Self-Pick|Requisition Self-Pick]] · [[Schedule]] · [[Timesheet]] · [[Hotel Invoicing|Hotel Billing]] |
| Operational status lights | [[Requisition Status Light|Requisition Status Light]] · [[Requisition Urgency Status Light|Requisition Urgency Status Light]] · [[Collaborator Pool|Collaborator Pool]] |

---

## Related simulations

- [[Simulation - Inspection Point of View|Inspection Point of View Simulation]] — Continues the story of Hotel Costa Esmeralda from the perspective of Inspector Daniel Ortega, who receives the operational handoff after the conversion to client.
- [[Simulation - Hotel Point of View|Hotel Point of View Simulation]] — Narrates the complete cycle of a hotel as a client, including the commercial phases detailed here from Sales.
- [[Simulation - Recruitment Point of View|Recruitment Point of View Simulation]] — Covers the staffing process that activates once the hotel generates its first requisition in Orange status.
- [[Simulation - Collaborator Life Cycle|Collaborator Life Cycle Simulation]] — Walks through the states of the collaborator assigned to the hotel, from entry into the Pool to daily operation.
