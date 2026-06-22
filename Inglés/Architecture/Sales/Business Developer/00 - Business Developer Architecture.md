---
tags:
  - arquitectura
  - modulo/ventas
aliases:
  - Business Developer Architecture
  - Business Developer Wireframe
  - BD Architecture
---

# Architecture — Business Developer (BD)

Oranje platform wireframe for the [[Sales/Roles/Business Developer|Business Developer]] role. Defines the entry flow, global header, module sidebar and the detail of each module it has access to.

> [!info]
> The Business Developer is the **base operational role** of the Sales department. It runs the commercial cycle: identifies prospects, makes cold visits, prepares proposals, follows up and manages rejections. Their BDC validates the terms and approves the final conversion.

> [!important]
> The BD **NEVER** approves the conversion to client — that action is **exclusive to the BDC** (rule RR-V-01). The BD prepares, proposes and negotiates, but the "final yes" is given by the BDC.

## N0 — Start

```
PLATAFORMA ORANGE
        │
        ▼
LOGIN / AUTORIZACIÓN
        │
        ▼
ROL IDENTIFICADO / BUSINESS DEVELOPER (BD)
        │
        ▼
MÓDULOS / SIDEBAR
```

---

## HEADER (present throughout the app)

### 👤 USER PROFILE (dropdown)

**My information**
- Full name + photo
- Email + phone
- Role: Business Developer (BD)

**My assigned BDC**
- Name of the BDC they report to
- Zone / routes in charge

**My territory**
- Assigned routes
- Operational zones
- Number of active prospects

**My metrics (current month)**
- Prospects identified
- Proposals sent
- Conversions (active clients)
- Personal conversion rate
- Rejections managed

**Settings**
- Change password
- Notification preferences

🚪 Log out

### 🔍 SEARCH (global)

**What can be searched**
- Prospect hotels by name / city / zone
- Active client hotels
- Proposals sent
- T&C documents

**How it works**
- Live results grouped by type
- Shortcut: `/` or `Ctrl+K`

### 🔔 NOTIFICATIONS (bell with badge)

**By event type**
- 📩 Hotel responded to the proposal
- ✅ The BDC approved the conversion of my prospect → active client
- 🔴 Hotel rejected the proposal
- ☕ My BDC unblocked a Brown case
- ⚫ Active client moved to Black (paused)
- 📊 Report request from the BDC
- 🎯 Scheduled follow-up reminder

**States**
- 🟠 Unread (counted in the badge)
- 🟢 Read

---

## N1 — SIDEBAR (Business Developer Modules)

```
SIDEBAR
   ├─ DASHBOARD
   ├─ PIPELINE             (Mis prospectos por status)
   ├─ MI TERRITORIO        (rutas + zonas + mapa)
   ├─ PROPUESTAS           (Propuesta Personalizada)
   ├─ DOCUMENTOS T&C       (creación con BDC)
   └─ CLIENTES ACTIVOS     (referente comercial post-Naranja)
```

> [!note]
> The BD does **NOT** have a "My Team", "Executive Reports", or "Conversion" action module. Those belong to the BDC.

---

## 📊 DASHBOARD Module

### Personal KPIs of the month
- Prospects in each status of the Onboarding Status Light
- Proposals sent (Green)
- Hotels in negotiation (Yellow / Pink)
- Conversions closed (Orange)
- Personal conversion rate
- Rejections of the month
- Cold visits made

### Summary views
- **My prospects by status:** mini-pipeline with count per stage.
- **Upcoming follow-ups:** list of prospects that require contact (based on last contact and status).
- **Alerts:** prospects with no activity >X days.

### Quick actions
- ➕ Identify new prospect
- ➕ Register cold visit
- ➕ Prepare new Proposal
- 📞 Register contact attempt

### 🔄 How this module is used

When logging in, the BD arrives here. The first thing they look at are the personal KPIs of the month to have context on how their performance is going (how many prospects they identified, how many proposals they sent, how many were converted, their conversion rate).

Then they review **"Upcoming follow-ups"** — the system shows them the prospects that require contact today (based on their last contact and the status). If they see red alerts for prospects with no activity >7 days, they go straight to the detail from here.

If there is nothing urgent, they decide what to do with the **quick actions**: identify a new prospect, register a contact attempt they made offline, or start preparing a proposal. The Dashboard is their **daily entry point** — from here they move to Pipeline, My Territory or Proposals depending on what they need.

---

## 📋 PIPELINE Module (My Prospects)

### Sub-views (by status of the [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]])

- ⚪ **Gray** — Identified (no contact yet)
- 🔵 **Light Blue** — Contact + data collected
- 🟢 **Green** — Proposal sent
- 🟡 **Yellow** — In follow-up (T&C under construction)
- 🩷 **Pink** — Terms negotiation
- 🟠 **Orange** — Active client (post-conversion)
- 🔴 **Red** — Rejection
- ⚫ **Black** — Paused / inactive client
- 🟤 **Brown** — Stagnation (managed by the BDC)
- 📂 **All** — Full view of my territory

