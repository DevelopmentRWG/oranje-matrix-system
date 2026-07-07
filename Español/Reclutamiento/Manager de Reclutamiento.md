---
tags:
  - modulo/reclutamiento
aliases:
  - Manager de Reclutamiento
---

# Manager de Reclutamiento

Rol responsable de coordinar la entrada de requisiciones y supervisar casos especiales dentro del módulo de [[Reclutamiento/Reclutamiento|Reclutamiento]].

## Responsabilidades

- Monitorea la bandeja compartida de [[Requisición|requisiciones]] e interviene manualmente solo en casos excepcionales: balanceo entre grupos, líder ausente y corrección de error de asignación. Las requisiciones sin tomar por más de 24 horas son asignadas automáticamente por el sistema.
- Revisa casos de [[Core/Módulos/Blacklist|Blacklist]].
- Supervisa a las [[Líder de Grupo de Reclutadoras|Líderes de Grupo de Reclutadoras]].
- Tiene visibilidad del **Indicador de Lunch Extendido** en el [[Timesheet]] para evaluar patrones de comportamiento de colaboradores activos.
- Gestiona su equipo directo en el módulo **Mi Equipo** (RF-29): da de alta, edita, mueve entre grupos y cambia el estado (incluyendo baja lógica) de [[Líder de Grupo de Reclutadoras|Líderes de Grupo]] y [[Reclutadora|Reclutadoras]]. Es el único rol del departamento con CRUD completo del equipo.
- Consulta el **Dashboard global** del departamento (RF-28): indicadores de cobertura global, requisiciones cubiertas/parciales/pendientes, casos escalados abiertos e [[Core/Módulos/Semáforos/Indicador de Calidad|Indicador de Calidad]], con vista de tendencia y bandeja de acciones prioritarias.
- Gestiona la bandeja de **Incidencias** del departamento (RF-30): recibe casos escalados por Líderes o Inspectores, investiga la evidencia y emite una decisión final. El ciclo de vida del caso transita por los estados Abierto → En investigación → Esperando info → Escalado a comercial / Escalado a Dirección → Resuelto. Los tipos de incidencia y los SLA están en proceso de validación de negocio.
- Puede **resolver** una incidencia (RF-30) o **escalarla a Comercial** (RF-31), notificando al [[Ventas/Roles/Business Developer|Business Developer]] o [[Ventas/Roles/Business Developer Coordinator|Business Developer Coordinator]] del hotel afectado para que gestionen la relación comercial.
- Ante casos críticos que exceden su alcance, puede **escalar a Dirección**: vía de escalamiento hacia arriba, distinta de los reportes de seguimiento que genera para supervisión propia del departamento.
- Audita el historial global de altas y entrevistas de candidatos del departamento (RR-12): acceso de solo lectura a todas las entrevistas registradas por cualquier Reclutadora o Líder; sus intervenciones directas son excepcionales y quedan en log auditable.

## Relacionado

- [[Flujo de Reclutamiento]]
- [[Reclutadora]]
- [[Líder de Grupo de Reclutadoras]]
- [[Requisición]]
- [[Timesheet]]
- [[Self-Pick de Requisiciones]]
- [[Core/Módulos/Semáforos/Indicador de Calidad|Indicador de Calidad]]
- [[Ventas/Roles/Business Developer|Business Developer]]
- [[Ventas/Roles/Business Developer Coordinator|Business Developer Coordinator]]
