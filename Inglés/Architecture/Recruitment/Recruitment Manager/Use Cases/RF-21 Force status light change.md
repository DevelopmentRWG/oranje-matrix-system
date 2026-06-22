---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - UC RF-21
---

# 🪪 ID: RF-21
🏷️ **Name:** Force status light change

**Story:**
Exceptionally, the Manager can manually modify a requisition's status light (Requisition / Urgency / Positions Status Light) when the automatic logic does not reflect the operational reality. For example: a requisition marked Red (expired) that was actually already resolved offline, or one marked Green that the Manager wants to raise to Yellow due to a detected risk.

**Acceptance criteria:**
Only the Manager can force the change. Justification is mandatory. The change is kept in an auditable log (rule RR-12). The affected Group Leader and Recruiter are notified. The forced change prevails over the automatic calculation until a later event recalculates it.

**Documentation:**
- PRD: PRD-RECL-03 Manager
- Flow: Force status light change
- Prototype: (Figma link)

**Flow:**
`Detalle de requisición` → MANUAL → `Click "Forzar semáforo"` → `Selecciona semáforo a modificar (Requisición / Urgencia / Posiciones) + valor destino + justificación obligatoria` → `Confirmar` → AUTOMATICO → `Aplica cambio + Registra en log auditable + Notifica al Líder y Reclutadora afectados`
