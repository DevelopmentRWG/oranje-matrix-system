---
tags:
  - arquitectura
  - modulo/hotel
aliases:
  - Architecture General Manager
  - Wireframe General Manager
  - GM Architecture
---

# Architecture — General Manager

Wireframe of the Oranje platform for the [[Hotel/General Manager|General Manager]] role. Defines the entry flow, global header, modules sidebar and the detail of each module they have access to.

> [!info]
> The General Manager is the role with **maximum authority on the hotel side**. **Always exists**, in both simple and extended hierarchy.
> - **Simple hierarchy:** also operates as Area Manager (same person, two roles). Executes all operational actions + supervision.
> - **Extended hierarchy:** supervises the Area Managers (one per department). Keeps global visibility and can execute operational actions when intervening on specific occasions.

> [!important]
> The General Manager DOES have operation in addition to supervision. Can create/authorize requisitions, generate QR, edit Schedule, correct punches, report collaborators (Red) and report accidents. Additionally, has **exclusive executive functions:** global visibility of the hotel, executive reports to direction, supervision of Area Managers.

## N0 — Start

```
PLATAFORMA ORANGE
        │
        ▼
LOGIN / AUTORIZACIÓN
        │
        ▼
ROL IDENTIFICADO / MANAGER GENERAL (GM)
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
- Role: General Manager (GM)

**My hotel**
- Hotel name
- Hotel zone
- Number of operational departments
- Number of Department Managers in charge
- Number of total Supervisors

**My global metrics (current month)**
- Global hotel coverage (% of positions covered)
- Authorized requisitions (hotel total)
- Active collaborators
- Timesheet Compliance Indicator (consolidated)
- Quality Indicator of the Hotel department ([[QA]])

**Settings**
- Change password
- Notification preferences

🚪 Log out

### 🔍 SEARCH (global)

**What can be searched**
- Requisitions (any hotel department)
- Assigned collaborators (any department)
- Schedule by position / day
- Department Managers and Supervisors of the hotel
**How it works**
- Live results grouped by type
- Shortcut: `/` or `Ctrl+K`

### 🔔 NOTIFICATIONS (bell with badge)

**By event type**
- 🔴 Requisition in Red urgency unauthorized (>24h)
- 🟢 Critical coverage of a department (global visibility)
- 🚨 Serious workplace accident in any department
- 🛡️ QA Quality Indicator dropped to Red
- 📊 Weekly/monthly report available
- ⏱️ Timesheet Compliance Indicator in Red (consolidated)
- 🔁 Organizational change (addition/removal of Manager or Supervisor)

**States**
- 🟠 Unread (counts in the badge)
- 🟢 Read

---

## N1 — SIDEBAR (General Manager modules)

```
SIDEBAR
   ├─ DASHBOARD
   ├─ REQUISICIONES        (crear / autorizar / rechazar / vista global)
   ├─ SCHEDULE             (gestión + visibilidad global de todos los deptos)
   ├─ TIMESHEET            (revisar ponches + generar QR + visibilidad global)
   ├─ MI PERSONAL          (gestionar colaboradores — Stand-by / Reportar)
   ├─ ACCIDENTES           (reportar y dar seguimiento)
   ├─ MI EQUIPO DEL HOTEL  (Managers de Área + Supervisores)
   └─ REPORTES             (consolidados + envío a dirección)
