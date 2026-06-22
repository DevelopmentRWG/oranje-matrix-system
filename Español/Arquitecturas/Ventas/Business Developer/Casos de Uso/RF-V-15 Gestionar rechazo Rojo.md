---
tags:
  - arquitectura
  - rol/business-developer
  - caso-de-uso
aliases:
  - CU RF-V-15
---

# 🪪 ID: RF-V-15
🏷️ **Nombre:** Gestionar rechazo (Rojo)

**Historia:**
Cuando un hotel rechaza la propuesta o no muestra interés, el BD marca el prospecto como **Rojo** indicando el motivo. El status queda como rechazado pero puede reactivarse después si las condiciones cambian. La gestión de Rojo es **exclusiva del BD** (RR-V-06).

**Criterios de aceptación:**
Motivo obligatorio (catálogo: No le interesó / No tiene presupuesto / Otra empresa / Otro). Comentario obligatorio (mín. 30 caracteres). Opción de marcar "Reactivar más adelante" para que aparezca en lista de candidatos a reactivar. Notifica al BDC del rechazo. Queda en línea de tiempo.

**Documentación:**
- PRD: PRD-VENTAS-02 Business Developer
- Flow: Gestionar rechazo (Rojo)
- Prototipo: (link de Figma)

**Flujo:**
`Detalle de prospecto (cualquier status pre-Naranja)` → MANUAL → `Click "Marcar Rojo"` → `Selecciona motivo (catálogo)` → `Comentario obligatorio (mín. 30 caracteres)` → `Marca "Reactivar más adelante" opcional` → `Confirmar` → AUTOMATICO → `Status pasa a Rojo + Notifica al BDC + Línea de tiempo actualizada + Si "reactivar" marcado, aparece en lista de candidatos a reactivar`

**Reactivación (RF-V-16):**
`Lista de Rojos → Click en prospecto → Click "Reactivar"` → AUTOMATICO → `Status regresa a Azul Claro (RR-V-07) + Histórico mantiene el rechazo + Notifica al BDC`
