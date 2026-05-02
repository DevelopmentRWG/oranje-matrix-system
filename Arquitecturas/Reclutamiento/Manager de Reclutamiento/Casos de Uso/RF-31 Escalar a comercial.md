---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - CU RF-31
---

# 🪪 ID: RF-31
🏷️ **Nombre:** Escalar a comercial

**Historia:**
Cuando una incidencia afecta la relación comercial con el hotel (queja recurrente, riesgo de pérdida de cliente, conflicto serio con el Manager del Hotel), el Manager de Reclutamiento la escala al Business Developer (BD) o Business Developer Coordinator (BDC) del módulo Onboarding-Hotel para que tomen la conversación comercial.

**Criterios de aceptación:**
El escalamiento incluye todo el contexto del caso (evidencia, historial, decisiones previas). Notifica al BD/BDC asignado al hotel en menos de 1 min. El caso queda en estado "Escalado a comercial" hasta que el área comercial lo cierre. La integración con Onboarding-Hotel se hace vía RI-05.

**Documentación:**
- PRD: PRD-RECL-03 Manager
- Flow: Escalar a comercial
- Prototipo: (link de Figma)

**Flujo:**
`Detalle de incidencia` → MANUAL → `Click "Escalar a comercial"` → `Selecciona destinatario (BD / BDC del hotel afectado) + agrega contexto + adjunta evidencia` → `Confirmar` → AUTOMATICO → `Notifica al BD/BDC con link al caso + Cambia estado a "Escalado a comercial" + Registra escalamiento en log`