```

> [!note]
> The General Manager has **operation + supervision**. Can execute all operational actions (same as the Area Manager: create/authorize requisitions, generate QR, edit Schedule, correct punches, Stand-by, Report Red, report accidents) **plus** the exclusive executive functions (global visibility of the hotel, supervision of Area Managers, executive reports to direction).

---

## 📊 DASHBOARD Module

### Global hotel KPIs
- **Global coverage** (% of positions covered — all departments)
- **Coverage by department** (Housekeeping, Food, Maintenance, Front Desk)
- **Requisitions pending authorization** (alert if any Manager is delayed)
- **Requisitions in coverage process** (Recruitment working on them)
- **Active collaborators** (total + by department)
- **Timesheet Compliance Indicator** (consolidated and by department)
- **Quality Indicator** ([[QA]] — status-coded by department)
- **Workplace accidents** of the month (total)

### Summary views
- **Coverage heatmap** by department and day of the week.
- **Ranking of Department Managers** by authorization speed and coverage.
- **Critical alerts** (any department with coverage <70%, open workplace accident, quality in Red).

### Quick actions
- 👁️ View global Schedule of the week
- 👁️ View monthly Report
- 📤 Request report from a Department Manager
- 🚨 View open critical cases

---

## 📅 GLOBAL SCHEDULE Module (consultation)

### Main view
- **Consolidated weekly calendar of the hotel** (Monday → Sunday).
- View by **department**: Housekeeping / Food / Maintenance / Front Desk.
- **Aggregated** view: total positions covered vs vacant per day.

### Filters
- Department
- Position
- Coverage status
- Week / month

### Actions (consultation)
- 👁️ **View detail** of any assignment.
- 📥 **Export consolidated Schedule** (PDF/CSV/Excel).
- 🔔 **Alert the Department Manager** if it detects critical vacancies.

> [!note]
> The General Manager does NOT edit the Schedule. The operational management is done by each Department Manager in their Schedule.

---

## ⏱️ GLOBAL TIMESHEET Module (consultation)

### Main view
- **Consolidated table of the hotel** with filter by department.
- Timesheet Compliance Indicator per collaborator (Green / Yellow / Red).
- Summary by department: payable hours, gross hours, deductions.

### Filters
- Department
- Collaborator
- Position
- Day / week

### Actions (consultation)
- 👁️ View workday detail of any hotel collaborator.
- 📤 Export consolidated Timesheet (PDF/CSV).
- 📊 Generate compliance report by department.

> [!warning]
> The General Manager **does NOT generate QR**, **does NOT correct punches**, **does NOT see the Extended Lunch Indicator** (the latter is exclusive to Oranje internal roles).

---

## 📋 REQUISITIONS Module (global view, supervision)

### Sub-views (all are consultation + supervision)
- 🟢 **Pending authorization** (any hotel department).
- 🟠 **Authorized** (in Recruitment).
- 🟡 **In process** of coverage.
- 🔵 **Covered**.
- 🔴 **Rejected**.
- 📂 **All** — historical view of the hotel.

### Filters
- Department
- Responsible Department Manager
- Status / urgency
- Position
- Date range

### Detail
- **Header:**
    - Requisition ID.
    - Number.
    - Supervisor who created it.
    - Date.
    - Status.
- **Requested positions:**
    - Quantity.
    - Position.
    - Modality.
    - English level.
    - Schedule.
    - Start date.
- **Additional notes** from the Supervisor.
- **Current coverage** ([[Requisition Positions Status Light|Requisition Positions Status Light]]).
- **Assigned collaborators** (when Recruitment has already started).
- **Additional information for global supervision** *(exclusive to the General Manager)*:
    - Manager who authorized/rejected it.
    - Processing time.

### Actions (supervisor profile)
- 👁️ **View full detail** of any hotel requisition.
- 💬 **Comment on the file** (visible to the Department Manager).
- 🚨 **Request the Department Manager** to prioritize a delayed requisition.
- 📤 **Escalate to Recruitment** if a requisition has been untaken for a while.
- 📊 **Generate report** of authorization times by Manager.

> [!important]
> The General Manager **does NOT authorize or reject** requisitions — authorization is the exclusive responsibility of the Department Manager. The General Manager's intervention is only supervision and escalation.

---

## 👥 MY HOTEL TEAM Module

### Sub-views
- 🧑‍💼 **Department Managers** — one per operational department.
- 🦺 **Supervisors** — consolidated list by department.

### List of Department Managers
- Name.
- Department.
- No. of Supervisors in charge.
- No. of active collaborators.
- % coverage.
- Average authorization time.

### List of Supervisors
- Name.
- Department.
- Manager they report to.
- No. of requisitions created (month).
- No. of accidents reported.

### Filters
- Department
- Load (high / medium / low)
- Search by name

### Detail (on click on a Manager or Supervisor)
- Basic data.
- Individual metrics.
- History of managed requisitions.
- Communication (chat / internal note).

### Actions
- 👁️ **View performance** in detail.
- 💬 **Communicate** with Manager or Supervisor.
- 📊 **Request report** specific.
- 🚨 **Escalate** if persistent low performance is detected.

> [!warning]
> The General Manager CANNOT add / remove Managers or Supervisors (that is done by the Hotel Administrator from Settings — outside the scope of the Hotel department on the platform).

---

## 📈 REPORTS Module

### Report types
- **Hotel coverage** (consolidated and by department).
- **Performance by Department Manager** (authorization times, % coverage, escalated cases).
- **Timesheet Compliance** by department and collaborator.
- **Quality** ([[QA]] — metrics and alerts).
- **Workplace accidents** of the period.
- **Executive indicators** for direction.

### Filters
- Date range (week / month / quarter / custom)
- Department
- Report type

### Actions
- 📊 **Generate report** with preview.
- 📥 **Export** (PDF / CSV / Excel).
- 📤 **Send to direction** (email / internal link).
- 📅 **Schedule recurring send** (weekly / monthly).
- 💾 **Save as template**.

### History
- List of generated reports with date, type, recipients, status.
- Reopen / Reuse as template.

---

## General Manager operational flow

```
1. Login → Dashboard
   │
   ▼
