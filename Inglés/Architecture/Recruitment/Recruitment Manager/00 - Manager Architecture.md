---
tags:
  - arquitectura
  - rol/manager-reclutamiento
aliases:
  - Recruitment Manager Architecture
  - Recruitment Manager Wireframe
---

# Architecture — Recruitment Manager

Wireframe of the Oranje platform for the [[Recruitment Manager|Recruitment Manager]] role. Defines the entry flow, global header, module sidebar and the detail of each module they have access to.

> [!info]
> The Manager **does not distribute requisitions in the normal flow** (approved Self-Pick model). Requisitions arrive in the system and Recruiters and Group Leaders take them freely according to their capacity. The Manager only intervenes in **special cases** (escalations, absences, VIP requisitions, balancing between groups, correction).

> [!important]
> **Main functions of the Manager:**
> 1. Manage the team (create Group Leaders and Recruiters).
> 2. Resolve problems and escalations.
> 3. Supervise the Group Leaders.
> 4. Consult and add to the Blacklist (the Black ban is permanent; disputes are resolved by the Zone Inspector).
> 5. View global metrics of the Recruitment module.
> 6. Take requisitions exceptionally (special case).

## N0 — Start

```
PLATAFORMA ORANGE
        │
        ▼
LOGIN / AUTORIZACIÓN
        │
        ▼
ROL IDENTIFICADO / MANAGER DE RECLUTAMIENTO
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
- Role: Recruitment Manager

**My team**
- Group Leaders in charge (count)
- Total Recruiters (count)
- Zones covered

**My global metrics**
- Global coverage of the module
- Pending requisitions (untaken)
- Pending escalated cases
- Module Quality Indicator

🚪 Log out

### 🔍 SEARCH (global)

- Requisitions by ID
- Collaborators by name / document / phone
- Hotels by name
- Blacklisted individuals
- Recruiters and Leaders of the module
- Incident / dispute cases

### 🔔 NOTIFICATIONS (bell with badge)

- 🚨 Case escalated by a Leader or Inspector
- 🔴 Requisition in Red urgency untaken (>X hours)
- ⚫ Blacklist approval request
- 📊 Report received from a Group Leader
- 🛡️ Quality Indicator dropped
- 💼 VIP requisition authorized

---

## N1 — SIDEBAR (Manager modules)

```
SIDEBAR
   ├─ DASHBOARD
   ├─ RECLUTAMIENTO            (Pool + Entrevistas global del depto + apoyo operativo)
   ├─ REQUISICIÓN              (vista global + intervención excepcional + semáforos)
   ├─ BLACKLIST                (global consult + add)
   ├─ MI EQUIPO                ← exclusivo (Líderes + Reclutadoras: gestión + supervisión)
   ├─ INCIDENCIAS              ← exclusivo (recibe escalamientos)
   └─ REPORTES                 (recibe de Líderes + genera globales)
