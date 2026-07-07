---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - UC RF-28
---

# 🪪 ID: RF-28
🏷️ **Name:** View global coverage

**Story:**
The Manager consults the master indicator of the Recruitment department: % total coverage, covered / pending / partial requisitions, ranking of Leaders by performance, critical alerts (red status lights, escalated cases). It is the command dashboard for making department decisions and for the Manager's own tracking and supervision.

**Acceptance criteria:**
View exclusive to the Manager. Global KPIs for the current month updated as of the previous day's close. Allows drill-down by zone, Leader or Recruiter. Visible alerts for red status lights and pending escalated cases. Comparison against the previous month.

**Documentation:**
- PRD: PRD-RECL-03 Manager
- Flow: Global department coverage
- Prototype: (Figma link)

**Flow:**
`Dashboard Manager` → AUTOMATICO → `Sistema compila KPIs globales del mes en curso (cobertura total, req. cubiertas/pendientes/parciales, ranking Líderes, alertas)` → MANUAL → `Click en métrica para drill-down (zona / Líder / Reclutadora)` → `Acción: Ver detalle / Exportar / Generar reporte`
