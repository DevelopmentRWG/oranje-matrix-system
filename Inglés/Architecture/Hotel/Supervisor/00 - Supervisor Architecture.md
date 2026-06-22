---
tags:
  - arquitectura
  - modulo/hotel
aliases:
  - Supervisor Architecture
  - Supervisor Wireframe
  - SUP Architecture
---

# Architecture — Supervisor

Oranje platform wireframe for the [[Hotel/Supervisor|Supervisor]] role. Defines the entry flow, global header, modules sidebar and the detail of each module they have access to.

> [!info]
> The Supervisor is the **base operational role** on the hotel side. Their main task is to **create staffing requisitions** and send them to the [[Hotel/Area Manager|Area Manager]] for authorization. They also report workplace accidents on the property.

> [!important]
> The Supervisor **CANNOT** authorize requisitions — that action is exclusive to the Area Manager (platform security layer).

## N0 — Start

```
PLATAFORMA ORANGE
        │
        ▼
LOGIN / AUTORIZACIÓN
        │
        ▼
ROL IDENTIFICADO / SUPERVISOR
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
- Role: Supervisor (SUP)

**My hotel / department**
- Hotel name
- Department they report to *(in extended hierarchy — e.g. Housekeeping)*
- Area Manager / Department Manager they report to

**My metrics (current month)**
- Requisitions created
- Requisitions authorized
- Requisitions rejected
- Workplace accidents reported

**Settings**
- Change password
- Notification preferences

🚪 Log out

### 🔍 SEARCH (global)

**What can be searched**
- My requisitions (by ID or number)
- Collaborators assigned to the hotel/department
- Schedule positions

**How it works**
- Live results grouped by type
- Shortcut: `/` or `Ctrl+K`

### 🔔 NOTIFICATIONS (bell with badge)

**By event type**
- ✅ My requisition was authorized by the Area Manager
- ❌ My requisition was rejected with observations (needs corrections)
- 👤 Recruitment assigned a collaborator to one of my requisitions
- 🟢 One of my requisitions was 100% covered
- 🚨 Workplace accident reported by a collaborator (Scenario A — I must attend)
- ⏱️ Change in the department Schedule

**States**
- 🟠 Unread (counts in the badge)
- 🟢 Read

---

## N1 — SIDEBAR (Supervisor Modules)

```
SIDEBAR
   ├─ DASHBOARD
   ├─ REQUISICIONES        (crear + ver mis creadas)
   ├─ SCHEDULE             (consulta del depto)
   ├─ TIMESHEET            (consulta del depto)
   ├─ MI PERSONAL          (colaboradores asignados — Stand-by limitado)
   └─ ACCIDENTES           (reportar y dar seguimiento)
