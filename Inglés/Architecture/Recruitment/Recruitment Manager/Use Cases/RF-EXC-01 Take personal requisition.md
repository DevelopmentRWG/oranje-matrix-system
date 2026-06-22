---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
  - excepcion
aliases:
  - UC RF-EXC-01
---

# 🪪 ID: RF-EXC-01
🏷️ **Name:** Take personal requisition (Manager special case)

**Story:**
**Exception to the Self-Pick model (RR-01).** In extraordinary situations —urgent coverage with no available Recruiter, a VIP requisition requiring direct attention, lack of personnel due to mass absence— the Manager personally takes a requisition and works it as if they were a Recruiter. It is an exceptional intervention, not their daily task.

**Acceptance criteria:**
The action is exceptional and therefore requires mandatory justification. It is kept in an auditable log (rule RR-12). The requisition moves to a visually distinct "My Taken (Manager)" inbox. The status light automatically changes to Yellow. Reports and metrics distinguish requisitions taken by the Manager vs by a Recruiter. Under the collaborative model (RR-15), taking it **does not block it for others**: the Manager is registered as a participating recruiter and other recruiters can join to work it in parallel. The taking is recorded in the requisition's History (RR-16) with author and date.

**Documentation:**
- PRD: PRD-RECL-03 Manager
- Flow: Exceptional Manager Self-Pick
- Prototype: (Figma link)

**Flow:**
`Bandeja de Autorizadas` → MANUAL → `Click "Tomar como Manager"` → `Justificación obligatoria (motivo de la intervención)` → `Confirmar` → AUTOMATICO → `Mueve a "Mis Tomadas (Manager)" + Semáforo Amarillo + Se registra como reclutador participante (otros pueden unirse) + Registra evento en el Historial de la requisición + Registra excepción en log auditable + Notifica al Líder de zona`
