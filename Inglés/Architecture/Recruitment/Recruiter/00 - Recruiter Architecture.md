---
tags:
  - arquitectura
  - modulo/reclutamiento
aliases:
  - Recruiter Architecture
  - Recruiter Wireframe
  - Recruiter Architecture
---

# Architecture — Recruiter

Oranje platform wireframe for the [[Recruiter|Recruiter]] role. It defines the entry flow, global header, modules sidebar, and the detail of each module it has access to.

> [!info]
> The Recruiter is the **base operational role** of the [[Recruitment/Recruitment|Recruitment]] module. It executes the entire cycle of recruiting, validating, and assigning collaborators to hotels.

> [!important]
> **Collaborative Self-Pick model (RR-15):** requisitions arrive in the system and the Recruiter **takes them freely** from the Authorized inbox. Nobody assigns requisitions to her — she decides what she takes and when. Taking a requisition **does NOT block the others**: a single requisition can have **several participating recruiters** working it at the same time. Taking one that is already taken means **joining** as an additional participating recruiter; nobody loses the requisition.

## N0 — Start

```
ORANGE PLATFORM
        │
        ▼
LOGIN / AUTHORIZATION
        │
        ▼
ROLE IDENTIFIED / RECRUITER
        │
        ▼
MODULES / SIDEBAR
```

---

## HEADER (present throughout the app)

### 👤 USER PROFILE (dropdown)

**My information**
- Full name + photo
- Email + phone
- Role: Recruiter

**My Group Leader**
- Name of the Leader she reports to
- Group she belongs to

**My assigned zone**
- E.g. "Centro Zone"

**My metrics (current month)**
- Covered requisitions
- Personal coverage rate
- Approved candidates
- Average assignment time
- Active temporary assignments

**Settings**
- Change password
- Notification preferences

🚪 Log out

### 🔍 SEARCH (global)

**What can be searched**
- Requisitions by ID or number
- Collaborators by name / document / phone
- Hotels by name
- Banned people in [[Core/Modules/Blacklist|Blacklist]]

**How it works**
- Live results grouped by type
- Each result leads to the corresponding detail
- Shortcut: `/` or `Ctrl+K`

**Quick filters**
- Type (req · collaborator · hotel · blacklist)
- Recent search (last 5)

### 🔔 NOTIFICATIONS (bell with badge)

**By event type**
- 📋 New requisition available to take
- 👤 Candidate completed sign-up in App → ready to validate
- 🔴 One of my requisitions entered Red urgency (<72h)
- ⚫ Blacklist updated
- 🟢 My requisition reached 100% coverage
- 🩷 Assigned collaborator moved to Stand-by (Pink) by the hotel
- 🔴 Assigned collaborator was reported (Red) by the hotel
- ⬜ Assigned collaborator had a work-related accident (Gray)
- 📊 My Group Leader requested info for a report

**States**
- 🟠 Unread (counted in the badge)
- 🟢 Read

**Actions**
- Click → takes you to the related module
- Mark as read
- Mark all as read

---

## N1 — SIDEBAR (Recruiter Modules)

```
SIDEBAR
   ├─ DASHBOARD
   ├─ RECRUITMENT     (Pool + Interviews + New Collaborator)
   ├─ REQUISITION     (Authorized Queue + My Taken — Self-Pick)
   └─ BLACKLIST       (lookup + add)
```

---

## 📊 DASHBOARD Module

### Personal KPIs
- Requisitions taken (month)
- Open requisitions in process
- Urgent requisitions (Red) under my responsibility
- Candidates pending validation
- Critical alerts

### Summary views
- **Pool by position:**
  - Housekeeper (8 available)
  - Hoseman (3 available)
  - Chef (1 available)
- **My Requisitions (summary):**
  - Req #001 · Housekeeper · 🔴 Red (in process)
  - Req #002 · Chef · 🟡 Yellow (in process)
  - Req #003 · Hoseman · 🟢 Green (covered)
  - [See all →] navigates to Requisitions
- **Inbox of available to take:**
  - Short list of the authorized untaken requisitions (sorted by urgency)

### Action Inbox
- Latest Blacklist updates
- Candidates who completed the App → Validate

### Quick actions
- New Candidate
- Search in Pool
- Check Blacklist
- Take requisition (takes you to the available inbox)

---

## 🧑‍🤝‍🧑 RECRUITMENT Module

### Collaborator Pool

