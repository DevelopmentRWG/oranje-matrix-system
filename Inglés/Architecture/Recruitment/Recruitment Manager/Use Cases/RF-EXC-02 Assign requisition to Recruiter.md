---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
  - excepcion
aliases:
  - UC RF-EXC-02
---

# 🪪 ID: RF-EXC-02
🏷️ **Name:** Assign requisition to Recruiter (VIP / balancing case)

**Story:**
**Exception to the collaborative Self-Pick model (RR-01).** The Manager manually assigns a requisition to a specific Recruiter, bypassing Self-Pick. It applies only in exceptional scenarios: a VIP hotel requisition that must go to the most senior Recruiter, load balancing when a Recruiter is saturated and nobody takes the requisition, absence of the zone's Group Leader. Under the collaborative model (RR-15), this assignment distinguishes two modes: **add as a participant** —the Recruiter joins the recruiters already working the requisition without displacing anyone— or **transfer** —it is reassigned as the main owner (see RF-EXC-03). The Manager's usual case is **add as a participant**.

**Acceptance criteria:**
The action is exceptional and requires mandatory justification. It is kept in an auditable log (rule RR-12). The selected Recruiter receives an immediate notification. The requisition's status light changes to Yellow (or stays the same if it was already In process). The requisition appears marked as "Assigned by Manager" in the Recruiter's inbox. When the Manager **adds them as a participant**, the Recruiter joins the active recruiters without displacing the existing ones and shares the coverage progress (RR-15). The event is recorded in the requisition's History (RR-16) with author and date.

**Documentation:**
- PRD: PRD-RECL-03 Manager
- Flow: Exceptional manual assignment
- Prototype: (Figma link)

**Flow:**
`Bandeja de Autorizadas` → MANUAL → `Selecciona requisición` → `Click "Asignar manual a Reclutadora"` → `Selecciona Reclutadora destino + modo (Agregar como participante / Transferir) + justificación obligatoria (VIP / balanceo / ausencia Líder)` → `Confirmar` → AUTOMATICO → `Reclutadora recibe la requisición en su bandeja + Marca como "Asignada por Manager" + Se une como reclutador participante sin desplazar a los existentes (modo Agregar) + Semáforo Amarillo + Notificación + Registra evento en el Historial de la requisición + Registro de excepción en log`
