---
tags:
  - proposal
  - module/recruitment
aliases:
  - Self-Pick
  - Requisition Self-Pick
status: approved
---

# Requisition Self-Pick

Requisition assignment model in the [[Reclutamiento/Reclutamiento|Reclutamiento]] module. [[Reclutadora|Recruiters]] and [[Reclutamiento/Líder de Grupo de Reclutadoras|Team Leads]] freely take requisitions from a shared inbox, without intermediation by the [[Manager de Reclutamiento]].

## Flow

```
Area Manager authorizes requisition
      ↓
Arrives in the system and is placed in the "Authorized" queue (visible to all Recruitment)
      ↓
The queue is automatically prioritized by the Requisition Urgency Status Indicator
      ↓
Recruiters and Team Leads freely take requisitions
      ↓
Upon taking, the requisition moves to Yellow (In progress) in the Requisition Status Indicator
      ↓
The Recruiter covers with associates from the Pool
```

## Operational Rules

- **No limit on simultaneous requisitions** — each Recruiter handles as many as arrive based on demand.
- **No restrictions by zone or language** — Recruiters receive candidates from everywhere and assign them according to the [[Core/Módulos/Reglas de Negocio|Reglas de Negocio]].
- **Global inbox with filters** — all Recruiters see all available requisitions. They can filter by zone, urgency, position, and other criteria, but the inbox is not segmented by group or by Recruiter.
- **Concurrency: first to confirm wins** — if two Recruiters attempt to take the same requisition at the same time, the system locks it for the first one to confirm. The second receives a message indicating the requisition has already been taken.
- **Auto-assignment at 24 hours** — if a requisition has been untaken for more than 24 hours (counted from authorization), the system automatically assigns it to the Recruiter with the lowest active requisition load at that moment. The [[Manager de Reclutamiento]] does not receive a notification; the process is transparent.

## Manager Intervention

The [[Manager de Reclutamiento]] only intervenes in exceptional cases:

- Balancing between groups
- Absent team lead
- Correcting an assignment error

## Escalation to Team Lead

When the [[Reclutadora]] cannot find a match in the [[Pool de Colaboradores]] and has actively searched outside the system (social networks, external groups, etc.), an escalation timeout to the [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo]] applies. The timeframe depends on the status of the [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición|Semáforo de Urgencia de Requisición]]:

| Urgency color | Condition | Time to escalate |
|---|---|---|
| Red | Less than 72h until start | 24h without coverage |
| Yellow | Between 72h and 120h until start | 48h without coverage |
| Dark Green | More than 120h until start | 72h without coverage |

> [!important] Throughout this entire process the requisition remains in **Yellow** status in the [[Core/Módulos/Semáforos/Semáforo de Requisición|Semáforo de Requisición]]. The escalation goes to the [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo]], not to the [[Manager de Reclutamiento]].

## Updated Documents

The following vault files reflect this model:

- [[Reclutamiento/Reglas de Reclutamiento|Reglas de Reclutamiento]] — section "Requisitions — Reception and Assignment (Self-Pick)"
- [[Core/Módulos/Reglas de Negocio|Reglas de Negocio]] — sections "Requisition Distribution" and "Assignment"
- [[Core/Módulos/Semáforos/Semáforo de Requisición|Semáforo de Requisición]] — Green → Yellow trigger
- [[Core/Módulos/Requisicion/Flujo de Requisición|Flujo de Requisición]] — section 5
- [[Reclutadora]] — first responsibility
- [[Manager de Reclutamiento]] — responsibilities

## Related

- [[Reclutamiento/Reglas de Reclutamiento|Reglas de Reclutamiento]]
- [[Core/Módulos/Reglas de Negocio|Reglas de Negocio]]
- [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición|Semáforo de Urgencia de Requisición]]
- [[Core/Módulos/Semáforos/Semáforo de Requisición|Semáforo de Requisición]]
- [[Manager de Reclutamiento]]
- [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo de Reclutadoras]]
- [[Reclutadora]]