**List** (states of the [[Collaborator Status Light|Collaborator Status Light]])
- ⚪ White — Pre-assignment
- 🟢 Apple Green — Day 1-2 onboarding
- 🔵 Light Blue — Day 3+ uniform delivery
- 🟠 Orange — Permanent
- 🟢 Strong Green — Available
- 🟡 Yellow — Available volunteer
- 🟤 Brown — Temporary assignment
- 🩷 Pink — Stand-by
- 🟣 Purple — Did not return
- 🔴 Red — Reported
- ⚫ Black — Blacklist
- ⬜ Gray — Injured

**Filters**
- Position ([[Core/Catalogs/Posiciones|Positions]]: Housekeeper, Hoseman, Chef, Laundry)
- Zone ([[Core/Catalogs/Zones|Zones]]: Centro, Sur, Este, Oeste, Noroeste, Sureste)
- Modality ([[Core/Catalogs/Employment Types|Modalities]]: Full time, Part time, Temporary, On request)
- English level ([[Core/Catalogs/English Levels|English]]: Basic, Intermediate, Advanced, Conversational)
- Search by name / document / phone

**Detail**
- Personal data: name, document, phone, address
- Work data: position, modality, English, experience
- Collaborator's current status light
- History: hotels where they have worked
- Documents: SSN, ITIN, uploaded PDFs

**Actions**
- Assign to requisition (Strong Green / Yellow → Brown for temporary assignment)
- Edit collaborator (Pending)
- Validate sign-up in App (when the collaborator completed their self-registration)
- Enable access to panels
- View assignment history
- Check whether they are in Blacklist

### 📝 Interviews (sub-view — candidates in process)

> [!info]
> This sub-view tracks the candidates who **already went through the interview (Phase 1)** but are **not yet in the Pool**. It answers the question that previously only a notification answered: *who is in the queue? who has gone days without completing the app? how many are ready to validate?*.

**Internal tabs (candidate status)**
- 🟠 **Pending App** — Phase 1 done, waiting for the collaborator to download the app and complete Phase 2.
- 🟡 **Pending Validation** — the collaborator completed Phase 2 + Phase 3 in the app and is waiting for the Recruiter to validate (RF-08).
- ⚪ **Drafts** — interviews started but not saved (timeout / accidental close).
- ⚫ **Abandoned** — candidates with >X days without completing the app (configurable threshold).
- ✅ **Validated (last 30 days)** — recent history of those who already moved to the Pool.

**Filters (cross-cutting across all tabs)**
- Position ([[Core/Catalogs/Posiciones|Positions]]: Housekeeper, Hoseman, Chef, Laundry)
- Zone ([[Core/Catalogs/Zones|Zones]]: Centro, Sur, Este, Oeste, Noroeste, Sureste)
- Expected modality ([[Core/Catalogs/Employment Types|Modalities]])
- Days in status (slider: 1-3 / 4-7 / >7 — those over 7 with a visual alert)
- Interview date (range)
- Source (referral / direct application / active recruitment)
- Search by name / document / phone

**Candidate detail (on click)**
- **Header:** photo + name + phone + expected position + visual timeline `Phase 1 ✅ → Phase 2 🟡 → Phase 3 ⚪ → Validation`.
- **Days since interview** with color indicator (🟢 <3 · 🟡 3-7 · 🔴 >7).
- **Internal tabs:**
  1. **Phase 1 Data** — captured by the Recruiter during the interview (editable).
  2. **Phase 2 Data** — completed by the collaborator in the app (SSN, ITIN, position, English, experience, transportation, modality). Read only. Flags what is missing.
  3. **Phase 3 Data** — emergency data (contact, blood type, allergies). Read only.
  4. **Communication history** — when the link was sent, reminders, app opened, etc.
  5. **Documents** — ID card, uploaded photos, proofs.

**Actions**
- ✏️ **Edit Phase 1 data** (capture correction).
- 📩 **Resend App link** (Pending App).
- 🔔 **Send reminder** (Pending App with >3 days).
- ✅ **Validate sign-up** (Pending Validation — triggers RF-08, moves to the Pool with Strong Green status).
- ❌ **Reject sign-up** (Pending Validation — with mandatory reason).
- 🚫 **Mark as abandoned** (Pending App with >X days without activity).
- 📞 **Call / Contact** (any tab).
- 🗑️ **Delete draft** (Drafts only).

