---
tags:
  - arquitectura
  - modulo/hotel
aliases:
  - Area Manager Architecture
  - Area Manager Wireframe
  - Department Manager Architecture
---

# Architecture — Area Manager (Department Manager)

Wireframe of the Oranje platform for the [[Hotel/Area Manager|Area Manager]] role. Defines the entry flow, global header, module sidebar and the detail of each module it has access to.

> [!info]
> In **simple hierarchy** this role is the highest authority on the hotel side. In **extended hierarchy**, this role corresponds to the **Department Manager** (one per department: Housekeeping, Food, Maintenance, Front Desk), subordinate to the [[Hotel/General Manager|General Manager]]. The platform responsibilities are the same; only the scope changes (the whole hotel vs. its department).

> [!important]
> **Security layer:** this role is the only one that can **authorize** requisitions (Hotel rule). The Supervisor creates, but only the Area Manager sends the requisition to Recruitment.

## N0 — Start

```
PLATAFORMA ORANGE
        │
        ▼
LOGIN / AUTORIZACIÓN
        │
        ▼
ROL IDENTIFICADO / MANAGER DE ÁREA (o GERENTE DE DEPARTAMENTO)
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
- Role: Area Manager / Department Manager

**My hotel / department**
- Hotel name
- Assigned department *(extended hierarchy only — Housekeeping, Food, Maintenance, Front Desk)*
- Hotel zone

**My metrics (current month)**
- Authorized requisitions
- Positions covered / pending
- Active collaborators in my dept
- Timesheet Compliance Indicator (dept status)

**Settings**
- Change password
- Notification preferences

🚪 Log out

### 🔍 SEARCH (global)

**What can be searched**
- Requisitions by ID or number
- Assigned collaborators (by name / position)
- Schedule positions (by day / position)
**How it works**
- Live results grouped by type
- Shortcut: `/` or `Ctrl+K`

### 🔔 NOTIFICATIONS (bell with badge)

**By event type**
- 📋 New requisition created by the Supervisor → pending authorization
- ✅ Recruitment took an authorized requisition
- 👤 Collaborator assigned by Recruitment (enters my Schedule)
- 🟢 Requisition covered 100%
- 🔴 Collaborator reported / work accident in my dept
- ⏱️ Timesheet Compliance Indicator turned Red
- 🛡️ QA detected an incident in my dept

**States**
- 🟠 Unread (counts in the badge)
- 🟢 Read

---

## N1 — SIDEBAR (Area Manager Modules)

```
SIDEBAR
   ├─ DASHBOARD
   ├─ REQUISICIONES        (crear / autorizar / rechazar / ver historial del depto)
   ├─ SCHEDULE             (gestión semanal)
   ├─ TIMESHEET            (revisar ponches + generar QR)
   ├─ MI PERSONAL          (colaboradores asignados — Stand-by / Reportar)
   └─ ACCIDENTES           (reportar y dar seguimiento)
