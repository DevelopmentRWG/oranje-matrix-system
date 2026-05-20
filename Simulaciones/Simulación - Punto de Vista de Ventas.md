---
type: simulation
perspective: sales
fictional_hotel: Hotel Costa Esmeralda
zone: Northwest
hierarchy: commercial
tags:
  - simulation
  - sales
  - full-cycle
aliases:
  - Simulation Sales
---

# Full Simulation — Sales Point of View

> [!abstract] Purpose
> This simulation narrates the complete commercial cycle of a hotel within the Oranje system, from the perspective of the Sales team: the [[Business Developer]] (BD) and the [[Business Developer Coordinator]] (BDC). It covers every stage of the [[Semáforo Onboarding]], including a rejection and reactivation branch, through to the operational handoff. All data is fictional, but every action, transition, and rule faithfully follows the vault documentation.

## Simulation Characters

| Character | Role | Department |
|---|---|---|
| Sofía Méndez | [[Business Developer]] (BD) | Sales — Oranje |
| Ricardo Fuentes | [[Business Developer Coordinator]] (BDC) | Sales — Oranje |
| Operator 4 | [[Operador de QA]] (permanently assigned to Sales) | QA — Oranje |
| Daniel Ortega | [[Inspector]] (Northwest zone) | Inspection — Oranje |
| Mariana Vega | Operations Manager | Hotel Costa Esmeralda |
| Carlos Navarro | General Manager (new) | Hotel Costa Esmeralda |

---

## Phase 1 — Prospecting

> Reference: [[Flujo de Onboarding]] · [[Semáforo Onboarding]]

### 1.1 — Hotel Identification (Gray)

It is Monday, June 2, 2026. Sofía Méndez, [[Business Developer]] assigned to the Northwest zone, reviews her territory route. She identifies **Hotel Costa Esmeralda** as a 120-room hotel with high seasonal occupancy and no external staffing provider.

Sofía creates the hotel's record as a prospect in the system.

> [!info] Status Indicator Onboarding
> → **Gray** — Hotel identified
> **Date:** 2026-06-02 · **Responsible:** Sofía Méndez (BD) · **Comment:** "Hotel identified on Northwest Zone route. 120 rooms, no current staffing provider."

