---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - CU RF-14
---

# 🪪 ID: RF-14
🏷️ **Nombre:** Remover de Blacklist

**Historia:**
Tras una revisión, una disputa resuelta a favor del colaborador o un caso aclarado por evidencia nueva, el Manager remueve manualmente a un colaborador del Blacklist. La acción es exclusiva del Manager (regla RR-03) y reactiva automáticamente al colaborador en el Pool con estado Verde fuerte (Disponible).

**Criterios de aceptación:**
Solo el Manager puede remover (regla RR-03). La justificación es obligatoria. El colaborador queda reactivado en el Pool en menos de 1 min. Queda registro auditable de quién removió, cuándo y con qué motivo. Se notifica al colaborador.

**Documentación:**
- PRD: PRD-RECL-03 Manager
- Flow: Remoción de Blacklist
- Prototipo: (link de Figma)

**Flujo:**
`Detalle de colaborador en Blacklist` → MANUAL → `Click "Remover"` → `Justificación obligatoria` → `Confirmar` → AUTOMATICO → `Reactiva en Pool (Verde fuerte) + Registra remoción en log auditable + Notifica al colaborador y Reclutadora`
