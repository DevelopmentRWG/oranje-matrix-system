---
tags:
  - arquitectura
  - rol/bdc
  - caso-de-uso
aliases:
  - CU RF-V-20
---

# 🪪 ID: RF-V-20
🏷️ **Nombre:** Marcar cliente Negro

**Historia:**
Cuando un cliente activo (status Naranja) deja de operar — por cierre del hotel, cambio de administración, pausa o disputa — el BDC lo marca como **Negro**. Esta acción es **exclusiva del BDC** (RR-V-05). El cliente queda como pausado / inactivo y sale de la vista de clientes activos. Posteriormente puede reactivarse (RF-V-21) volviendo a status Azul Claro como prospecto.

**Criterios de aceptación:**
Solo el BDC puede marcar Negro (RR-V-05). Motivo obligatorio (catálogo: Cierre del hotel / Cambio de administración / Pausa / Disputa / Otro). Comentario obligatorio (mín. 30 caracteres). Fecha de pausa opcional. Notifica al BD asignado. Queda en log auditable. El hotel sale de la vista de clientes activos y se mueve a la sub-vista "Negro" del módulo Clientes Activos.

**Documentación:**
- PRD: PRD-VENTAS-03 BDC
- Flow: Marcar cliente Negro
- Prototipo: (link de Figma)

**Flujo:**
`Detalle de cliente activo (Naranja)` → MANUAL → `Click "Marcar Negro"` → `Selecciona motivo (catálogo)` → `Comentario obligatorio (mín. 30 caracteres)` → `Fecha de pausa opcional` → `Confirmar` → AUTOMATICO → `Status pasa a Negro + Cliente sale de vista activos + Aparece en sub-vista Negro + Notifica al BD asignado + Log auditable`

**Reactivación (RF-V-21):**
`Sub-vista Negro → Click en cliente → Click "Reactivar"` → `Justificación opcional` → `Confirmar` → AUTOMATICO → `Status regresa a Azul Claro como prospecto (RR-V-07) + Notifica al BD original + Línea de tiempo mantiene el histórico Negro`
