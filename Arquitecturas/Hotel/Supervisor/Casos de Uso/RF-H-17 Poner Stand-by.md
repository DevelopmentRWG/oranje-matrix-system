---
tags:
  - arquitectura
  - rol/supervisor-hotel
  - caso-de-uso
aliases:
  - CU RF-H-17 (Supervisor)
---

# 🪪 ID: RF-H-17
🏷️ **Nombre:** Poner colaborador en Stand-by (Rosa) — Supervisor

**Historia:**
El Supervisor puede poner a un colaborador en **Stand-by (Rosa)** por decisión operativa: vacaciones del colaborador, temporada baja, decisión del hotel. Esta acción es **compartida con el Manager de Área** (RR-H-11). El colaborador queda sin Schedule ni Timesheet hasta que se cambie su estado.

**Criterios de aceptación:**
Compartido con Manager de Área (RR-H-11). El motivo es obligatorio (catálogo: Vacaciones / Temporada baja / Decisión del hotel / Otro). El colaborador no puede ya estar en Stand-by. La acción notifica al colaborador y al Manager de Área. Queda en log auditable. La posición queda sin colaborador asignado en el Schedule.

**Documentación:**
- PRD: PRD-HOTEL-02 Supervisor
- Flow: Stand-by (Rosa)
- Prototipo: (link de Figma)

**Flujo:**
`Módulo Mi Personal → Detalle del colaborador` → MANUAL → `Click "Poner en Stand-by"` → `Selecciona motivo (catálogo)` → `Notas opcional` → `Confirmar` → AUTOMATICO → Si OK → `Estado del colaborador a Rosa + Sin Schedule ni Timesheet + Notifica al colaborador y al Manager de Área + Log auditable` / Si ya en Stand-by → `Bloquea con mensaje`
