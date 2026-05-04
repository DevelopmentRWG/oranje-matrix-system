---
tags:
  - arquitectura
  - rol/manager-general
  - caso-de-uso
aliases:
  - CU RF-H-22
---

# 🪪 ID: RF-H-22
🏷️ **Nombre:** Ver Schedule global del hotel

**Historia:**
El Manager General consulta el Schedule **consolidado de todos los departamentos** del hotel (Housekeeping, Alimentos, Mantenimiento, Front Desk). Le permite identificar desbalances de cobertura, días con vacantes críticas y oportunidades de balanceo entre deptos. A diferencia del Manager del Hotel — que ve solo su depto — el Manager General tiene visibilidad consolidada.

**Criterios de aceptación:**
Vista exclusiva del Manager General (solo jerarquía extendida). Calendario semanal consolidado del hotel con vista por depto + agregada. Drill-down hasta posición / colaborador. Filtros por depto, posición, estado de cobertura, semana. Heatmap de cobertura por día. Sin acceso a edición — solo lectura.

**Documentación:**
- PRD: PRD-HOTEL-04 Manager General
- Flow: Schedule Global del Hotel
- Prototipo: (link de Figma)

**Flujo:**
`Sidebar → Schedule Global` → AUTOMATICO → `Sistema consolida Schedule de todos los deptos del hotel + Heatmap de cobertura por día` → MANUAL → `Aplica filtros (depto / posición / estado / semana)` → `Click en celda para drill-down` → `Acción: Exportar consolidado / Comentar al Gerente del depto / Escalar a Reclutamiento`
