---
tags:
  - arquitectura
  - rol/manager-de-area
  - caso-de-uso
aliases:
  - CU RF-H-06
---
H
# 🪪 ID: RF-H-06
🏷️ **Nombre:** Rechazar requisición con observaciones

**Historia:**
Cuando una requisición creada por el Supervisor tiene errores (posiciones equivocadas, modalidad incorrecta, datos incompletos, justificación insuficiente), el Manager de Área la rechaza con observaciones. La requisición vuelve al Supervisor en estado **En elaboración** y este puede corregir y reenviar. Es el mecanismo formal para mantener la calidad de las requisiciones antes de que lleguen a Reclutamiento.

**Criterios de aceptación:**
El motivo y las observaciones son obligatorios (mín. 20 caracteres). Al rechazar, la requisición vuelve al Supervisor con las observaciones visibles en el detalle. Notifica al Supervisor en menos de 1 min. Queda en log auditable con autor, fecha y motivo.

**Documentación:**
- PRD: PRD-HOTEL-03 Manager de Área
- Flow: Rechazo de requisición
- Prototipo: (link de Figma)

**Flujo:**
`Sidebar → Requisiciones → Bandeja "Pendientes de autorización"` → MANUAL → `Click en requisición` → `Revisa contenido` → MANUAL → `Click "Rechazar"` → `Selecciona motivo (Posiciones erróneas / Modalidad incorrecta / Datos incompletos / Falta justificación / Otro)` → `Escribe observaciones obligatorias (mín. 20 caracteres)` → `Adjunta evidencia opcional` → `Confirmar` → AUTOMATICO → `Cambia estado a En elaboración + Notifica al Supervisor + Registra en log con autor/fecha/motivo`