```

> [!note]
> The Area Manager does **NOT** have a Collaborator Pool module or a Recruitment module — those are on the Oranje side. It only sees the collaborators assigned to its hotel/dept.

---

## 📊 DASHBOARD Module

### Personal dept KPIs
- Requisitions pending authorization (red badge if >24h)
- Authorized requisitions in the coverage process
- Dept positions with partial coverage
- Active collaborators
- Collaborators on Stand-by (Pink)
- Reported collaborators (Red)
- Work accidents of the month
- Timesheet Compliance Indicator (status-lighted)

### Summary views
- **Pending Supervisor requisitions:** short list with CTA "Review and authorize".
- **Schedule of the week:** calendar view with covered / vacant positions.
- **Critical positions** (no collaborator assigned and start date < 72h).

### Quick actions
- Review pending requisition
- Generate / Renew QR
- View Schedule of the week
- Report collaborator

---

## 📋 REQUISITIONS Module

### Sub-views (by [[Requisition Status Light|Requisition Status Light]] state)

- 🟢 **Pending authorization** *(Apple Green — In preparation)* — created by my Supervisor, awaiting my review.
- 🟠 **Authorized** — already sent to Recruitment, awaiting them to take the requisition.
- 🟡 **In process** — Recruitment took them and is assigning collaborators.
- 🔵 **Covered** — at 100% coverage.
- 🔴 **Rejected** — returned to the Supervisor with observations.
- 📂 **All** — full view of the dept history.

### Filters
- State (status light)
- Urgency ([[Requisition Urgency Status Light|Requisition Urgency Status Light]])
- Position ([[Posiciones|Positions]])
- Creation date (range)
- Search by requisition ID or number

### Detail
- **Header:**
    - Requisition ID.
    - Number.
    - Supervisor who created it.
    - Date.
    - State.
- **Requested positions:**
    - Quantity.
    - Position.
    - Modality.
    - English level.
    - Schedule.
    - Start date.
- **Additional notes** from the Supervisor.
- **Current coverage** ([[Requisition Positions Status Light|Requisition Positions Status Light]]).
- **Assigned collaborators** (once Recruitment has started).

### Actions
- ➕ **Create requisition** *(the Area Manager can also create, not just the Supervisor)*.
- ✏️ **Edit draft** of my requisitions.
- 📤 **Send for authorization** (if I create it, I can authorize it myself or have the General Manager approve it).
- ✅ **Authorize requisition** *(sends to Recruitment — Self-Pick model)*.
- ❌ **Reject with observations** *(returns to the creator in In preparation state)*.
- 👁️ **View history / journal** of the requisition.
- 🗑️ **Delete requisition** *(with justification if it has positions)*.

> [!important]
> **Authorization shared with the General Manager.** Only the Area Manager or the General Manager can authorize. If the Supervisor tries to authorize, the system blocks with: *"Only the hotel manager can authorize the requisition"*. If the requisition has no positions: *"It has no registered positions, register at least one position and try again"*.

### Automatic effects upon authorization
| Effect | Result |
|---|---|
| Urgency calculation per position | >120h → Green · 72-120h → Yellow · <72h → Red |
| Position transition | Golden → Orange in [[Requisition Positions Status Light|Requisition Positions Status Light]] |
| Reflection in Schedule | Positions appear in the corresponding week |
| Inspector assignment | Automatic according to hotel zone |

---

## 📅 SCHEDULE Module

### Main view
- **Weekly calendar** of the hotel/dept (Monday → Sunday).
- Rows: required positions (Housekeeper, Hoseman, Chef, etc.).
- Columns: days of the week.
- Cells: assigned collaborator + schedule, or "Vacant" in red.

### Filters
- Department *(General Manager only; the Area Manager sees only its own)*.
- Position.
- Coverage status (covered / partial / vacant).
- Week (selector).

### Actions
- ✏️ **Edit assignment** *(reorder shifts, change schedules within the position)*.
- 🔁 **Move collaborator** between days/shifts (without changing the position).
- ⏸️ **Mark day as the collaborator's day off**.
- 📥 **Export Schedule of the week** (PDF/CSV).
- 🔔 **Request reinforcement from Recruitment** (generates a new express requisition if a position becomes vacant).

> [!info]
> The Schedule is the **axis of the Hotel module**. The Timesheet is built on top of it — without a Schedule there is no time tracking.

---

## ⏱️ TIMESHEET Module

### Main view
- **Weekly table** of collaborators × days with their 6 punches of the day (Clock-in, Lunch-out, Lunch-in, Break-out, Break-in, Clock-out).
- Indicator per shift: gross hours, Lunch deduction, net hours.
- **Timesheet Compliance Indicator** status-lighted per collaborator (Green / Yellow / Red).

### Filters
- Collaborator
- Position
- Day / week
- Compliance Indicator state

### Actions
- 📷 **Generate / Renew QR code** of the dept *(Area Manager exclusive)* — so that collaborators can punch.
- 👁️ **View shift detail** of a collaborator.
- ✏️ **Correct punch** (with mandatory justification — recorded in an auditable log).
- 📤 **Export Timesheet** weekly (PDF/CSV).

> [!warning]
> The Area Manager does **NOT have access** to the Extended Lunch Indicator — that is exclusive to internal Oranje roles (Inspector, Inspection Coordinator, Recruitment Manager).

### Lunch deduction rules (visible in each shift)
| Scenario | Deduction applied |
|---|---|
| Lunch < 30 min | 30 min (mandatory minimum) |
| Lunch ≥ 30 min | Actual time taken |
| No Lunch punch | 30 min (auto-deduction) |

---

## 👥 MY STAFF Module

### List
- Collaborators assigned to the hotel/dept, with [[Collaborator Status Light|Collaborator Status Light]] visible:
  - 🟠 Orange — Permanent
  - 🟢 Apple Green — Day 1-2 onboarding
  - 🔵 Light Blue — Day 3+ uniform delivery
  - 🩷 Pink — Stand-by
  - 🔴 Red — Reported
  - ⬜ Gray — In accident

### Filters
- Position
- Status light state
- Search by name / document

### Detail
- Collaborator data (name, photo, phone, position, modality).
- Collaborator's Schedule (assigned days).
- Weekly Timesheet (summary).
- History at the hotel (since when, positions covered).
- Current status light state.

### Actions
- 🩷 **Put on Stand-by (Pink)** *(Area Manager and Supervisor)* — no Schedule or Timesheet until the state is changed.
- 🔴 **Report collaborator (Red)** *(Area Manager exclusive)* — starts the Inspector's investigation.
- 👁️ **View history** of incidents / assignments.
- 📞 **Contact the collaborator** (phone / message).

> [!important]
> Area Manager, General Manager and Supervisor can put on Stand-by (Pink) and can report the collaborator (Red).

---

## 🚨 WORK ACCIDENTS Module

> [!info]
> The Area Manager also participates in reporting work accidents (together with the Supervisor and the General Manager). When it detects an accident in its department, it creates the accident card with on-site capture.

### Sub-views
- 🟢 **Active** — accidents under investigation by the Inspector.
- ✅ **Closed** — resolved cases (last month).
- 📂 **History** — all dept accidents.

### Accident detail
- Data of the affected collaborator.
- Date, time, exact location.
- Circumstances and witnesses.
- Immediate care provided.
- Collaborator's status (moves to **Gray (In accident)** in the Collaborator Status Light — protection against the 3-absence rule).
- Zone Inspector assigned automatically.

### Actions

#### Scenario A — Collaborator reports from the app
1. Simultaneous notification to the Supervisor, Area Manager and Inspector.
2. If the Area Manager attends physically (or if the Supervisor is unavailable), it captures the on-site information: exact location, circumstances, witnesses, immediate care.

#### Scenario B — The Area Manager itself detects the accident
1. Creates the accident card from the app:
   - 📝 Accident data
   - 📷 Attaches photos / evidence
   - 👤 Identifies the affected collaborator
2. The signal reaches the zone Inspector automatically.

### Filters
- Case status (Active / Closed)
- Affected collaborator
- Assigned Inspector
- Date range

---

## Area Manager operational flow

```
1. Login → Dashboard
   │
   ▼
