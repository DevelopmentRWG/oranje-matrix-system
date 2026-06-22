---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - CU RF-21
---

# 🪪 ID: RF-21
🏷️ **Nombre:** Forzar cambio de semáforo

**Historia:**
De manera excepcional, el Manager puede modificar manualmente un semáforo de una requisición (Semáforo de Requisición / Urgencia / Posiciones) cuando la lógica automática no refleja la realidad operativa. Por ejemplo: una requisición marcada Roja (vencida) que en realidad ya fue resuelta offline, o una marcada Verde que el Manager quiere subir a Amarilla por riesgo detectado.

**Criterios de aceptación:**
Solo el Manager puede forzar el cambio. La justificación es obligatoria. El cambio queda en log auditable (regla RR-12). Se notifica al Líder de Grupo y Reclutadora afectados. El cambio forzado prevalece sobre el cálculo automático hasta que un evento posterior lo recalcule.

**Documentación:**
- PRD: PRD-RECL-03 Manager
- Flow: Forzar cambio de semáforo
- Prototipo: (link de Figma)

**Flujo:**
`Detalle de requisición` → MANUAL → `Click "Forzar semáforo"` → `Selecciona semáforo a modificar (Requisición / Urgencia / Posiciones) + valor destino + justificación obligatoria` → `Confirmar` → AUTOMATICO → `Aplica cambio + Registra en log auditable + Notifica al Líder y Reclutadora afectados`
