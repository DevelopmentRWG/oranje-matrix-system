---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-25
---

# 🪪 ID: RF-25
🏷️ **Nombre:** Enviar reporte al Manager

**Historia:**
Tras generar un reporte del grupo (RF-24), el Líder lo envía formalmente al Manager de Reclutamiento. El envío crea una notificación con link al reporte, queda registrado en el histórico y dispara la lectura por parte del Manager. Es el canal oficial por el que el Líder reporta el desempeño de su grupo.

**Criterios de aceptación:**
Solo el Líder puede enviar (acción exclusiva). El reporte debe estar generado previamente (RF-24). El envío notifica al Manager en menos de 1 min. Queda en histórico de reportes enviados con fecha, destinatario y estado (enviado / leído). Comentario opcional al Manager.

**Documentación:**
- PRD: PRD-RECL-02 Líder de Grupo
- Flow: Envío formal de reporte
- Prototipo: (link de Figma)

**Flujo:**
`Vista previa de reporte (post RF-24)` → MANUAL → `Click "Enviar al Manager"` → `Comentario opcional` → `Confirmar` → AUTOMATICO → `Notifica al Manager con link al reporte + Registra en histórico (fecha / destinatario / estado) + Cambia estado del reporte a "Enviado"`
