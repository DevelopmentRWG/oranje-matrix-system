---
tags:
  - arquitectura
  - rol/manager-del-hotel
  - caso-de-uso
aliases:
  - CU RF-H-12
---

# 🪪 ID: RF-H-12
🏷️ **Nombre:** Editar Schedule semanal

**Historia:**
El Manager del Hotel ajusta el Schedule semanal del depto: reordena turnos, mueve colaboradores entre días o turnos dentro de la misma posición, marca días de descanso. La edición es **operación viva**: cambia las horas reales que trabajan los colaboradores y se refleja inmediatamente en su Timesheet y notificaciones.

**Criterios de aceptación:**
El Manager del Hotel ve el calendario semanal del depto (Lunes → Domingo) con filas de posiciones y columnas de días. Las ediciones persisten en menos de 2s. Si el cambio genera un cruce (mismo colaborador en 2 turnos al mismo tiempo), el sistema bloquea con mensaje claro. Cada edición notifica al colaborador afectado. Recalcula Indicador de Cumplimiento del Timesheet si aplica.

**Documentación:**
- PRD: PRD-HOTEL-03 Manager del Hotel
- Flow: Edición de Schedule semanal
- Prototipo: (link de Figma)

**Flujo:**
`Módulo Schedule` → MANUAL → `Selecciona semana` → `Click en celda (colaborador × día × posición)` → `Edita horario / mueve colaborador / marca descanso` → `Confirmar` → AUTOMATICO → `Valida que no haya cruces` → Si OK → `Persiste cambio + Notifica al colaborador + Recalcula Indicador de Cumplimiento` / Si cruce → `Bloquea con mensaje "El colaborador ya está asignado en este horario en otra posición"`
