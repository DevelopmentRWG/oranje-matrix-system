---
tags:
  - arquitectura
  - rol/manager-general
  - caso-de-uso
aliases:
  - CU RF-H-27
---

# 🪪 ID: RF-H-27
🏷️ **Nombre:** Escalar requisición demorada

**Historia:**
Cuando una requisición autorizada lleva tiempo en la bandeja de Reclutamiento sin ser tomada (especialmente si es urgencia Roja o de hotel VIP), el Manager General la **escala al Manager de Reclutamiento** para priorizarla. El escalamiento notifica formalmente al Manager de Reclutamiento con contexto y motivo, y el sistema marca la requisición como "Escalada".

**Criterios de aceptación:**
Acción exclusiva del Manager General. Motivo obligatorio (catálogo: Tiempo en cola excesivo / Urgencia Red / Hotel VIP / Otro). Mensaje al Manager de Reclutamiento obligatorio (mín. 30 caracteres). Notifica al Manager de Reclutamiento en menos de 1 min. Cambia indicador de la requisición a "Escalado". Queda en log auditable.

**Documentación:**
- PRD: PRD-HOTEL-04 Manager General
- Flow: Escalar requisición demorada
- Prototipo: (link de Figma)

**Flujo:**
`Detalle de requisición autorizada (sin tomar por mucho tiempo)` → MANUAL → `Click "Escalar a Reclutamiento"` → `Selecciona motivo (catálogo)` → `Escribe mensaje al Manager de Reclutamiento (mín. 30 caracteres)` → `Confirmar` → AUTOMATICO → `Notifica al Manager de Reclutamiento con link al expediente + Cambia indicador a "Escalado" + Queda en log auditable + Notifica al Gerente de Departamento responsable`