```

---

## 📊 DASHBOARD Module

- Global KPIs of the module
- Critical requisitions (untaken for a long time)
- Top performers / Leaders with low coverage
- Pending escalated cases
- Quality Indicator

---

## 🧑‍🤝‍🧑 RECRUITMENT Module (global department view)

### Collaborator Pool
- Full access to the entire department Pool (same tabs/filters as Recruiter and Leader).
- Manager's additional filters: by Group Leader, by responsible Recruiter.

### 📝 Interviews (sub-view — global view with "who did what" traceability)

> [!info]
> The Manager **rarely recruits personally** (exceptional case). Their main use of this sub-view is to **audit and supervise the entire department**: viewing the full recruitment history, identifying Recruiters or Leaders with stuck candidates, detecting patterns (high abandonment in a certain zone, slow validations, etc.).

**Top toggle**
- 🌐 **Global Department History** *(default)* — ALL interviews done by any Recruiter or Leader in the department.
- 👤 **My Interviews** — only those the Manager did personally (special case — RF-EXC-01 when intervening directly).

**Internal tabs (candidate status)**
- 🟠 **Pending App** — Phase 1 done, waiting for the collaborator to complete Phase 2.
- 🟡 **Pending Validation** — the collaborator completed Phase 2 + Phase 3, waiting for validation.
- ⚪ **Drafts** — interviews started but not saved.
- ⚫ **Abandoned** — candidates with >X days without completing the app.
- ✅ **Validated** — history of those who already moved to the Pool.

**Filters (cross-cutting — broader than Leader/Recruiter)**
- **Group Leader** — filters by the entire group of a specific Leader.
- **Recruiter** — filters by who conducted the interview.
- **Zone** ([[Core/Catalogs/Zones|Zones]])
- **Position** ([[Core/Catalogs/Posiciones|Positions]])
- Anticipated modality
- Days in status (slider)
- Interview date (range)
- Source (referral / direct application / active recruitment)
- Search by name / document / phone

**Candidate detail (on click)**
- **Header:** photo + name + phone + anticipated position + visual timeline `Phase 1 ✅ → Phase 2 🟡 → Phase 3 ⚪ → Validation`.
- **Responsibles traceability** (always visible):
  - 👤 **Responsible Recruiter** (who did Phase 1).
  - 🧑‍🏫 **Group Leader** the Recruiter belongs to.
  - 👁️ **Validator** (who validated / rejected Phase 2, if already done).
- **Days since interview** with color indicator (🟢 <3 · 🟡 3-7 · 🔴 >7).
- **Internal tabs:**
  1. **Phase 1 Data** — read-only (the Manager does not edit routinely — only in exceptional intervention).
  2. **Phase 2 Data** — completed by the collaborator in the app. Read-only.
  3. **Phase 3 Data** — emergency data. Read-only.
  4. **Communication History** — when the link was sent, reminders, opened the app.
  5. **Documents** — ID, photos, receipts.
  6. **File Log** — all actions (who, when, what they did).

**Actions (supervisor profile)**
- 👁️ **View detail** of the candidate.
- 📊 **View performance of the responsible person** (Recruiter or Leader — leads to global individual metrics, RF-23).
- 💬 **Comment on the file** (visible to the responsible Recruiter and Leader).
- 🚨 **Request action** from the Recruiter or the Leader (e.g. "resend the link, it's been 8 days").
- 📤 **Reassign candidate to another Recruiter / another group** (exceptional — Recruiter or Leader unavailable, balancing).
- ✅ **Validate sign-up under intervention** (exceptional — RF-EXC, kept in an auditable log).
- ❌ **Reject sign-up** with reason (exceptional).
- 🚫 **Mark as abandoned** (exceptional — normally done by the Recruiter or Leader).
- 📥 **Export** filtered list (CSV / PDF) for the Manager's own tracking and supervision.

**KPIs visible in the header (global view)**
- Total candidates in process (department).
- Phase 1 → Pool conversion rate (current month vs. previous month).
- Average days per stage.
- Top 3 Recruiters by validated candidates.
- Bottom 3 Recruiters with stuck candidates (>7 days).

### + New Collaborator (modal — exceptional operational support)
Same form as Recruiter / Leader. The Manager only uses it when intervening directly (recorded as an exception).

> [!important]
> Routine validation / rejection / editing is done by the Recruiter who originated the interview (or their Group Leader in their absence). The Manager intervenes only as an **auditor or exceptional executor**, and any action of theirs is kept in an auditable log (rule RR-12).

---

## 📋 REQUISITIONS Module (global view, exceptional intervention)

- List by status (Authorized / In process / Covered / Partial)
- Filters by urgency, position, hotel, zone, time in queue

> [!info]
> **Collaborative model (RR-15).** A requisition can have **several participating recruiters** working on it at the same time (there is no single owner). Taking an already-taken requisition does NOT transfer or block it: the recruiter **joins as an additional participant** and the coverage progress is **shared**. The Manager sees all active recruiters of each requisition and can add one without displacing the existing ones.

- Exceptional actions:
  - 🎯 Take the requisition personally (special case — registered as a participant; others can join)
  - 👤 Assign manually (VIP, balancing, absence) — with justification
  - ➕ Add a recruiter to the requisition (adds them as a participant without displacing the existing ones — collaborative model)
  - Reassign to another Recruiter (transfer) or keep the original one as a support participant
  - 📜 View the requisition history (chronological timeline: who took / joined / left, who assigned/unassigned each collaborator, with date and author — RR-16)
  - Force a status light change (with log)

---

## ⚫ BLACKLIST Module (global consult + add)

- 👁️ Consult the full department Blacklist
- ✅ Add to Blacklist (with reason and evidence — same as any Recruitment role)

> [!note]
> The ban (Black status) is **permanent**: there is no removal or rehabilitation. Disputes (Red status of the collaborator) are resolved by the **Zone Inspector**, not the Manager.

---

## 👥 MY TEAM Module (Manager-exclusive)

Sub-views:
- 👥 Group Leaders (list + detail + metrics + nested group)
- 🧑 Recruiters (list + detail + Leader they belong to)

Management actions:
- ➕ Create Leader / Recruiter
- 📝 Edit user
- 🔁 Move Recruiter to another Leader
- ⏸️ Mark as inactive / vacation / termination

Supervision actions:
- 📊 View detailed performance
- 📝 Request report
- 🚨 Escalate to Management

---

## ⚠️ INCIDENTS / DISPUTES Module

- Open / resolved cases
- ✅ Resolve case (final decision with reason)
- 🚨 Escalate to Management
- Close case

---

## 📈 REPORTS Module

- Reports received from Leaders
- Generate global report
- Export (CSV / PDF / Excel)
- Schedule recurring delivery

---

## Key differences vs Group Leader

| Aspect | Group Leader | Recruitment Manager |
|---|---|---|
| Takes requisitions (Self-Pick) | Yes | Yes but exceptional |
| Recruitment (Pool + Assignment) | Operational access | Full access |
| Blacklist | Consult + Add | Global consult + Add (same as any role) |
| My Group / My Team | Sees Recruiters in the group | Sees Leaders + Recruiters + management |
| Resolve disputes (Inspector) | ❌ | ❌ (resolved by the Zone Inspector) |
| Reports | Generates and sends | Receives + generates global |

---

## Related

- [[Recruitment Manager|Recruitment Manager]] (role definition)
- [[Recruitment/Recruiters Group Leader|Recruiters Group Leader]]
- [[Recruiter|Recruiter]]
- [[Recruitment/Recruitment|Recruitment]]
- [[Core/Modules/Blacklist|Blacklist]]
- [[QA/QA|QA]]
