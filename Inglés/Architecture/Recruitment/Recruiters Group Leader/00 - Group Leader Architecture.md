---
tags:
  - arquitectura
  - modulo/reclutamiento
aliases:
  - Group Leader Architecture
  - Recruiters Group Leader Wireframe
---

# Architecture — Recruiters Group Leader

Wireframe of the Oranje platform for the [[Recruitment/Recruiters Group Leader|Recruiters Group Leader]] role. Defines the entry flow, global header, module sidebar and the detail of each module they have access to.

> [!info]
> The Group Leader **executes all the operational functions of a [[Recruiter|Recruiter]]** and additionally supervises the group and reports to the [[Recruitment Manager|Recruitment Manager]]. Their architecture is that of a Recruiter + supervision and reporting modules.

> [!important]
> **Collaborative Self-Pick model (RR-15):** requisitions arrive at the system and the Leader (like any Recruiter) **freely takes** them from the Authorized inbox. Taking a requisition **does NOT block the others**: a single requisition can have **several participating recruiters** working it at the same time. Taking an already-taken one means **joining** as an additional participating recruiter; no one loses the requisition. Coverage progress is **shared** among all participating recruiters.

## N0 — Start

```
ORANGE PLATFORM
        │
        ▼
LOGIN / AUTHORIZATION
        │
        ▼
ROLE IDENTIFIED / RECRUITERS GROUP LEADER
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
- Role: Recruiters Group Leader

**My group**
- Group name
- Recruiters in charge (count)

**My assigned zone**
- e.g. "Centro Zone"

**My metrics (current month)**
- Group coverage
- Requisitions distributed
- Cases escalated to the Manager
- Average coverage time

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
- Recruiters in the group

**How it works**
- As you type, it shows live results grouped by type
- Each result takes you directly to the corresponding detail
- Keyboard shortcut: `/` or `Ctrl+K`

**Quick filters**
- Type (req · collaborator · hotel · blacklist · recruiter)
- Recent search (last 5)

### 🔔 NOTIFICATIONS (bell with badge)

**By event type**
- 📋 New requisition authorized by the hotel
- 👤 Candidate completed sign-up in App → ready to validate
- 🔴 Requisition at Red urgency (<72h)
- ⚫ Blacklist updated (new banned collaborator)
- 🛡️ Case escalated by QA
- 🟢 Group Recruiter covered requisition 100%
- ⚠️ Group Recruiter reported a problem
- 📊 Report request from the Manager

**States**
- 🟠 Unread (highlighted, counts in the badge)
- 🟢 Read

**Actions**
- Click → takes you to the related module
- Mark as read
- Mark all as read

---

## N1 — SIDEBAR (Leader's Modules)

```
SIDEBAR
   ├─ DASHBOARD
   ├─ RECRUITMENT     (Pool + Interviews — own + group's)
   ├─ REQUISITION     (Authorized queue + My taken/participated Requisitions — collaborative Self-Pick)
   ├─ BLACKLIST       (lookup + add)
   ├─ MY GROUP        ← Leader-exclusive (supervision)
   └─ REPORTS         ← formal module with its own screen
```

---

## 📊 DASHBOARD Module

### Personal KPIs (as a Recruiter)
- Own open requisitions
- Urgent requisitions
- Candidates pending validation
- Critical alerts

### Group KPIs (Leader extra)
- Aggregated group coverage (month)
- Group requisitions covered vs. pending
- Coverage rate per recruiter
- Pending escalated cases
- Active recruiters

### Summary views
- **Pool:** available collaborators by position
- **My Requisitions (summary):**
  - Req #001 · Housekeeper · 🔴 Red
  - Req #002 · Chef · 🟡 Yellowh
  - Req #003 · Hoseman · 🟢 Green
  - [View all →] navigates to My Requisitions

### Action Inbox
- Latest Blacklist updates
- Candidates who completed the App → Validate
- Group reports
- Pending approval requests

### Quick actions
- New Candidate
- Search in Pool
- Check Blacklist
- Take requisition from the inbox
- Generate report

---

## 🧑‍🤝‍🧑 RECRUITMENT Module

### Collaborator Pool

**List** (states of the [[Collaborator Status Light|Collaborator Status Light]])
- ⚪ White — Pre-assignment
- 🟢 Apple Green — Day 1-2 onboarding
- 🔵 Light Blue — Day 3+ uniform delivery
- 🟠 Orange — Fixed
- 🟢 Strong Green — Available
- 🟡 Yellow — Voluntarily available
- 🟤 Brown — Temporary assignment
- 🩷 Pink — Stand-by
- 🟣 Purple — Did not return
- 🔴 Red — Reported
- ⚫ Black — Blacklist
- ⬜ Gray — Injured

**Filters**
- Position ([[Core/Catalogs/Posiciones|Positions]]: Housekeeper, Hoseman, Chef, Laundry)
- Zone ([[Core/Catalogs/Zones|Zones]]: Centro, Sur, Este, Oeste, Noroeste, Sureste)
- Modality ([[Core/Catalogs/Employment Types|Modalities]]: Full-time, Part-time, Temporary, On-demand)
- English level ([[Core/Catalogs/English Levels|English]]: Basic, Intermediate, Advanced, Conversational)
- Search by name / document / phone

**Detail**
- Personal data: name, document, phone, address
- Work data: position, modality, English, experience
- Collaborator's current status light
- History: hotels where they have worked
- Documents: SSN, ITIN, uploaded PDFs

**Actions**
- Assign to requisition (Strong Green / Yellow → Brown)
- Edit collaborator (Pending)
- View assignment history
- Check if they are in the Blacklist

### 📝 Interviews (sub-view — dual mode: operational + supervision)

> [!info]
> The Leader uses this sub-view in **two ways**:
> 1. **Operational mode (minority):** when they themselves recruit as support, they see their own candidates in process (just like the Recruiter).
> 2. **Supervision mode (majority):** they see the **complete history of the group's recruitments** with detail of **who** (which Recruiter) did each one. It is the main tool for auditing and following up.

**Top toggle**
- 👤 **My Interviews** — only the ones the Leader did personally.
- 👥 **Group History** — ALL interviews done by the Leader + their Recruiters.

**Internal tabs (candidate state — common to both modes)**
- 🟠 **Pending App** — Phase 1 done, waiting for the collaborator to complete Phase 2.
- 🟡 **Pending Validation** — the collaborator completed Phase 2 + Phase 3, awaiting validation.
- ⚪ **Drafts** — interviews started but not saved.
- ⚫ **Abandoned** — candidates with >X days without completing the app.
- ✅ **Validated** — history of those who already moved to the Pool (configurable range).

**Filters (cross-cutting)**
- **Group Recruiter** *(only in Group History mode)* — who did the interview.
- Position ([[Core/Catalogs/Posiciones|Positions]])
- Zone ([[Core/Catalogs/Zones|Zones]])
- Expected modality
- Days in state (slider)
- Interview date (range)
- Origin (referral / direct application / active recruitment)
- Search by name / document / phone

**Candidate detail (on click)**
- **Header:** photo + name + phone + expected position + visual timeline `Phase 1 ✅ → Phase 2 🟡 → Phase 3 ⚪ → Validation`.
- **Responsible Recruiter** (who did the interview — Group Recruiter or the Leader themselves). 👈 *visible in Group History mode*.
- **Days since interview** with color indicator (🟢 <3 · 🟡 3-7 · 🔴 >7).
- **Internal tabs:**
  1. **Phase 1 data** — captured in the interview (editable only by whoever did it or by the Leader).
  2. **Phase 2 data** — completed by the collaborator in the app. Read-only.
  3. **Phase 3 data** — emergency data. Read-only.
  4. **Communication history** — when the link was sent, reminders, opened the app.
  5. **Documents** — ID card, photos, receipts.

**Actions**

*Common to both modes:*
- 👁️ **View detail** of the candidate.
- 📞 **Call / Contact** the candidate.
- 📩 **Resend App link** (if in Pending App).
- 🔔 **Send reminder** (Pending App with >3 days).

*"My Interviews" mode (operational — Leader recruiting):*
- ✏️ **Edit own Phase 1 data**.
- ✅ **Validate sign-up** of own candidates (RF-08).
- ❌ **Reject own sign-up** with reason.
- 🚫 **Mark as abandoned** own.

*"Group History" mode (supervision):*
- 📊 **View performance** of the Recruiter who did the interview (leads to individual metrics — RF-23).
- 💬 **Comment on the file** (remains visible to the responsible Recruiter).
- 🚨 **Request action from the Recruiter** (e.g. "resend the link, it has been 5 days without completing").
- 📤 **Reassign candidate to another Recruiter** in the group (case of an absent or overloaded Recruiter).
- ✅ **Validate sign-up on behalf of the group** (exceptional — if the original Recruiter is not available).

> [!important]
> The Leader can **view and supervise** ALL the group's interviews, but the routine editing/validation is done by the Recruiter who originated the interview. The Leader's intervention is for cases of follow-up, delay or absence.

### + New Collaborator (modal form)
- Full name
- Date of birth (the **age is calculated automatically** from the date; it is not captured)
- Gender
- Phone
- Email
- Address

> [!info]
> The sign-up does NOT request document / ID nor uploading an ID card. Those data are completed later by the collaborator in the app (Phase 2).

---

## 📋 REQUISITIONS Module (Self-Pick model)

### Sub-views

**🟢 Authorized Inbox (available to take)**
- List of all the requisitions that the [[Hotel/Area Manager|Area Manager]] approved.
- Any Recruiter or Leader can **take** the one they want (collaborative Self-Pick, RR-15). Taking it does **NOT block the others**.
- An already-taken requisition is still visible here with the label **"Shared · N recruiters"**: taking it means **Join** as an additional participating recruiter.
- Ordered by urgency (Red first) and age in the queue.

**🟡 My Requisitions (the ones I took or participate in)**
- The requisitions the Leader **took** OR in which they **participate** alongside other recruiters (collaborative model — there is no single owner).
- Shared ones show the label **"Shared · N recruiters"**.
- By sub-state:
  - 🟡 In process (one or several recruiters assigning collaborators)
  - 🔵 Covered (100%)
  - 🔴 Partial (closed with shortfalls)
  - 📂 All

### Filter
- Urgency (🔴 🟡 🟢) — from the [[Requisition Urgency Status Light|Requisition Urgency Status Light]]
- Position
- Hotel
- Zone
- State
- Search by ID

### Detail
- Header (hotel, dates, urgency)
- **Active recruiters on this requisition** (RF-40) — list of all participating recruiters working it right now (role + name), with the label "Shared · N recruiters". Coverage progress is shared among all.
- Requested positions (with [[Requisition Positions Status Light|Requisition Positions Status Light]])
- Hotel Schedule (context)
- Collaborators already assigned (those assigned by **any** participating recruiter, with who assigned them)

### Requisition history (RF-41)
- **Immutable** chronological timeline with the **actor** of each event (role + name) and timestamp.
- Records: who took it / joined, who left, who assigned/unassigned which collaborator to which position, who closed it.
- Visible to all participating recruiters, the Group Leader and the [[Recruitment Manager|Recruitment Manager]].

### Actions (collaborative Self-Pick)
- **🎯 Take requisition** *(from the Authorized inbox — moves to My Requisitions)*. If there are already other recruiters, the action is **Join** as an additional participating recruiter.
- **👥 View active recruiters** (RF-40) — who is working the requisition right now.
- **🕓 View history** (RF-41) — chronological timeline with the actor of each event.
- **👤 Assign collaborator** (opens Pool filtered by position/zone/English)
- **🔄 Temporary assignment** (Strong Green/Yellow → Brown transition)
- Mark as covered (when all positions are at 100%)
- Mark as partial (close with shortfalls)
- Report a problem (escalates to the Manager)
- **🚪 Leave the requisition** — removes only you; the requisition stays **In process** if other recruiters remain and does NOT reset what is already assigned. It only returns to **Authorized** when the **last** recruiter leaves.

> [!important]
> The Group Leader operates with the same collaborative Self-Pick model (RR-15) as the Recruiter: they **freely take** the requisitions they can cover and can **join** those already being worked by other recruiters. The difference from the Recruiter is that they **also supervise the group** ("My Group" module) and **send formal reports to the Manager** ("Reports" module).

---

## 👥 MY RECRUITERS GROUP Module *(Leader-exclusive)*

### List
- Recruiter · zone · number of active requisitions · % coverage
- e.g.: Ana López · Centro · 3 active · 85%
- e.g.: Beatriz Cruz · Norte · 2 active · 92%
- e.g.: Carlos Mena · Centro · 1 active · 70%

### Filters
- By zone
- By state (active / vacation / leave)
- By workload (high / medium / low)
- Search by name

### Detail (on click on a Recruiter)
- Basic data (name, contact, photo)
- Assigned zone
- Current workload (number of requisitions in process)
- Individual metrics (coverage, average time, escalated cases)
- History of covered requisitions
- Pending approval requests

### Actions
- View detailed workload
- Reassign requisition to another recruiter (RF-37)
- Mark availability (vacation / return) (RF-38)
- Generate individual report (links to the Reports module)

---

## 📈 REPORTS Module *(formal module — own screen)*

### Generate report
**Type selector**
- Group coverage
- Individual performance of Recruiters
- Escalated cases
- Average coverage time
- Requisition distribution

**Date range**
- Today / This week / This month / Custom

**Filters**
- By zone
- By position
- By hotel
- By recruiter

### Preview
- Numeric metrics
- Charts (bars, lines, donuts)
- Detailed table

### Actions
- 📤 Send to the [[Recruitment Manager|Recruitment Manager]]
- 📄 Export (CSV / PDF)
- 💾 Save as draft
- 📋 Schedule recurring delivery (weekly / monthly)

### History of sent reports
- List of previous reports
- Date · Type · Recipient · State (sent / read)
- Reopen / Reuse as template

---

> [!info]
> **Hotel Schedule** is not a Leader module — it is a contextual view of the Hotel module consulted during the assignment process (within the Recruitment module). Useful as context prior to taking or working a requisition.

---

## ⚫ BLACKLIST Module

### List
- All banned people
- By reason (3 absences, dispute, serious offense)

### Filters
- Search by name / document
- By reason
- By blacklist entry date
- By zone

### Detail
- Collaborator info
- Reason for the ban
- Entry date
- Who proposed it

### Actions
- ➕ **Add to Blacklist** (with mandatory reason and evidence) — available for **any role in the Recruitment department** (rule RR-03).
- 👁️ **Check** before each assignment (mandatory).

> [!warning]
> The Leader **CAN add** to the Blacklist (with reason and evidence), just like the Recruiter and the Manager.
> What they **CANNOT** do is **remove or resolve disputes** — that action is exclusive to the [[Zone Inspector]].
> The check is **mandatory** before each recruitment (rule of the [[Recruitment Flow|Recruitment Flow]]).

---

## Operational rules (user's final decision)

### Normal requisition flow (95%)
```
Area Manager authorizes requisition
        │
        ▼
Arrives at the Recruitment module
        │
        ▼
Group Leader receives it
        │
        ├── 🎯 Distribute to a Recruiter in the group  (majority)
        └── 👤 Take for myself                          (special cases)
        │
        ▼
Recruiter (or Leader) covers it with collaborators from the Pool
```

### Exception flow (5%) — the Manager intervenes
- Leader unavailable (vacation, leave, outside hours).
- VIP requisition / key hotel.
- Balancing between groups when one is saturated.
- Escalation due to Red urgency with no progress.
- Audit / correction of erroneous assignments.

### Key differences vs the Recruiter
| Aspect | Recruiter | Group Leader |
|---|---|---|
| Recruitment, Requisition, Blacklist | Full access | Full access (same functions) |
| Dashboard KPIs | Personal | Personal **+ group's** |
| Distribute requisitions | ❌ | ✅ main action |
| Take requisition for oneself | ✅ (only option) | ✅ (special case) |
| My Recruiters Group | ❌ | ✅ exclusive module |
| Formal reports | ❌ | ✅ exclusive module |
| Add to Blacklist | ✅ | ✅ (with reason and evidence) |
| Resolve Blacklist dispute | ❌ | ❌ (Zone Inspector) |

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
║              ROLE: RECRUITERS GROUP LEADER                   ║
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
│ 📊 Dashboard │  Personal + group KPIs                        │
│ 🧑 Recruit.  │  Pool · Interviews (own + group) · New        │
│ 📋 Requisit. │  Distribute · Take · Assign                   │
│ 👥 My Group  │  Recruiters · Metrics · Reassign              │
│ 📈 Reports   │  Generate · Send Manager · History            │
│ ⚫ Blacklist │  Lookup · Reasons · History                   │
└──────────────┴───────────────────────────────────────────────┘
```

---

## Related

- [[Recruitment/Recruiters Group Leader|Recruiters Group Leader]] (role definition)
- [[Recruiter|Recruiter]]
- [[Recruitment Manager|Recruitment Manager]]
- [[Recruitment/Recruitment|Recruitment]]
- [[Recruitment Flow|Recruitment Flow]]
- [[Core/Modules/Requisition/Requisition|Requisition]]
- [[Core/Modules/Collaborator Pool|Collaborator Pool]]
- [[Core/Modules/Blacklist|Blacklist]]
- [[Core/Modules/Schedule|Schedule]]
- [[Collaborator Status Light|Collaborator Status Light]]
- [[Requisition Status Light|Requisition Status Light]]