### Filters
- Status (one or several)
- Route / Zone
- Identification date (range)
- Days without contact
- Search by name / city

### Prospect detail
- **Header:** name, photo, address, main contact, current status, days in status.
- **Hotel data:** email, phone, contact, position, business need.
- **Contact history:** calls, emails, visits, results.
- **Associated documents:** Proposal sent, T&C draft.
- **Timeline:** status changes with date, author, comment.

### Actions
- ➕ **Identify prospect** *(creates record in Gray)*
- ✏️ **Edit hotel profile** *(Light Blue)*
- ➕ **Register cold visit**
- ➕ **Register contact attempt**
- ✏️ **Advance status** (Gray → Light Blue → Green → Yellow → Pink)
- 🔴 **Mark rejection (Red)** with reason
- ↩️ **Reactivate from Red** (returns to Light Blue)
- ☕ **Mark stagnation (Brown)** *(BDC handles the unblocking)*

> [!warning]
> The BD can **NOT** approve conversion, validate T&C, create Hotel User, unblock Brown, mark/reactivate Black. All of that belongs to the BDC.

### 🔄 How this module is used

Pipeline is the BD's **operations center**. Here they manage all their prospects along the Onboarding Status Light.

**When the prospect is new (Gray):** the BD enters the hotel detail and fills in the profile — email, phone, contact, position, business need. On saving, the system changes the status to **Light Blue** automatically and notifies the BDC. The timeline records the change with author and date.

**When the prospect is in Light Blue:** the BD registers cold visits and contact attempts each time they call or visit the hotel. Each attempt is logged in the prospect's contact history. Once they have enough information and the contact is warm, they leave the Pipeline and move to the Proposals module to prepare the Personalized Proposal.

**When the prospect is in Green (proposal sent):** the BD waits for a response from the hotel and follows up. If the hotel responds with interest, click **"Advance to Yellow"** → enter mandatory reason and comment → the status changes and notifies the BDC.

**If the hotel rejects:** click **"Mark Red"** → select reason from the catalog (Not interested / No budget / Another company / Other) + mandatory comment min. 30 characters. They can mark "Reactivate later" if they think the contact can be revived. Later, from the Red sub-view, they can click **"Reactivate"** → the status automatically returns to Light Blue (rule RR-V-07, NEVER returns to Gray).

**If the prospect stagnates** (no response after multiple attempts, change of contact, indecision): click **"Mark Brown"** → reason + notes for the BDC (min. 30 characters, this is the context the BDC needs to investigate). From there, **the BD loses control** of the prospect: the case moves to the BDC's Brown inbox, who investigates, provides a solution and reactivates (returns to Light Blue). Only then does the BD recover the case.

**When it reaches Pink:** the BD has already sent the T&C and is negotiating alongside the BDC. If the BDC approves the conversion, the prospect moves to Orange and disappears from the Pipeline (enters Active Clients).

> [!note]
> Each status change records **date, responsible and comment** in the prospect's timeline (rule RR-V-11). Nothing moves "silently".

---

## 🗺️ MY TERRITORY Module

### Main view
- **Interactive map** with my assigned routes and zones.
- **Pins by status** of the prospect at each location.
- **Side list** of prospects by route.

### Filters
- Route
- Zone
- Status
- Search by name

### Actions
- 👁️ View prospect detail
- ➕ Identify new prospect on the map
- 📍 Mark route of the day (visit planning)

### 🔄 How this module is used

My Territory is the module the BD uses **when going out to the field**. They mainly open it from mobile.

The first thing they see is the **map with their assigned routes and zones**, with colored pins according to the prospect's status at each location (Gray = recently identified, Light Blue = contact in progress, Green = proposal sent, etc.).

**At the start of the day** the BD uses **"Mark route of the day"** to plan visits: they select the prospects they are going to visit and the system suggests an efficient route order. This helps them optimize time and not forget any.

**During the visit**, if they detect a **new hotel** that was not registered, they click directly on the map at that location → the system captures **geolocation automatically** and opens the "Identify prospect" form with the zone pre-filled. They fill in the name and minimum data → the prospect remains in Gray ready to be worked on later.

**If they want to see the detail** of an existing prospect (to refresh the information before knocking on the door), they click its pin → enter the prospect detail from Pipeline. From there they can register the contact attempt they are going to make at that moment.

> [!info]
> My Territory and Pipeline are synchronized: any status change made from Pipeline is reflected on the map, and any prospect identified on the map appears in Pipeline.

---

## 📝 PROPOSALS Module