2. Reviso requisiciones pendientes creadas por mi Supervisor
   │
   ├─→ Autorizo → pasa a Reclutamiento (Self-Pick)
   └─→ Rechazo → vuelve al Supervisor con observaciones
   │
   ▼
3. Reclutamiento toma la requisición y asigna colaboradores
   │
   ▼
4. Los colaboradores aparecen en mi Schedule semanal
   │
   ▼
5. Genero QR para que ponchen en Timesheet
   │
   ▼
6. Reviso Timesheet semanal:
      • Verifico cumplimiento (semáforo Verde / Amarillo / Rojo)
      • Corrijo ponches con justificación si aplica
   │
   ▼
7. Gestión continua:
      • Stand-by (Rosa) por temporada baja / decisión del hotel
      • Reportar (Rojo) si hay falta grave
      • Recibir alertas de QA y de Inspector
```

---

## Key differences vs Supervisor and General Manager

| Aspect | Supervisor | Area Manager | General Manager |
|---|---|---|---|
| Create requisition | ✅ | ❌ | ❌ |
| Authorize requisition | ❌ | ✅ exclusive | ❌ |
| Reject with observations | ❌ | ✅ | ❌ |
| Generate QR (Timesheet) | ❌ | ✅ exclusive | ❌ |
| Put on Stand-by (Pink) | ✅ | ✅ | ❌ |
| Report collaborator (Red) | ❌ | ✅ exclusive | ❌ |
| Manage weekly Schedule | View | ✅ edit | Global visibility |
| Report work accident | ✅ | — | ❌ |
| Global hotel visibility | ❌ | Only its dept | ✅ all depts |

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
║         ROL: MANAGER DE ÁREA / GERENTE DE DEPTO             ║
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
│ 📊 Dashboard │  KPIs del depto · Acciones rápidas            │
│ 📋 Requisic. │  Pendientes · Autorizar / Rechazar · Histor.  │
│ 📅 Schedule  │  Calendario semanal · Editar · Exportar       │
│ ⏱️ Timesheet │  Ponches · Generar QR · Cumplimiento          │
│ 👥 Personal  │  Mis colaboradores · Stand-by · Reportar      │
└──────────────┴───────────────────────────────────────────────┘
```

---

## Related

- [[Hotel/Area Manager|Area Manager]] (role definition)
- [[Hotel/Supervisor|Supervisor]]
- [[Hotel/General Manager|General Manager]]
- [[Hotel/Hotel|Hotel]]
- [[Hotel/Hotel Rules|Hotel Rules]]
- [[Core/Modules/Requisition/Requisition|Requisition]]
- [[Core/Modules/Requisition/Requisition Flow|Requisition Flow]]
- [[Core/Modules/Schedule|Schedule]]
- [[Timesheet]]
- [[Requisition Status Light|Requisition Status Light]]
- [[Collaborator Status Light|Collaborator Status Light]]
- [[Hotel Departments|Hotel Departments]]
- [[Inspector]]
