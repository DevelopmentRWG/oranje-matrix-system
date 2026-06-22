---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - UC RF-24
---

# 🪪 ID: RF-24
🏷️ **Name:** Generate global report

**Story:**
The Manager generates consolidated reports of the Recruitment department for Management or other areas. It includes global coverage, performance by Leader, escalated cases, distribution by zone and trends for the period. The report can be exported or scheduled for recurring delivery (weekly/monthly).

**Acceptance criteria:**
The report is generated with data updated as of the previous day's close. It includes filters by date range, zone, position and hotel. It supports CSV / PDF / Excel export. It allows scheduling recurring delivery with configurable recipients. A history of sent reports is kept.

**Documentation:**
- PRD: PRD-RECL-03 Manager
- Flow: Generate global report
- Prototype: (Figma link)

**Flow:**
`Módulo Reportes` → MANUAL → `Click "Nuevo reporte"` → `Tipo: Global` → `Selecciona rango de fechas + filtros (zona / posición / hotel)` → AUTOMATICO → `Sistema compila datos del periodo` → MANUAL → `Vista previa del reporte` → `Acción: Exportar (CSV/PDF/Excel) / Enviar a Dirección / Programar envío recurrente`
