---
tags:
  - arquitectura
  - modulo/ventas
aliases:
  - BDC Architecture
  - BDC Wireframe
  - Business Developer Coordinator Architecture
---

# Architecture — Business Developer Coordinator (BDC)

Oranje platform wireframe for the [[Sales/Roles/Business Developer Coordinator|Business Developer Coordinator]] role. Defines the entry flow, global header, module sidebar and the detail of each module it has access to.

> [!info]
> The BDC is the **supervisor role** of the Sales department. Supervises routes and zones, validates the terms of the T&C Document, **gives the final yes** to the conversion of prospect into client, and manages special cases: stagnation (Brown) and paused clients (Black).

> [!important]
> **EXCLUSIVE actions of the BDC** (not the BD):
> 1. Validate T&C Document
> 2. Create Hotel User
> 3. **Approve conversion** (RR-V-01) → fires the Automatic Trigger
> 4. Unblock stagnation (Brown — RR-V-04)
> 5. Manage paused client (Black — RR-V-05)
> 6. Generate executive reports

## N0 — Start

```
PLATAFORMA ORANGE
        │
        ▼
LOGIN / AUTORIZACIÓN
        │
        ▼
ROL IDENTIFICADO / BUSINESS DEVELOPER COORDINATOR (BDC)
        │
        ▼
MÓDULOS / SIDEBAR
```

---

## HEADER (present across the whole app)

### 👤 USER PROFILE (dropdown)

**My information**
- Full name + photo
- Email + phone
- Role: Business Developer Coordinator (BDC)

**My supervised territory**
- Routes and zones in charge
- Number of supervised BDs
- Number of active prospects
- Number of active clients

**My metrics (current month)**
- Approved conversions
- Territory conversion rate
- Unblocked Brown cases
- Reactivated Black clients
- Average T&C validation time

**Settings**
- Change password
- Notification preferences

🚪 Log out

### 🔍 SEARCH (global)

**What can be searched**
- Active prospect / client hotels
- Supervised BDs
- Proposals
- T&C Documents
- Brown / Black cases

**How it works**
- Live results grouped by type
- Shortcut: `/` or `Ctrl+K`

### 🔔 NOTIFICATIONS (bell with badge)

**By event type**
- 📄 BD sent T&C for validation
- ☕ BD marked prospect Brown (I must unblock)
- ⚫ Active client moved to Black
- 📊 Report request from management
- 📈 BDs reached monthly goals
- 🔴 Quality Indicator dropped

**States**
- 🟠 Unread (counts in the badge)
- 🟢 Read

---

## N1 — SIDEBAR (BDC Modules)

```
SIDEBAR
   ├─ DASHBOARD
   ├─ PIPELINE             (vista global del territorio)
   ├─ DOCUMENTOS T&C       (validación final)
   ├─ CONVERSIÓN           (Crear Usuario + Aprobar)
   ├─ MI EQUIPO            (BDs a cargo)
   ├─ CLIENTES ACTIVOS     (referente comercial)
   └─ REPORTES             (ejecutivos)
```

> [!note]
> The BDC has a **global view** of the entire territory. It does NOT operate prospects like the BD (does not identify, does not propose), but it can create T&C and participate in the negotiation (Pink).

---

## 📊 DASHBOARD Module

### Territory KPIs
- Total active prospects by status
- Conversions of the month (% of the territory)
- T&C pending validation (red badge if >24h)
- Brown cases pending unblocking
- Active Black clients
- Quality Indicator ([[QA]])

### Summary views
- **Conversion funnel:** Gray → Light Blue → Green → Yellow → Pink → Orange with count by stage.
- **Zone heatmap:** performance by route / zone.
- **BD ranking:** by conversions, proposals sent, success rate.
- **Critical cases:** T&C awaiting validation, Brown not unblocked, quality alerts.

### Quick actions
- 📄 Validate pending T&C
- ☕ Unblock Brown
- ✅ Approve conversion
- 📊 Generate report
- 💬 Communicate with a BD

---

## 📋 PIPELINE Module (Global view of the territory)