> [!tip] QA — Operator 4 Observes
> Operator 4 records the start of the onboarding cycle for Hotel Costa Esmeralda. From this moment the **Average onboarding cycle** begins counting (target: ≤ 45 days). — [[Métricas y KPIs por Departamento#Ventas|KPI 2]]

---

## Phase 2 — Contact and Data Collection

> Reference: [[Semáforo Onboarding#Azul Claro — Contacto y recopilación de datos]] · [[Flujo de Onboarding]]

### 2.1 — First Phone Contact

Tuesday, June 3. Sofía calls Hotel Costa Esmeralda. She speaks with Mariana Vega, Operations Manager, who confirms that the Housekeeping department is understaffed for the high season beginning in July. She schedules an in-person visit for Thursday the 5th.

### 2.2 — Cold Visit

Thursday, June 5. Sofía arrives at the hotel. She tours the facilities with Mariana, visits the Housekeeping and Laundry areas, meets the current team, and evaluates the operation.

**Identified need:** the hotel requires 5 Housekeepers and 2 Housemen to cover the high season, on a full-time basis.

Sofía creates the hotel profile in the system with the collected data:

| Field | Value |
|---|---|
| Hotel name | Hotel Costa Esmeralda |
| Zone | [[Zonas\|Northwest]] |
| Email | operaciones@costaesmeralda.com |
| Phone | +52 311 555 0200 |
| Main contact | Mariana Vega |
| Title | Operations Manager |
| Need | [[Departamentos del Hotel\|Housekeeping]] staff: 5 [[Posiciones\|Housekeeper]], 2 [[Posiciones\|Houseman]] |

> [!info] Status Indicator Onboarding
> Gray → **Light Blue** — Contact and data collection
> **Date:** 2026-06-05 · **Responsible:** Sofía Méndez (BD) · **Comment:** "Cold visit completed. Profile created. Need: 5 HK + 2 HM for high season."

> [!warning] Business Rule
> Required actions in Light Blue: create hotel profile, collect data (name, email, phone, contact, need), conduct cold visit. — [[Semáforo Onboarding#Azul Claro — Contacto y recopilación de datos]]

---

## Phase 3 — First Proposal

> Reference: [[Semáforo Onboarding#Verde — Propuesta enviada]] · [[Propuesta Personalizada]]

### 3.1 — Drafting the Customized Proposal

Friday, June 6. Sofía drafts the [[Propuesta Personalizada]] for Hotel Costa Esmeralda:

| Component | Detail |
|---|---|
| Services offered | Housekeeping staffing: Housekeepers and Housemen |
| Operating model | Oranje recruits, assigns, and supervises. Zone Inspector present on Day 1 and Day 3 |
| Tentative prices (pay rate) | $12.00/hr (HK), $10.50/hr (HM) |
| Tentative prices (bill rate) | $18.00/hr (HK), $16.00/hr (HM) |
| General terms | Overtime at 1.5x, holidays at 2x, uniforms included |

Sofía sends the proposal by email to Mariana Vega and delivers a physical copy during a brief visit to the hotel.

### 3.2 — Follow-up

Sofía logs each contact attempt in the system:

| Date | Type | Outcome |
|---|---|---|
| June 9 | Call | Mariana says "I'm reviewing it with the director" |
| June 10 | Follow-up email | No response |
| June 11 | Call | Mariana informs the director rejected the proposal |

> [!info] Status Indicator Onboarding
> Light Blue → **Green** — Proposal sent
> **Date:** 2026-06-06 · **Responsible:** Sofía Méndez (BD) · **Comment:** "Customized Proposal sent by email and delivered in person."

> [!warning] Business Rule
> Actions in Green: draft customized proposal (services, prices, terms), send to hotel, log contact attempts and responses, follow up. — [[Semáforo Onboarding#Verde — Propuesta enviada]]

---

## Phase 4 — Rejection (Alternate Branch)

> Reference: [[Semáforo Onboarding#Rojo — Rechazo o no interés]] · [[Reglas de Ventas#Reactivaciones]]

### 4.1 — Hotel Rejects the Proposal

Wednesday, June 11. Mariana Vega informs Sofía that the hotel's General Manager decided not to hire external services at this time — he considers the budget does not allow it during this quarter.

Sofía evaluates the case: the hotel showed genuine interest during the visit, the operational need is real. The rejection stems from a budget decision by the director, not a lack of need. Sofía decides to mark the prospect as rejected but with reactivation potential.

> [!info] Status Indicator Onboarding
> Green → **Red** — Rejection or no interest
> **Date:** 2026-06-11 · **Responsible:** Sofía Méndez (BD) · **Comment:** "Hotel director rejected due to budget. Operational need confirmed. High reactivation potential."

> [!warning] Business Rule
> The [[Business Developer]] manages Red status. They evaluate whether the hotel is archived or reactivated. — [[Semáforo Onboarding#Rojo — Rechazo o no interés]]

> [!tip] QA — Operator 4 Observes
> Transition to Red recorded. Feeds the **Loss rate** KPI (hotels in Red or Black without reactivation / total managed). Target: ≤ 20%. This hotel does not yet count as a definitive loss because Sofía logged reactivation potential. — [[Métricas y KPIs por Departamento#Ventas|KPI 4]]

---

## Phase 5 — Reactivation

> Reference: [[Reglas de Ventas#Reactivaciones]] · [[Semáforo Onboarding#Azul Claro — Contacto y recopilación de datos]]

### 5.1 — Change of Circumstances

Wednesday, June 25. Fourteen days have passed. Sofía receives information from a zone contact that the General Manager of Hotel Costa Esmeralda has been replaced. The new director, **Carlos Navarro**, comes from a hotel chain that already worked with staffing services and is open to exploring the proposal.

Sofía decides to reactivate the prospect.

> [!info] Status Indicator Onboarding
> Red → **Light Blue** — Reactivation
> **Date:** 2026-06-25 · **Responsible:** Sofía Méndez (BD) · **Comment:** "New director (Carlos Navarro) open to staffing services. Restarting contact."

> [!warning] Business Rule
> Red, Black, and Brown **always** reactivate to Light Blue. Responsible for reactivation from Red: [[Business Developer]]. — [[Reglas de Ventas#Reactivaciones]]

> [!tip] QA — Operator 4 Observes
> Reactivation from Red initiated. Upon advancing beyond Green, it will feed the **Successful reactivation rate** KPI (target: ≥ 40%). — [[Métricas y KPIs por Departamento#Ventas|KPI 5]]

---

## Phase 6 — Second Cycle: Contact and Proposal

> Reference: [[Semáforo Onboarding#Azul Claro — Contacto y recopilación de datos]] · [[Semáforo Onboarding#Verde — Propuesta enviada]] · [[Propuesta Personalizada]]

### 6.1 — New Contact (Light Blue)

Thursday, June 26. Sofía calls the hotel and speaks directly with Carlos Navarro. He confirms immediate interest. Sofía schedules a visit for Friday the 27th.

Friday, June 27. Sofía visits the hotel with Carlos and Mariana. The needs have grown: now they require **8 Housekeepers, 3 Housemen, and 2 Laundry staff** to cover the full high season.

Sofía updates the hotel profile with the new contact (Carlos Navarro, General Manager) and the expanded needs.

> [!info] Status Indicator Onboarding
> Light Blue (maintained) — Second contact and visit
> **Date:** 2026-06-27 · **Responsible:** Sofía Méndez (BD) · **Comment:** "Second visit completed. New director confirms interest. Updated needs: 8 HK, 3 HM, 2 LN."

### 6.2 — Second Proposal (Green)

Saturday, June 28. Sofía drafts a new [[Propuesta Personalizada]] with the updated demand:

| Component | Detail |
|---|---|
| Services offered | Housekeeping and Laundry staffing |
| Positions | 8 [[Posiciones\|Housekeeper]], 3 [[Posiciones\|Houseman]], 2 [[Posiciones\|Laundry]] |
| Operating model | Recruitment, assignment, supervision by Oranje |
| Tentative prices (pay rate) | $12.50/hr (HK), $11.00/hr (HM), $11.50/hr (LN) |
| Tentative prices (bill rate) | $19.00/hr (HK), $16.50/hr (HM), $17.00/hr (LN) |
| General terms | Overtime at 1.5x, holidays at 2x, uniforms included |

Sofía sends the proposal. Carlos responds on Tuesday, July 1: **"We're interested. Let's move forward with the formal terms."**

> [!info] Status Indicator Onboarding
> Light Blue → **Green** — Second proposal sent
> **Date:** 2026-06-28 · **Responsible:** Sofía Méndez (BD) · **Comment:** "Second Customized Proposal with updated demand sent to new director."

> [!info] Status Indicator Onboarding
> Green → advance due to confirmed interest
> **Date:** 2026-07-01 · **Responsible:** Sofía Méndez (BD) · **Comment:** "Director accepts proposal in principle. Requests to negotiate specific terms."

---

## Phase 7 — Follow-up and Terms and Conditions Document

> Reference: [[Semáforo Onboarding#Amarillo — En seguimiento tras propuesta]] · [[Documento de Términos y Condiciones]]

### 7.1 — Creating the Terms and Conditions Document (Yellow)

Wednesday, July 2. Sofía, with support from Ricardo Fuentes ([[Business Developer Coordinator]]), creates the [[Documento de Términos y Condiciones]] with the proposed commercial parameters:

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

> [!info] Status Indicator Onboarding
> Green → **Yellow** — In follow-up after proposal
> **Date:** 2026-07-02 · **Responsible:** Sofía Méndez (BD) · **Comment:** "Terms and Conditions Document drafted with BDC support. Pending presentation to hotel."

> [!warning] Business Rule
> In Yellow, the BD or BDC creates the [[Documento de Términos y Condiciones]] with the required fields: pay rate, bill rate, overtime, holidays, calendar. The BDC supports but does not yet have the exclusive decision-making role — that comes in Pink. — [[Semáforo Onboarding#Amarillo — En seguimiento tras propuesta]]

---

## Phase 8 — Terms Negotiation

> Reference: [[Semáforo Onboarding#Rosa — Negociación de términos]] · [[Reglas de Ventas#Conversión de prospecto a cliente]] · [[Trigger Automático de Conversión]] · [[Contrato]]

### 8.1 — Formal Negotiation Begins (Pink)

Monday, July 7. Sofía and Ricardo (BDC) meet with Carlos Navarro and Mariana Vega at Hotel Costa Esmeralda to present and negotiate the Terms and Conditions Document.

> [!info] Status Indicator Onboarding
> Yellow → **Pink** — Terms negotiation
> **Date:** 2026-07-07 · **Responsible:** Sofía Méndez (BD) · **Comment:** "Terms and Conditions Document presented to hotel. Formal negotiation begins."

### 8.2 — Negotiation Rounds

**Round 1 — July 7:**
Carlos objects to the Housekeeper bill rate: $19.00/hr seems high compared to his budget. He requests $17.00/hr. All other rates are accepted.

**Internal analysis — July 8:**
Ricardo (BDC) analyzes margins. With a pay rate of $12.50/hr, the minimum viable bill rate for Housekeepers is $18.00/hr. Ricardo prepares a counter-offer.

**Round 2 — July 9:**
Sofía and Ricardo present the counter-offer: $18.25/hr for Housekeepers. Carlos accepts. All terms are agreed upon.

### 8.3 — Final Terms

| Field | Final value |
|---|---|
| Pay rate (Housekeeper) | $12.50/hr |
| Pay rate (Houseman) | $11.00/hr |
| Pay rate (Laundry) | $11.50/hr |
| Bill rate (Housekeeper) | $18.25/hr |
| Bill rate (Houseman) | $16.50/hr |
| Bill rate (Laundry) | $17.00/hr |
| Overtime | 1.5x bill rate after 40 gross weekly hours |
| Holidays | 2x bill rate on federal holidays |
| Week start | Monday |
| Week end | Sunday |
| Term | July 21, 2026 — July 20, 2027 (1 year) |
| Renewal | Automatic for annual periods unless 30-day prior notice |

Ricardo (BDC) validates the Terms and Conditions Document: all required fields are complete, margins are viable.

> [!warning] Business Rule
> The [[Business Developer Coordinator]] validates the terms of the [[Documento de Términos y Condiciones]] before closing. — [[Reglas de Ventas#Documento de Términos y Condiciones]]

### 8.4 — Creating the Hotel User Account

Thursday, July 10. Before approving the conversion, Ricardo (BDC) creates the [[Usuario del Hotel]] in the system:

| Field | Value |
|---|---|
| Hotel | Hotel Costa Esmeralda |
| Zone | Northwest |
| General Manager | Carlos Navarro |
| Operations Manager | Mariana Vega |
| Access email | operaciones@costaesmeralda.com |

> [!warning] Business Rule — Mandatory Precondition
> The [[Usuario del Hotel]] **must** be created in the system **before** triggering the conversion. Without this step, the Automatic Trigger cannot execute. — [[Reglas de Ventas#Conversión de prospecto a cliente]]

### 8.5 — Conversion Approval by the BDC

Friday, July 11. Ricardo Fuentes (BDC) gives the **final approval**. He approves the conversion of Hotel Costa Esmeralda from prospect to active client.

> [!warning] Business Rule — BDC Exclusivity
> **Only** the [[Business Developer Coordinator]] can approve the conversion from prospect to client. No other role has this authority. — [[Reglas de Ventas#Conversión de prospecto a cliente]]

### 8.6 — Automatic Conversion Trigger

Upon approving the conversion, the system executes the [[Trigger Automático de Conversión]] — three parallel actions:

> [!tip] Automatic system actions — [[Trigger Automático de Conversión]]
> 1. **Welcome email** sent to operaciones@costaesmeralda.com
> 2. **Notification to BD:** Sofía Méndez receives alert "Hotel Costa Esmeralda converted to active client"
> 3. **Prospect list:** Hotel Costa Esmeralda disappears from the prospect list

### 8.7 — Contract Formalization

The [[Contrato]] is formalized from the Terms and Conditions Document. Each field has a direct effect on the system:

| Contract Field | Value | System Effect |
|---|---|---|
| Pay rate | $12.50 / $11.00 / $11.50 | Associate payment calculations |
| Bill rate | $18.25 / $16.50 / $17.00 | [[Facturación al Hotel]] calculations |
| Overtime | 1.5x bill rate | Overtime rules in [[Timesheet]] |
| Holidays | 2x bill rate | Federal holiday calendar |
| Week start/end | Monday — Sunday | Weekly [[Schedule]] structure |
| Term | Jul 21, 2026 — Jul 20, 2027 | Validity period |
| Renewal | Automatic annual, 30-day notice | Renewal terms |

> [!info] Status Indicator Onboarding
> Pink → **Orange** — Agreement signed, hotel active client
> **Date:** 2026-07-11 · **Responsible:** Ricardo Fuentes (BDC) · **Comment:** "Conversion approved. Hotel User created. Automatic trigger executed. Contract formalized."

---

## Phase 9 — Active Hotel and Handoff to Operations

> Reference: [[Semáforo Onboarding#Naranja — Acuerdo firmado, hotel cliente activo]] · [[Reglas de Ventas#Transición a Operaciones (Naranja)]] · [[Flujo de Requisición]]

### 9.1 — Responsibility Transfer (Orange)

With Hotel Costa Esmeralda at **Orange** status, responsibility is redistributed:

| Scope | Responsible | Role |
|---|---|---|
| Operational | Daniel Ortega | [[Inspector]] of Northwest zone |
| Operational | Recruiters | [[Reclutadora\|Recruiters]] (staff assignment) |
| Commercial (reference) | Sofía Méndez | Assigned [[Business Developer]] |
| Commercial (reference) | Ricardo Fuentes | Supervising [[Business Developer Coordinator]] |

Sofía and Ricardo no longer execute operations for this hotel. Their role is to maintain the commercial relationship and be available for renegotiations or contractual disputes.

> [!warning] Business Rule
> **Orange is the only status in the [[Semáforo Onboarding]] that enables the hotel to generate [[Requisición|requisitions]].** Before this status, the hotel is a commercial prospect without operational access. — [[Reglas de Ventas#Transición a Operaciones (Naranja)]]

### 9.2 — The First Requisition

Monday, July 14. Mariana Vega, now with system access as the hotel's [[Supervisor]], creates the first staffing requisition:

| # Position | Position | Quantity | Modality | Start date | Schedule | English |
|---|---|---|---|---|---|---|
| 1 | [[Posiciones\|Housekeeper]] | 5 | [[Modalidades de Contratación\|Full time]] | Jul 21, 2026 | 07:00–15:00 | Basic |
| 2 | [[Posiciones\|Houseman]] | 3 | [[Modalidades de Contratación\|Full time]] | Jul 21, 2026 | 07:00–15:00 | Basic |
| 3 | [[Posiciones\|Laundry]] | 2 | [[Modalidades de Contratación\|Full time]] | Jul 21, 2026 | 06:00–14:00 | Not required |

> [!tip] Automatic system actions
> - Requisition number generated: **202607141015A3**
> - Carlos Navarro (General Manager) authorizes the requisition
> - **Urgency calculation:** authorization date (Jul 14 10:30) vs start date (Jul 21 07:00) ≈ 165 hours → **Dark Green** (Normal, >120h) — [[Semáforo de Urgencia de Requisición]]
> - **Inspector assigned:** Daniel Ortega — automatic based on Northwest zone
> - The requisition appears in the [[Self-Pick de Requisiciones]] queue, prioritized by urgency

> [!info] Connection to the operational cycle
> The requisition now follows the [[Flujo de Requisición]]. A [[Reclutadora]] will pick it up from the queue via [[Self-Pick de Requisiciones]] and fill the positions with associates from the [[Pool de Colaboradores]].
>
> **The Sales cycle has fulfilled its purpose: the hotel is active and generating requisitions.**

---

## Phase 10 — QA Supervision: Closing the Cycle

> Reference: [[Métricas y KPIs por Departamento#Ventas]] · [[Indicador de Calidad]] · [[Reglas de Ventas#Supervisión de Calidad (QA)]]

The [[Operador de QA]] (Operator 4), permanently assigned to the [[Ventas/Ventas|Sales]] department, has observed the entire cycle without executing any operational action. Their role is exclusively observation, measurement, and feedback.

### Summary of Measured KPIs

| # | KPI | Result in this simulation | Target | Status |
|---|---|---|---|---|
| 1 | **Conversion rate** | +1 hotel converted in the period | ≥ 25% | ✓ Contributes to target |
| 2 | **Average onboarding cycle** | 39 days (Jun 2 — Jul 11), includes 14 days at Red | ≤ 45 days | ✓ Within target |
| 3 | **Stagnation rate** | 0 days at Brown | ≤ 10% | ✓ No stagnation |
| 4 | **Loss rate** | Hotel reactivated from Red — does not count as definitive loss | ≤ 20% | ✓ Recovered |
| 5 | **Successful reactivation rate** | Hotel reactivated from Red and converted to Orange (surpassed Green) | ≥ 40% | ✓ Successful reactivation |

> [!warning] Business Rule
> QA does not execute Sales operations; it only observes, measures, and provides feedback. If the department's [[Indicador de Calidad]] reaches Red without improvement, the [[Manager de QA]] escalates to management. — [[Reglas de Ventas#Supervisión de Calidad (QA)]]

The [[Indicador de Calidad]] of the Sales department remains at **Green** (Optimal quality). No formal observations are issued.

---

## Summary of Onboarding Status Indicator Transitions

| Date | Status | Action | Responsible |
|---|---|---|---|
| Jun 2, 2026 | **Gray** | Hotel identified in Northwest zone | Sofía (BD) |
| Jun 5, 2026 | **Light Blue** | Cold visit, profile created | Sofía (BD) |
| Jun 6, 2026 | **Green** | Customized Proposal sent | Sofía (BD) |
| Jun 11, 2026 | **Red** | Hotel rejects proposal | Sofía (BD) |
| Jun 25, 2026 | **Light Blue** | Reactivation due to director change | Sofía (BD) |
| Jun 28, 2026 | **Green** | Second proposal sent | Sofía (BD) |
| Jul 2, 2026 | **Yellow** | Terms and Conditions Document drafted | Sofía (BD) + Ricardo (BDC) |
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

## Referenced Modules and Concepts

| Module | Reference |
|---|---|
| Sales | [[Ventas/Ventas\|Sales]] · [[Reglas de Ventas]] |
| Sales Roles | [[Business Developer]] · [[Business Developer Coordinator]] |
| Onboarding | [[Flujo de Onboarding]] · [[Semáforo Onboarding]] |
| Proposal and closing | [[Propuesta Personalizada]] · [[Documento de Términos y Condiciones]] · [[Trigger Automático de Conversión]] · [[Usuario del Hotel]] · [[Contrato]] |
| Quality | [[Operador de QA]] · [[Manager de QA]] · [[Indicador de Calidad]] · [[Métricas y KPIs por Departamento]] |
| Catalogs | [[Zonas]] · [[Posiciones]] · [[Departamentos del Hotel]] · [[Modalidades de Contratación]] |
| Operations (handoff) | [[Inspector]] · [[Reclutadora]] · [[Requisición]] · [[Flujo de Requisición]] · [[Self-Pick de Requisiciones]] · [[Schedule]] · [[Timesheet]] · [[Facturación al Hotel]] |
| Operational Status Indicators | [[Semáforo de Requisición]] · [[Semáforo de Urgencia de Requisición]] · [[Pool de Colaboradores]] |

---

## Related Simulations

- [[Simulación - Punto de Vista de Inspección]] — Continues the Hotel Costa Esmeralda story from the perspective of Inspector Daniel Ortega, who receives the operational handoff after the conversion to client.
- [[Simulación - Punto de Vista del Hotel]] — Narrates the full cycle of a hotel as a client, including the commercial phases detailed here from the Sales side.
- [[Simulación - Punto de Vista de Reclutamiento]] — Covers the staffing process that activates once the hotel generates its first requisition at Orange status.
- [[Simulación - Ciclo de Vida del Colaborador]] — Traces the states of the associate assigned to the hotel, from entry into the Pool through daily operations.
