---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
  - excepcion
aliases:
  - UC RF-EXC-03
---

# 🪪 ID: RF-EXC-03
🏷️ **Name:** Reassign requisition between Recruiters

**Story:**
**Exception to the collaborative Self-Pick model (RR-01).** When a Recruiter has already taken a requisition but cannot continue it (unexpected absence, overload, Leader escalation), the Manager moves the requisition to another Recruiter. In **transfer** mode, the original Recruiter loses access and the new one receives it with all the prior context (notes, shortlisted candidates, history). As a **collaborative alternative (RR-15)** —when it is about support or overload and not a total replacement— the Manager adds the new Recruiter as a participant and the **original one remains a participating recruiter**; both work the requisition in parallel with shared coverage progress.

**Acceptance criteria:**
The action is exceptional and requires a mandatory reason. It is kept in an auditable log (rule RR-12). In transfer mode, the original Recruiter receives a notification of access loss; in support/collaborative mode, the original one keeps access as a participant and is only notified of the reinforcement. The new Recruiter receives the requisition with all the context. If the requisition had shortlisted collaborators, those remain visible to the new Recruiter and what was already assigned by others is not rolled back. The status light is not reset. The event (transfer or support incorporation) is recorded in the requisition's History (RR-16) with author and date. *(It does not affect RR-05, which governs the exclusivity of the collaborator/worker between hotels.)*

**Documentation:**
- PRD: PRD-RECL-03 Manager
- Flow: Exceptional reassignment
- Prototype: (Figma link)

**Flow:**
`Detalle de requisición tomada` → MANUAL → `Click "Reasignar"` → `Selecciona nueva Reclutadora + modo (Transferir / Agregar como apoyo) + motivo obligatorio (ausencia / sobrecarga / escalamiento)` → `Confirmar` → AUTOMATICO → `[Modo Transferir] Reclutadora original pierde acceso + Notificación a Reclutadora original / [Modo Apoyo] Reclutadora original permanece como participante + Notificación de refuerzo + Nueva Reclutadora recibe la requisición con contexto completo (notas + candidatos preseleccionados + historial) + Notificación a nueva Reclutadora + Notificación a ambos Líderes (si distintos) + Registra evento en el Historial de la requisición + Registro de excepción en log auditable`