### Sub-views
- ✏️ **Drafts** — proposals under construction
- 📤 **Sent** — waiting for hotel response
- ✅ **Accepted** — the hotel showed interest (advanced to Yellow)
- ❌ **Rejected** — the hotel rejected (Red)
- 📂 **History**

### Actions
- ➕ **Prepare Personalized Proposal** (RF-V-04 — Green)
- 📤 **Send to hotel** (RF-V-05)
- ✏️ **Edit draft**
- 📥 **Export PDF**
- 📋 **Duplicate** (use as template for another prospect)

### Detail
- Destination hotel data
- Proposed services
- Prices and conditions
- Proposal validity
- State (draft / sent / responded)
- Send history

> [!info]
> The Personalized Proposal is prepared exclusively in **Green** status (RR-V-09). If the prospect is stagnant (Brown), the BDC will take the case to unblock it and enable a new proposal.

### 🔄 How this module is used

When a prospect is ready (Light Blue with complete profile and prior contacts made), the BD moves to Proposals to build the formal commercial offer.

**Create the proposal:** click **"➕ Prepare Personalized Proposal"** → select the destination hotel from the list of their prospects in Light Blue (hotels in other statuses do not appear) → fill in the proposed services from the catalog → set prices per service → write general conditions (min. 100 characters with the commercial terms) → define validity (future date). They can attach PDFs or supporting documents. Save as a **draft** and edit it freely as many times as they want.

**Send to hotel:** when the BD is satisfied with the proposal, click **"📤 Send to hotel"** → the system validates that it is complete (services + prices + conditions + validity) → sends an email to the hotel with the proposal attached → changes the prospect's status to **Green** automatically → locks that version of the proposal for editing (kept as history) → notifies the BD and the BDC.

**Reuse proposals:** if the BD wants to build a similar proposal for another hotel, they use **"📋 Duplicate"** on an existing one. The system creates a copy with the data pre-filled, and the BD only adjusts what is different for the new prospect. This greatly speeds up the work when there are standard proposals.

**If the hotel responds with interest:** that flow is managed from Pipeline (advance to Yellow). In Proposals the BD only sees that the proposal changed state to "Accepted".

**If the hotel rejects:** from Pipeline the BD marks Red. In Proposals the proposal remains as "Rejected" in the history — it can be consulted or duplicated if the prospect is reactivated later.

---

## 📄 T&C DOCUMENTS Module

### Sub-views
- ✏️ **Drafts** — T&C under construction
- ⏳ **Pending BDC validation**
- ✅ **Validated** (ready for Pink)
- 📂 **History**

### Actions
- ➕ **Create T&C Document** *(BD or BDC, in Yellow status)*
- ✏️ **Edit draft** of the T&C
- 📤 **Send to the BDC for validation**
- 👁️ **View BDC feedback**

### Mandatory T&C fields (RR-V-10)

| Field      |
| ---------- |
| Pay rate   |
| Bill rate  |
| Overtime   |
| Holidays   |
| Calendar   |

> [!warning]
> The BD does **NOT** validate or approve the T&C. They only create and edit it. The final validation belongs to the BDC (RR-V-15).

### 🔄 How this module is used

Once the hotel responds with interest to the Proposal (Yellow status), the BD builds the formal document that lays out the legal and economic basis of the agreement: the Terms and Conditions Document.

**Create the T&C:** click **"➕ Create T&C Document"** → fill in the **5 mandatory fields** (rule RR-V-10):
1. **Pay rate** — payment rate to the collaborator
2. **Bill rate** — billing rate to the hotel
3. **Overtime** — overtime rules
4. **Holidays** — paid holidays
5. **Calendar** — start and end of the work week

Optionally: validity, renewal, attachments. The T&C remains an **editable draft** while the BD builds it. If they have doubts, they can request **support from the BDC** from the document detail (the BDC enters and co-edits).

**Send to the BDC for validation:** when the T&C is complete, click **"📤 Send to the BDC for validation"** → the system validates that the 5 mandatory fields are filled → changes the document to the "Pending BDC validation" state → **locks the BD's editing** while it is pending → notifies the BDC in their inbox.

**Wait for the BDC's decision:**
- **If the BDC validates:** the BD receives the notification *"Your T&C was validated"* → the document remains as "Validated" → the BD can now advance the prospect to **Pink** (formal negotiation) from Pipeline.
- **If the BDC rejects with observations:** the BD receives a notification with the BDC's observations → the T&C returns to editable → the BD corrects according to the feedback and resends it.

> [!important]
> Without a validated T&C, the BD can NOT initiate Pink, and therefore the prospect can NOT reach conversion. The validated T&C is a **mandatory prerequisite** for the entire closing flow.

---

## 🏨 ACTIVE CLIENTS Module (commercial reference)

### Main view
- List of active clients (Orange status) in my territory.
- Commercial (not operational) data.
- Onboarding history (when it converted, applicable T&C, validity).