2. Reviso KPIs globales del hotel:
      • Cobertura por depto
      • Requisiciones pendientes
      • Indicador de Calidad / Timesheet
      • Casos críticos (accidentes, calidad en Rojo)
   │
   ▼
3. Reviso Schedule y Timesheet globales (consulta)
   │
   ▼
4. Detecto desbalances entre deptos:
      ├─→ Solicito reporte a Gerente de Depto
      ├─→ Comento al expediente de requisiciones demoradas
      └─→ Escalo a Reclutamiento si hace falta
   │
   ▼
5. Genero reportes consolidados:
      • Para mí (operativo)
      • Para dirección (ejecutivo)
   │
   ▼
6. Programo envíos recurrentes a dirección y a mí
```

---

## Key differences vs Supervisor and Area Manager

| Aspect | Supervisor | Area Manager | General Manager |
|---|---|---|---|
| Create requisition | ✅ | ❌ | ❌ |
| Authorize requisition | ❌ | ✅ exclusive | ❌ |
| Generate QR | ❌ | ✅ | ❌ |
| Edit Schedule | ❌ | ✅ | Global consultation only |
| Correct Timesheet | ❌ | ✅ | ❌ |
| Stand-by (Pink) | ✅ | ✅ | ❌ |
| Report (Red) | ❌ | ✅ exclusive | ❌ |
| Report accident | ✅ | — | ❌ |
| Global visibility of the hotel | ❌ | Only their department | ✅ all departments |
| Executive reports to direction | ❌ | ❌ | ✅ exclusive |
| Supervision of Managers | — | — | ✅ exclusive |

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
║                    ROL: MANAGER GENERAL (GM)                  ║
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
│ 📊 Dashboard │  KPIs globales · Heatmap · Ranking            │
│ 📅 Schedule  │  Schedule consolidado todos los deptos        │
│ ⏱️ Timesheet │  Timesheet consolidado · Cumplimiento         │
│ 📋 Requisic. │  Vista global · Supervisión · Escalamiento   │
│ 👥 Equipo    │  Gerentes de Depto · Supervisores · Métricas  │
│ 📈 Reportes  │  Generar · Enviar dirección · Programar       │
└──────────────┴───────────────────────────────────────────────┘
```

---

## Related

- [[Hotel/General Manager|General Manager]] (role definition)
- [[Hotel/Area Manager|Area Manager]]
- [[Hotel/Supervisor|Supervisor]]
- [[Hotel/Hotel|Hotel]]
- [[Hotel/Hotel Rules|Hotel Rules]]
- [[Hotel Departments|Hotel Departments]]
- [[Core/Modules/Schedule|Schedule]]
- [[Timesheet]]
- [[Core/Modules/Status Lights/Timesheet Compliance Indicator|Timesheet Compliance Indicator]]
- [[Core/Modules/Status Lights/Quality Indicator|Quality Indicator]]
- [[QA/QA|QA]]
- [[Requisition Status Light|Requisition Status Light]]
