---
tags:
  - arquitectura
  - rol/manager-general
  - caso-de-uso
aliases:
  - UC RF-H-24
---

# 🪪 ID: RF-H-24
🏷️ **Name:** Generate executive report

**Story:**
The General Manager generates consolidated hotel reports for internal use and to send to direction. The available templates are: Coverage, Performance per Manager, Timesheet Compliance, Quality (QA), Workplace Accidents and Executive Indicators. Each report can be compared against the previous period.

**Acceptance criteria:**
Action exclusive to the General Manager. Preview before exporting / sending. Supports export in CSV / PDF / Excel. Filters by date range, departments and additional filters (position, hotel, Manager). Optional comparison against the previous period. Stays in the history of generated reports.

**Documentation:**
- PRD: PRD-HOTEL-04 General Manager
- Flow: Generate executive report
- Prototype: (Figma link)

**Flow:**
`Sidebar → Reports → Click "New report"` → MANUAL → `Select type (Coverage / Performance / Compliance / Quality / Accidents / Indicators)` → `Select date range` → `Select departments (optional — all by default)` → `Additional filters (optional)` → `Check "Comparison against previous period" (optional)` → `Select output format (PDF / CSV / Excel)` → `Click "Generate"` → AUTOMATICO → `System compiles period data + Generates preview` → MANUAL → `Action: Export / Send to direction (RF-H-25) / Save as template`
