---
tags:
  - arquitectura
  - rol/business-developer
  - caso-de-uso
aliases:
  - CU RF-V-05
---

# 🪪 ID: RF-V-05
🏷️ **Nombre:** Enviar propuesta al hotel

**Historia:**
Tras elaborar la Propuesta Personalizada, el BD la envía al hotel por email desde la plataforma. Este envío marca el cambio de status del prospecto a **Verde** (Propuesta Enviada). El hotel recibe el documento y empieza la ventana de seguimiento.

**Criterios de aceptación:**
La propuesta debe estar completa (servicios, precios, condiciones, vigencia). Al enviar, el status pasa a Verde automáticamente. Se notifica al BDC del envío. El email queda en histórico de envíos. La propuesta deja de ser editable en esta versión (puede duplicarse como plantilla).

**Documentación:**
- PRD: PRD-VENTAS-02 Business Developer
- Flow: Enviar propuesta
- Prototipo: (link de Figma)

**Flujo:**
`Vista previa de Propuesta (post RF-V-04)` → MANUAL → `Click "Enviar al hotel"` → `Confirma destinatarios (email del hotel pre-llenado)` → `Mensaje opcional para el hotel` → `Confirmar` → AUTOMATICO → Si propuesta completa → `Envía email con propuesta adjunta + Status pasa a Verde + Notifica al BDC + Bloquea edición de esta versión + Registra envío en histórico` / Si propuesta incompleta → `Bloquea con mensaje "Complete servicios y precios"`
