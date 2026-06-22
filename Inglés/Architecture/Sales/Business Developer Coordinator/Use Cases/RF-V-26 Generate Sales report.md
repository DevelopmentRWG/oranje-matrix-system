---
tags:
  - arquitectura
  - rol/bdc
  - caso-de-uso
aliases:
  - CU RF-V-26
---

# 🪪 ID: RF-V-26
🏷️ **Name:** Generate Sales report

**Story:**
The BDC generates consolidated territory reports for internal use and to send to management. The available templates are: Territory Pipeline, Conversion by BD/zone/month, Unblocked Brown cases, Black Clients, Quality Indicator, and Executive Report. Each report can be compared against the previous period.

**Acceptance criteria:**
Exclusive BDC action. Preview before exporting / sending. Supports CSV / PDF / Excel export. Filters by date range, BDs, routes, and zones. Optional comparison against the previous period. Recorded in the history of generated reports.

**Documentation:**
- PRD: PRD-VENTAS-03 BDC
- Flow: Generate Sales report
- Prototype: (Figma link)

**Flow:**
`Sidebar → Reports → Click "New report"` → MANUAL → `Selects type (Pipeline / Conversion / Performance / Brown / Black / Quality / Executive)` → `Selects date range` → `Optional included BDs (all by default)` → `Optional Routes/Zones` → `Marks "Comparison against previous period" optional` → `Selects output format (PDF / CSV / Excel)` → `Click "Generate"` → AUTOMATICO → `System compiles period data + Generates preview` → MANUAL → `Action: Export / Send to management (RF-V-27) / Save as template`