### Sub-views (all Onboarding Status Light statuses, all BDs)
- ⚪ **Gray** · 🔵 **Light Blue** · 🟢 **Green** · 🟡 **Yellow** · 🩷 **Pink**
- 🟠 **Orange** · 🔴 **Red** · ⚫ **Black** · 🟤 **Brown** · 📂 **All**

### Filters
- Assigned BD
- Route / Zone
- Status
- Identification date
- Days in status

### Prospect detail
- Same fields the BD sees + **assigned BD** visible.
- Full timeline with all status changes.

### Actions (supervisor profile)
- 👁️ **View full detail** of any prospect.
- 💬 **Comment on the file** (visible to the BD).
- 📤 **Reassign prospect to another BD** (exceptional — BD absent or overloaded).
- 📝 **Edit status / correct** (with mandatory justification).

---

## 📄 T&C DOCUMENTS Module

### Sub-views
- ⏳ **Pending validation** (red badge if it has been >24h)
- ✅ **Validated**
- ❌ **Rejected with observations**
- 📂 **History**

### T&C detail
- Hotel data
- Pay rate, Bill rate, Overtime, Holidays, Calendar
- BD who created it
- Version history (if it was rejected and resent)

### Actions (BDC exclusive)
- ✓ **Validate T&C** (RF-V-10) — gives the final yes to start Pink.
- ✗ **Reject T&C with observations** — returns to the BD for correction.
- 💬 **Comment** to the BD about a field.

> [!important]
> T&C validation is a **prerequisite** to start the negotiation (Pink) and, subsequently, to approve the conversion.

---

## ✅ CONVERSION Module

### Sub-views
- ⏳ **Ready for conversion** (in Pink with validated T&C)
- ✅ **Converted** (last 30 days)
- 📂 **History**

### Actions (BDC exclusive)
- ➕ **Create Hotel User** (RF-V-11) — mandatory precondition.
- ✅ **Approve conversion** (RF-V-12) — only if Hotel User already created (RR-V-02).

### Detail of the conversion process

```
PROSPECTO EN ROSA + T&C VALIDADO
         │
         ▼
1. BDC crea USUARIO DEL HOTEL (RF-V-11)
         │
         ▼
2. BDC click "APROBAR CONVERSIÓN" (RF-V-12)
         │
         ▼
3. Sistema dispara TRIGGER AUTOMÁTICO (RF-V-13):
      ├─ Email de bienvenida al hotel
      ├─ Notificación al BD asignado
      └─ Hotel sale de Pipeline (prospectos)
         │
         ▼
4. Status pasa a NARANJA (cliente activo)
         │
         ▼
5. Hotel pasa a operación: Reclutamiento + Inspector
         │
         ▼
6. Contrato se genera con T&C validado como insumo
```

> [!warning]
> If the BDC tries to approve conversion without having created the Hotel User, the system blocks with: *"You must create the Hotel User before approving the conversion"* (RR-V-02).

---

## 👥 MY TEAM Module

### List of BDs
- BD · route/zone · no. of active prospects · % conversion · average time

### Filters
- Route / Zone
- Status (active / vacation / leave)
- Load (high / medium / low)

### BD detail (on click)
- Basic data
- Individual metrics (conversions, proposals, rejections, average time)
- History of managed prospects
- Communication (chat / internal note)

### Actions
- 👁️ **View performance** detail of the BD.
- 💬 **Communicate** with the BD.
- 📤 **Reassign prospect** to another BD on the team.
- 📊 **Request report** specific.

---

## 🏨 ACTIVE CLIENTS Module (commercial reference)

### Sub-views
- ✅ **Active** (Orange status)
- ⚫ **Black** (paused / inactive — BDC exclusive management)

### Detail
- Commercial data of the client
- Onboarding history
- Applicable T&C
- Originating assigned BD

### Actions
- 👁️ **View client detail**.
- ⚫ **Mark Black** (paused / inactive client) — RF-V-20.
- ↩️ **Reactivate from Black** (returns to Light Blue as a prospect) — RF-V-21.

> [!important]
> Black and reactivation from Black are **exclusive to the BDC** (RR-V-05). The BD does not have access.

---

## ☕ Brown Inbox (direct view from Pipeline)

### Dedicated sub-view
- All territory prospects in Brown
- Notes from the BD who marked Brown (context)