### Filters
- Route / Zone
- Conversion date
- Search by name

### Actions
- 👁️ **View client detail** (commercial data)
- 📞 **Register commercial contact** (courtesy visit, follow-up)

> [!important]
> Post-Orange, BD and BDC are **commercial references** without operational permissions (RR-V-12). They do NOT create requisitions, do NOT edit the hotel, do NOT manage personnel — that belongs to the Hotel and Recruitment departments.

### 🔄 How this module is used

After the BDC approves the conversion (Pink → Orange), the prospect disappears from the BD's Pipeline and **automatically appears in Active Clients**. From there the hotel is no longer a prospect: it is a client and operates with Recruitment, Inspection and the Hotel department. The BD becomes a **commercial reference** — Oranje's human contact with the client.

**What the BD does here:**
- **Consult the client:** sees commercial data (when it converted, applicable T&C, contract validity, originating BD, onboarding history). Read-only on the operational side.
- **Register commercial contact:** click **"📞 Register commercial contact"** → documents courtesy visits, follow-up calls or meetings to maintain the relationship. Logged in the client's history.

**What they can NOT do (RR-V-12):**
- ❌ Create requisitions (done by the hotel Supervisor)
- ❌ Edit the hotel (done by the Area Manager)
- ❌ Manage assigned personnel (done by Recruitment)
- ❌ Authorize anything

**If the client falls to Black:** if the BDC marks the client as Black (closure, pause, dispute), the BD receives a notification: *"Your client X moved to Black"*. **The BD does not intervene in the management** — that is exclusive to the BDC (RR-V-05). They are only informed.

**If the client is reactivated from Black:** it returns to the cycle from Light Blue as a prospect (RR-V-07). If the BDC reassigns that case to them, the BD recovers it in their Pipeline and starts the Sales cycle again.

---

## Key differences vs BDC

| Aspect | BD | BDC |
|---|---|---|
| Identify prospect (Gray) | ✅ | — |
| Create profile (Light Blue) | ✅ | — |
| Prepare Personalized Proposal | ✅ exclusive | — |
| Create T&C Document | ✅ | ✅ support |
| Validate T&C Document | ❌ | ✅ exclusive |
| Negotiate (Pink) | ✅ | ✅ |
| Create Hotel User | ❌ | ✅ exclusive |
| Approve conversion | ❌ | ✅ exclusive |
| Manage Red | ✅ | — |
| Unblock Brown | ❌ | ✅ exclusive |
| Manage Black | ❌ | ✅ exclusive |
| My Team (BDs in charge) | ❌ | ✅ exclusive |
| Executive reports | ❌ | ✅ exclusive |
| Visibility | My territory | Entire zone / routes in charge |

---

## General ASCII diagram of the wireframe

```
╔══════════════════════════════════════════════════════════════╗
║                       PLATAFORMA ORANGE                       ║
║                              │                                ║
║                              ▼                                ║
║                   LOGIN / AUTORIZACIÓN                        ║
║                              │                                ║
║                              ▼                                ║
║                   ROL: BUSINESS DEVELOPER                     ║
╚══════════════════════════════════════════════════════════════╝
                                │
                                ▼
┌──────────────────────────────────────────────────────────────┐
│ HEADER:  [👤 Perfil]   [🔍 Buscador]   [🔔 Notificaciones]   │
└──────────────────────────────────────────────────────────────┘
        │
        ▼
┌──────────────┬───────────────────────────────────────────────┐
│  SIDEBAR     │              ÁREA DE TRABAJO                  │
│              │                                               │
│ 📊 Dashboard │  KPIs personales · Próximos seguimientos      │
│ 📋 Pipeline  │  Mis prospectos por status                    │
│ 🗺️ Territorio│  Mapa · Rutas · Pines por status              │
│ 📝 Propuesta │  Borradores · Enviadas · Histórico            │
│ 📄 T&C       │  Borradores · Validación BDC                  │
│ 🏨 Clientes  │  Activos (referente comercial)                │
└──────────────┴───────────────────────────────────────────────┘
```

---

## Related

- [[Sales/Roles/Business Developer|Business Developer]] (role definition)
- [[Sales/Roles/Business Developer Coordinator|Business Developer Coordinator]]
- [[Sales/Sales|Sales]]
- [[Sales/Sales Rules|Sales Rules]]
- [[Sales/Hotel Onboarding/Hotel Onboarding|Hotel Onboarding]]
- [[Sales/Hotel Onboarding/Onboarding Flow|Onboarding Flow]]
- [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]]
- [[Sales/Hotel Onboarding/Concepts/Personalized Proposal|Personalized Proposal]]
- [[Sales/Hotel Onboarding/Concepts/Terms and Conditions Document|Terms and Conditions Document]]
- [[Hotel/Hotel|Hotel]] (post-Orange destination)