### + New Collaborator (modal form)
**Data captured in the initial interview (Phase 1):**
- Full name
- Date of birth (the **age is calculated automatically** from the date; it is not captured)
- Gender
- Phone
- Email
- Address

> [!info]
> The Phase 1 sign-up does NOT request a document / ID or uploading an ID card. The collaborator completes documents in the app (Phase 2).

> [!info]
> After creating the candidate, a link is sent to complete **Phase 2** (App sign-up: SSN, ITIN, position, English, experience, transportation, modality) and **Phase 3** (emergency data: contact, blood type, allergies). The candidate stays visible in the **Interviews → Pending App** sub-view while completing the process, and migrates to **Pending Validation** when finished.

---

## 📋 REQUISITIONS Module

### Sub-views

**🟢 Authorized Inbox (available to take)**
- List of all the requisitions that the [[Hotel/Area Manager|Area Manager]] approved.
- Any Recruiter or Leader can **take** the one she wants (collaborative Self-Pick, RR-15). Taking **does NOT block the others**.
- An already-taken requisition stays visible here with the tag **"Shared · N recruiters"**: taking it means **Joining** as an additional participating recruiter.
- Sorted by urgency (Red first) and time in queue.

**🟡 My Requisitions (the ones I took or participate in)**
- The requisitions that **I took** OR in which **I participate** alongside other recruiters (collaborative model — there is no single owner).
- Shared ones show the tag **"Shared · N recruiters"**.
- By sub-status:
  - 🟡 In process (one or several recruiters assigning collaborators)
  - 🔵 Covered (100%)
  - 🔴 Partial (closed with shortfalls)
  - 📂 All

### Filter
- Urgency (🔴 🟡 🟢) — from the [[Requisition Urgency Status Light|Requisition Urgency Status Light]]
- Position
- Hotel
- Zone
- Status
- Search by ID

### Detail
- Header (hotel, dates, urgency)
- **Active recruiters on this requisition** (RF-40) — list of all participating recruiters working it right now (role + name), with the tag "Shared · N recruiters". Coverage progress is shared among all of them.
- Requested positions (with [[Requisition Positions Status Light|Requisition Positions Status Light]])
- Hotel Schedule (context)
- Collaborators already assigned (those assigned by **any** participating recruiter, with who assigned them)

### Requisition history (RF-41)
- **Immutable** chronological timeline with the **actor** of each event (role + name) and timestamp.
- Records: who took it / joined, who left, who assigned/unassigned which collaborator to which position, who closed it.
- Visible to all participating recruiters, the [[Recruitment/Recruiters Group Leader|Group Leader]] and the [[Hotel/Area Manager|Area Manager]].

### Actions
- **🎯 Take requisition** *(from the Authorized inbox — moves to My Requisitions)*
- **🤝 Join the requisition** *(when there are already other participating recruiters — I join as an additional recruiter without displacing anyone, RF-39)*
- **👤 Assign collaborator** (opens the Pool filtered by position/zone/English; the lock is at the position/slot level: two recruiters do not assign the same collaborator to the same position)
- **🔄 Temporary assignment** (Strong Green/Yellow → Brown transition)
- **📜 View history** of the requisition (chronological timeline with actor — RF-41)
- Mark as covered (when all positions are at 100%)
- Mark as partial (close with shortfalls)
- Report a problem (escalates to the [[Recruitment/Recruiters Group Leader|Group Leader]])
- Leave the requisition (removes only me; it stays **In process** if other recruiters remain; does not reset what others assigned; returns to **Authorized** only when the **last** recruiter leaves)

> [!important]
> Key difference: the Recruiter **takes** requisitions freely and **works** them herself. She does NOT distribute to anyone (she has no group under her charge).

---

> [!info]
> **Hotel Schedule** is not a Recruiter module — it is a contextual view of the Hotel module that is consulted during the assignment process (inside the Recruitment module). It lets you see schedules and vacant positions before assigning a collaborator.

---

## ⚫ BLACKLIST Module

### List
- All banned people
- By reason (3 no-shows, dispute, serious misconduct)

### Filters
- Search by name / document
- By reason
- By blacklist entry date
- By zone

### Detail
- Collaborator info
- Ban reason
- Entry date
- Who proposed it

