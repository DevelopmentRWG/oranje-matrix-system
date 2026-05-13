---
tags:
  - arquitectura
  - rol/supervisor-hotel
  - caso-de-uso
aliases:
  - CU RF-H-03
---

# 🪪 ID: RF-H-03
🏷️ **Nombre:** Enviar requisición a autorización

**Historia:**
Cuando el Supervisor termina de armar la requisición (o de corregir una rechazada), la envía al Manager de Área para que la autorice. El sistema valida que tenga al menos 1 posición y, si es válida, la pasa a estado Verde manzana — pendiente de autorización y notifica al Manager de Área. La requisición queda visible en la bandeja de "Pendientes de autorización" del Manager.

**Criterios de aceptación:**
La requisición debe tener al menos 1 posición registrada (RR-H-03). Si no la tiene, el sistema bloquea con: *"No tiene posiciones registradas, registre al menos una posición e intente nuevamente"*. Si está OK, el estado pasa a Verde manzana pendiente y notifica al Manager de Área en menos de 1 min. La requisición ya NO es editable por el Supervisor hasta que el Manager la rechace o autorice.

**Documentación:**
- PRD: PRD-HOTEL-02 Supervisor
- Flow: Envío a autorización
- Prototipo: (link de Figma)

**Flujo:**
`Detalle de requisición (borrador o rechazada)` → MANUAL → `Click "Enviar a autorización"` → AUTOMATICO → `Valida que tenga ≥1 posición` → Si OK → `Estado pasa a Verde manzana — pendiente de autorización + Notifica al Manager de Área + Aparece en su bandeja "Pendientes de autorización" + Bloquea edición del Supervisor` / Si sin posiciones → `Bloquea con mensaje "No tiene posiciones registradas..."`