```

> [!note]
> The Supervisor **DOES NOT** have access to QR generation. Their Schedule and Timesheet are **read-only** (they do not edit assignments).

---

## 📊 DASHBOARD Module

### Personal KPIs
- Requisitions I created this month
- My requisitions pending authorization (waiting for the Area Manager)
- My authorized requisitions in process
- My rejected requisitions (need correction)
- Active workplace accidents in the department

### Summary views
- **My recent requisitions:** short list by status.
- **Critical Schedule positions:** vacant positions or those with partial coverage (to identify where to create a new requisition).
- **Accident alerts:** open cases where I must attend.

### Quick actions
- ➕ New requisition
- 🚨 Report accident
- 👁️ View today's Schedule
- 👁️ View my rejected requisitions

---

## 📋 REQUISITIONS Module

### Sub-views

- ✏️ **Drafts** — requisitions I am editing (not yet sent for authorization).
- 🟢 **Pending authorization** *(Apple Green — In progress)* — sent to the Area Manager, awaiting their decision.
- ❌ **Rejected** — returned with observations from the Area Manager; I must correct and resend.
- 🟠 **Authorized** — now in Recruitment's hands (read-only for me).
- 🟡 **In process** — Recruitment assigning collaborators.
- 🔵 **Covered** — at 100%.
- 📂 **All** — complete history of my requisitions.

### Filters
- Status
- Position
- Creation date
- Search by ID

### Requisition detail
- **Header:**
    - ID.
    - Number (auto-generated: `AAAAMMDDHHMMxx`).
    - Date.
    - Status.
- **Positions:**
    - Quantity.
    - Position.
    - Modality.
    - English level.
    - Schedule.
    - Start date.
- **Additional notes.**
- **Area Manager observations** *(visible only if rejected)*.

### Actions
- ➕ **Create new requisition** *(full form — see module below)*.
- ✏️ **Edit draft** or **rejected requisition**.
- 📤 **Send to the Area Manager for authorization** *(changes status to Apple Green — In progress)*.
- 🗑️ **Delete draft** or **requisition without positions** *(automatic physical deletion if it has no positions)*.
- 👁️ **View journal** of the requisition.

> [!warning]
> The Supervisor **CANNOT authorize** nor send directly to Recruitment. If they try, the system blocks with: **"Only the hotel manager can authorize the requisition"**.

### ➕ "New Requisition" form

**Required fields:**
- Required [[Posiciones|positions]] (catalog autocomplete)
- Number of people per position
- Start date
- Schedule (clock-in / clock-out)
- [[Employment Types|Hiring modality]] (Full-time / Part-time / Temporary / On request)
- [[English Levels|English level]] preference (Basic / Intermediate / Advanced / Conversational)

**Optional fields:**
- Additional notes (operational context, special requirements)
- Attachments (PDF / image)

**Validations:**
- At least 1 registered position (without this the Area Manager will NOT be able to authorize — the message "Has no registered positions" appears).
- Start date in the future.
- Quantity > 0.

---

## 📅 SCHEDULE Module (read-only)

### Main view
- **Weekly calendar** of the hotel/department (same as the Area Manager's).
- Rows: positions; columns: days; cells: assigned collaborator or "Vacant".

### Filters
- Position
- Coverage status
- Week (selector)

### Actions (limited — read-only)
- 👁️ View assignment detail.
- 📥 Export the week's Schedule (PDF/CSV).
- 🔔 **Suggest reinforcement to the Area Manager** (generates a new requisition prefill if a position is vacant for a long time).

> [!note]
> The Supervisor **DOES NOT edit** the Schedule. If they detect missing coverage, they create a new requisition or notify the Area Manager.

---

## ⏱️ TIMESHEET Module (read-only)

### Main view
- **Weekly table** of collaborators × days with their 6 clock-ins and net hours.
- Timesheet Compliance indicator per collaborator (Green / Yellow / Red).

### Filters
- Collaborator
- Position
- Day / week

### Actions (limited — read-only)
- 👁️ View workday detail.
- 📤 Export weekly Timesheet.

> [!warning]
> The Supervisor **DOES NOT generate QR** (that is exclusive to the Area Manager). **DOES NOT correct clock-ins** (that is also exclusive to the Area Manager). **DOES NOT see the Extended Lunch Indicator** (exclusive to Oranje roles).

---

## 👥 MY STAFF Module

### List
- Collaborators assigned to the hotel/department, with the [[Collaborator Status Light|Collaborator Status Light]] visible.

### Filters
- Position · Status Light state · Search by name

### Detail
- Collaborator data (name, photo, phone, position, modality).
- Collaborator's Schedule (assigned days).
- Weekly Timesheet (summary).

### Actions
- 🩷 **Put on Stand-by (Pink)** *(shared with Area Manager and General Manager)* — collaborator is left without Schedule or Timesheet.
- 🔴 **Report collaborator (Red)** *(NEW — shared with Area Manager and General Manager)* — starts an Inspector investigation with reason and evidence.
- 👁️ **View history** of incidents / assignments.
- 📞 **Contact the collaborator**.

> [!info]
> All 3 Hotel roles can report a collaborator (Red) and put one on Stand-by (Pink). Reporting a collaborator automatically triggers a zone Inspector investigation.

---

## 🚨 WORKPLACE ACCIDENTS Module

> [!important]
> The Supervisor has an **active role** in reporting and capturing workplace accidents. They physically attend the incident site.

### Sub-views
- 🟢 **Active** — accidents under investigation by the Inspector.
- ✅ **Closed** — resolved cases (last month).
- 📂 **History** — all department accidents.

### Accident detail
- Affected collaborator's data.
- Date, time, exact location.
- Circumstances.
- Witnesses.
- Immediate care provided.
- Collaborator status (switch to Gray in the [[Collaborator Status Light|Collaborator Status Light]] = protection against the 3-absence rule).
- Assigned Inspector.

### Actions

#### Scenario A — Collaborator reports from the app
1. **I receive a simultaneous notification** with the zone Inspector.
2. **I physically attend** the incident site.
3. **I capture on-site information**:
   - Exact location
   - Circumstances
   - Witnesses
   - Immediate care provided

#### Scenario B — I detect it first
1. **I detect the accident** on the property.
2. **I create the accident card** from the app:
   - 📝 **Create card** with all the data.
   - 📷 Attach photos / evidence.
   - 👤 Identify the affected collaborator.
3. **The signal reaches the zone Inspector** automatically.

> [!info]
> In both scenarios, the collaborator switches to **Gray** (Injured) state in the Collaborator Status Light, which protects them from the 3-absence rule while the investigation is underway.

### Filters
- Case status
- Affected collaborator
- Assigned Inspector
- Date range

---

## Supervisor operational flow

```
1. Login → Dashboard
   │
   ▼