### Actions (BDC exclusive)
- 🔍 **Investigate case** — review history, contacts, BD notes.
- ✅ **Unblock Brown** (RF-V-18) — agreed solution.
- ↩️ **Reactivate to Light Blue** (RF-V-19) — the original BD recovers the case.
- 🔄 **Reassign to another BD** if applicable.

---

## 📈 REPORTS Module

### Report types
- Territory pipeline
- Conversion by BD / zone / month
- Unblocked Brown cases
- Black clients
- Quality Indicator
- Executive report for management

### Filters
- Date range
- BD / Route / Zone

### Actions
- 📊 **Generate report** (RF-V-26)
- 📥 **Export** (CSV / PDF / Excel)
- 📤 **Send to management** (RF-V-27)
- 📅 **Schedule recurring sending**

### History
- List of generated reports with recipient and status.

---

## BDC operational flow

```
1. Login → Dashboard (embudo, casos críticos, alertas)
   │
   ▼
2. Reviso T&C pendientes → Valido o rechazo con observaciones
   │
   ▼
3. Reviso Pipeline global del territorio:
      ├─ Casos Café → desbloqueo
      ├─ Casos Negro → gestiono o reactivo
      └─ Casos Rosa con T&C validado → preparo conversión
   │
   ▼
4. Para cada conversión:
      ├─ Creo Usuario del Hotel (precondición)
      └─ Apruebo conversión → dispara Trigger Automático
   │
   ▼
5. Reviso desempeño de mis BDs (Mi Equipo)
   │
   ▼
6. Comunico observaciones, reasigno casos si aplica
   │
   ▼
7. Genero reportes ejecutivos para dirección
```

---

## Key differences vs BD

| Aspect | BD | BDC |
|---|---|---|
| Identify prospects | ✅ | — |
| Visibility | My territory | Entire supervised territory |
| Draft Proposal | ✅ | — |
| Create T&C | ✅ | ✅ |
| **Validate T&C** | ❌ | ✅ exclusive |
| Negotiate (Pink) | ✅ | ✅ |
| **Create Hotel User** | ❌ | ✅ exclusive |
| **Approve conversion** | ❌ | ✅ exclusive |
| Manage Red | ✅ | — |
| **Unblock Brown** | ❌ | ✅ exclusive |
| **Manage Black** | ❌ | ✅ exclusive |
| My Team (BDs) | ❌ | ✅ exclusive |
| Executive reports | ❌ | ✅ exclusive |

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
║              ROL: BUSINESS DEVELOPER COORDINATOR              ║
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
│ 📊 Dashboard │  Embudo · Heatmap · Ranking BDs · Casos       │
│ 📋 Pipeline  │  Vista global · Filtros por BD/zona/status    │
│ 📄 T&C       │  Validar · Rechazar · Histórico               │
│ ✅ Conversión│  Crear Usuario Hotel · Aprobar conversión     │
│ 👥 Mi Equipo │  BDs a cargo · Métricas individuales          │
│ 🏨 Clientes  │  Activos + Negro · Reactivar                  │
│ 📈 Reportes  │  Generar · Enviar dirección · Programar       │
└──────────────┴───────────────────────────────────────────────┘
```

---

## Related

- [[Sales/Roles/Business Developer Coordinator|Business Developer Coordinator]] (role definition)
- [[Sales/Roles/Business Developer|Business Developer]]
- [[Sales/Sales|Sales]]
- [[Sales/Sales Rules|Sales Rules]]
- [[Sales/Hotel Onboarding/Hotel Onboarding|Hotel Onboarding]]
- [[Sales/Hotel Onboarding/Onboarding Flow|Onboarding Flow]]
- [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]]
- [[Sales/Hotel Onboarding/Concepts/Terms and Conditions Document|Terms and Conditions Document]]
- [[Sales/Hotel Onboarding/Concepts/Automatic Conversion Trigger|Automatic Conversion Trigger]]
- [[Sales/Hotel Onboarding/Concepts/Hotel User|Hotel User]]
- [[Core/Modules/Contrato|Contract]]
- [[Hotel/Hotel|Hotel]] (post-Orange destination)
