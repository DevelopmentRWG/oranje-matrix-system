---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - UC RF-23
---

# 🪪 ID: RF-23
🏷️ **Name:** Individual metrics by Recruiter

**Story:**
The Manager consults the individual performance of any Recruiter in the department (regardless of which Leader they belong to). Unlike the Group Leader —who only sees their own Recruiters— the Manager has full visibility to detect low performance, balance loads or make management decisions.

**Acceptance criteria:**
Global access to the metrics of any Recruiter in the department. Minimum metrics: monthly coverage, average assignment time, escalated cases, covered vs partial requisitions. Filters by date range and zone. Metrics updated daily.

**Documentation:**
- PRD: PRD-RECL-03 Manager
- Flow: Individual metrics (global view)
- Prototype: (Figma link)

**Flow:**
`Módulo Mi Equipo` → MANUAL → `Selecciona Líder de Grupo` → `Selecciona Reclutadora` → AUTOMATICO → `Sistema compila métricas individuales (cobertura, tiempo promedio, casos)` → MANUAL → `Aplica filtros (rango fechas / zona)` → `Exporta o envía al Líder`
