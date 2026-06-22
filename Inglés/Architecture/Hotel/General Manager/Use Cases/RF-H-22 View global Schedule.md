---
tags:
  - arquitectura
  - rol/manager-general
  - caso-de-uso
aliases:
  - UC RF-H-22
---

# 🪪 ID: RF-H-22
🏷️ **Name:** View global hotel Schedule

**Story:**
The General Manager reviews the **consolidated Schedule of all departments** of the hotel (Housekeeping, Food, Maintenance, Front Desk). It allows them to identify coverage imbalances, days with critical vacancies and opportunities to balance across departments. Unlike the Area Manager — who only sees their department — the General Manager has consolidated visibility.

**Acceptance criteria:**
View exclusive to the General Manager (extended hierarchy only). Consolidated weekly hotel calendar with per-department + aggregated view. Drill-down to position / collaborator. Filters by department, position, coverage status, week. Coverage heatmap per day. No edit access — read-only.

**Documentation:**
- PRD: PRD-HOTEL-04 General Manager
- Flow: Global Hotel Schedule
- Prototype: (Figma link)

**Flow:**
`Sidebar → Global Schedule` → AUTOMATICO → `System consolidates Schedule of all hotel departments + Coverage heatmap per day` → MANUAL → `Apply filters (department / position / status / week)` → `Click on cell to drill-down` → `Action: Export consolidated / Comment to the department Manager / Escalate to Recruitment`
