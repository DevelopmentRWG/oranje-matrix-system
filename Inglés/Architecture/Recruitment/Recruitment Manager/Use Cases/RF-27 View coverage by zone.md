---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - UC RF-27
---

# 🪪 ID: RF-27
🏷️ **Name:** View coverage by zone

**Story:**
The Manager visualizes the aggregate coverage by zone (Centro, Sur, Este, Oeste, Noroeste, Sureste) to detect geographic imbalances: zones with low coverage, saturated zones, zones with high coverage times. It allows making balancing decisions between Leaders and Recruiters.

**Acceptance criteria:**
View by zone with: total requisitions, covered, partial, pending, % coverage, average time. Filters by date range and position. Visualization on map or table. Drill-down to the hotel/requisition level.

**Documentation:**
- PRD: PRD-RECL-03 Manager
- Flow: Coverage by zone
- Prototype: (Figma link)

**Flow:**
`Dashboard global` → MANUAL → `Filtro: Por zona` → AUTOMATICO → `Sistema agrupa requisiciones por zona + Calcula KPIs` → MANUAL → `Vista mapa o tabla` → `Click en zona para drill-down (hotel / requisición / Reclutadora)`
