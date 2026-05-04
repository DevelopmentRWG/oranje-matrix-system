---
tags:
  - arquitectura
  - rol/manager-general
  - caso-de-uso
aliases:
  - CU RF-H-26
---

# 🪪 ID: RF-H-26
🏷️ **Nombre:** Comentar al expediente de requisición

**Historia:**
Cuando el Manager General detecta una requisición demorada, mal armada o que requiere atención del Gerente de Departamento responsable, agrega un comentario al expediente de la requisición. El comentario es visible para el Gerente y queda en el journal de la requisición. Es el canal formal de **supervisión sin operación**: el Manager General no autoriza ni modifica, pero deja huella.

**Criterios de aceptación:**
El comentario debe tener al menos 20 caracteres. Aparece en el journal de la requisición con autor y fecha. Notifica al Gerente de Departamento responsable. Puede notificar a otros involucrados (Supervisor, etc.) si se selecciona. Adjuntos opcionales (PDF/JPG/PNG, máx. 5 MB).

**Documentación:**
- PRD: PRD-HOTEL-04 Manager General
- Flow: Comentar al expediente
- Prototipo: (link de Figma)

**Flujo:**
`Detalle de requisición (vista global)` → MANUAL → `Click "Comentar"` → `Escribe comentario (mín. 20 caracteres)` → `Selecciona destinatarios adicionales opcional` → `Adjunta archivo opcional` → `Confirmar` → AUTOMATICO → `Comentario aparece en journal + Notifica al Gerente de Departamento + Notifica a destinatarios adicionales si aplica + Queda en log con autor y fecha`