2. Detecto necesidad de personal en mi depto
   │
   ▼
3. Creo Nueva Requisición:
      • Posiciones, cantidad, modalidad, inglés, horario
      • Notas adicionales si aplica
   │
   ▼
4. Envío al Manager de Área para autorización
   │
   ├─→ Autoriza → pasa a Reclutamiento (Self-Pick)
   └─→ Rechaza → corrijo según observaciones y reenvío
   │
   ▼
5. Reclutamiento asigna colaboradores → aparecen en Schedule
   │
   ▼
6. Operación diaria:
      • Consulto Schedule y Timesheet
      • Pongo Stand-by (Rosa) si el hotel decide
      • Reporto accidentes laborales (Escenario A o B)
   │
   ▼
7. Si una posición se queda vacante o termina:
      • Genero nueva requisición
      • Sugiero refuerzo al Manager de Área
```

---

## Key differences vs Area Manager and General Manager

| Aspect | Supervisor | Area Manager | General Manager |
|---|---|---|---|
| Create requisition | ✅ main action | ❌ | ❌ |
| Authorize requisition | ❌ | ✅ exclusive | ❌ |
| Generate QR | ❌ | ✅ | ❌ |
| Edit Schedule | ❌ (read-only) | ✅ | Global read-only |
| Correct Timesheet | ❌ | ✅ | ❌ |
| Stand-by (Pink) | ✅ | ✅ | ❌ |
| Report (Red) | ❌ | ✅ exclusive | ❌ |
| Report workplace accident | ✅ main action | ❌ | ❌ |
| Global hotel visibility | Their department only | Their department only | ✅ all departments |

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
║                    ROL: SUPERVISOR (SUP)                      ║
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
│ 📊 Dashboard │  Mis KPIs · Acciones rápidas                  │
│ 📋 Requisic. │  Crear · Mis requisiciones · Rechazadas       │
│ 📅 Schedule  │  Calendario (consulta) · Sugerir refuerzo     │
│ ⏱️ Timesheet │  Ponches del depto (consulta)                 │
│ 👥 Personal  │  Mis colaboradores · Stand-by                 │
│ 🚨 Accidents │  Reportar · Casos activos · Histórico         │
└──────────────┴───────────────────────────────────────────────┘
```

---

## Related

- [[Hotel/Supervisor|Supervisor]] (role definition)
- [[Hotel/Area Manager|Area Manager]]
- [[Hotel/General Manager|General Manager]]
- [[Hotel/Hotel|Hotel]]
- [[Hotel/Hotel Rules|Hotel Rules]]
- [[Core/Modules/Requisition/Requisition|Requisition]]
- [[Core/Modules/Requisition/Requisition Flow|Requisition Flow]]
- [[Core/Modules/Schedule|Schedule]]
- [[Timesheet]]
- [[Core/Modules/Workplace Accident/Workplace Accident|Workplace Accident]]
- [[Core/Modules/Workplace Accident/Workplace Accident Flow|Workplace Accident Flow]]
- [[Requisition Status Light|Requisition Status Light]]
- [[Collaborator Status Light|Collaborator Status Light]]
- [[Hotel Departments|Hotel Departments]]
- [[Inspector]]