> [!warning]
> The Recruiter **CANNOT** add/remove from Blacklist — that action is exclusive to the [[Recruitment Manager|Recruitment Manager]].
> **Mandatory lookup before each recruitment** (rule of the [[Recruitment Flow|Recruitment Flow]]) — to avoid re-recruiting someone banned.

---

## Recruiter operational flow

```
1. Login → Dashboard
   │
   ▼
2. I see the Authorized Requisitions inbox (untaken)
   │
   ▼
3. I take a requisition I can cover
   │
   ▼
4. I review the hotel Schedule to understand the week
   │
   ▼
5. I go to the Pool, search candidates, check Blacklist
   │
   ▼
6a. If the candidate does not exist:
      → I create a new Collaborator (Phase 1: interview)
      → I send them a link for Phase 2 (App sign-up)
      → The candidate appears in Interviews → Pending App
      → When they complete it, it migrates to Pending Validation and I get a notification
      → I go to Interviews → Pending Validation, validate and enable access
   │
6b. If the candidate exists in the Pool (Strong Green / Yellow):
      → I assign them directly to the position
   │
   ▼
7. I repeat until all positions are covered
   │
   ▼
8. I mark the requisition as Covered (100%) or Partial
```

### Subsequent events I monitor
- **Day 1:** [[Inspector]] verifies the collaborator's arrival (Strong Green → Apple Green).
- **Day 3:** Inspector delivers the uniform (Apple Green → Light Blue).
- **Day 7:** System marks as Orange (Permanent) automatically.
- **Reports:** if the hotel reports the collaborator (Red) or if they have a work-related accident (Gray), I get a notification.

---

## Key differences vs Group Leader and Manager

| Aspect | Recruiter | Group Leader | Manager |
|---|---|---|---|
| Takes requisitions | ✅ freely | ✅ freely | ✅ exceptional |
| Distributes to others | ❌ | ❌ (self-pick model) | ❌ |
| Create collaborator | ✅ | ✅ | ✅ |
| Validate App sign-up | ✅ | ✅ | ✅ |
| Assign to Schedule | ✅ | ✅ | ✅ |
| My Group / My Leaders | ❌ | ✅ My Recruiters | ✅ My Leaders |
| Formal reports | ❌ | ✅ | ✅ |
| Approve/remove Blacklist | ❌ | ❌ | ✅ exclusive |
| Team management (role creation) | ❌ | ❌ | ✅ exclusive |

---

## General ASCII diagram of the wireframe

```
╔══════════════════════════════════════════════════════════════╗
║                       ORANGE PLATFORM                        ║
║                              │                                ║
║                              ▼                                ║
║                   LOGIN / AUTHORIZATION                       ║
║                              │                                ║
║                              ▼                                ║
║                    ROLE: RECRUITER                            ║
╚══════════════════════════════════════════════════════════════╝
                                │
                                ▼
┌──────────────────────────────────────────────────────────────┐
│ HEADER:  [👤 Profile]   [🔍 Search]   [🔔 Notifications]     │
└──────────────────────────────────────────────────────────────┘
        │
        ▼
┌──────────────┬───────────────────────────────────────────────┐
│  SIDEBAR     │              WORK AREA                        │
│              │                                               │
│ 📊 Dashboard │  Personal KPIs · Pool · My req · Inbox       │
│ 🧑 Recruit.  │  Pool · Interviews · New Collaborator (P1)    │
│ 📋 Requisit. │  Authorized Inbox · My taken · Assign         │
│ ⚫ Blacklist │  Lookup · Reasons · History                   │
└──────────────┴───────────────────────────────────────────────┘
```

---

## Related

- [[Recruiter|Recruiter]] (role definition)
- [[Recruitment/Recruiters Group Leader|Recruiters Group Leader]]
- [[Recruitment Manager|Recruitment Manager]]
- [[Recruitment/Recruitment|Recruitment]]
- [[Recruitment Flow|Recruitment Flow]]
- [[Core/Modules/Requisition/Requisition|Requisition]]
- [[Core/Modules/Collaborator Pool|Collaborator Pool]]
- [[Core/Modules/Blacklist|Blacklist]]
- [[Core/Modules/Schedule|Schedule]]
- [[Collaborator Status Light|Collaborator Status Light]]
- [[Requisition Status Light|Requisition Status Light]]
- [[Inspector]] (verifies arrival and uniform of the collaborators I assign)
- [[00 - Group Leader Architecture|Group Leader Architecture]]
- [[00 - Manager Architecture|Manager Architecture]]
