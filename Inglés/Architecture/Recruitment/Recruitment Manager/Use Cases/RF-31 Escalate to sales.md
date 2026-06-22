---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - UC RF-31
---

# 🪪 ID: RF-31
🏷️ **Name:** Escalate to commercial

**Story:**
When an incident affects the commercial relationship with the hotel (recurring complaint, risk of losing the client, serious conflict with the Area Manager), the Recruitment Manager escalates it to the Business Developer (BD) or Business Developer Coordinator (BDC) of the Onboarding-Hotel module so they take over the commercial conversation.

**Acceptance criteria:**
The escalation includes the full context of the case (evidence, history, previous decisions). It notifies the BD/BDC assigned to the hotel in under 1 min. The case remains in "Escalated to commercial" status until the commercial area closes it. The integration with Onboarding-Hotel is done via RI-05.

**Documentation:**
- PRD: PRD-RECL-03 Manager
- Flow: Escalate to commercial
- Prototype: (Figma link)

**Flow:**
`Detalle de incidencia` → MANUAL → `Click "Escalar a comercial"` → `Selecciona destinatario (BD / BDC del hotel afectado) + agrega contexto + adjunta evidencia` → `Confirmar` → AUTOMATICO → `Notifica al BD/BDC con link al caso + Cambia estado a "Escalado a comercial" + Registra escalamiento en log`
