---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-27 (Group Leader)
---

# 🪪 ID: RF-27
🏷️ **Name:** View coverage by zone

**Story:**
The Group Leader visualizes the aggregated coverage by the zones where their Recruiters operate (Centro, Sur, Este, Oeste, Noroeste, Sureste, as applicable). It allows them to identify zones with low coverage within their group, balance loads among Recruiters or prioritize critical requisitions by zone. Unlike the Manager —who sees all the department's zones— the Group Leader only sees the zones assigned to their group.

**Acceptance criteria:**
Scope limited to the zones where the group's Recruiters are assigned. KPIs per zone: total requisitions, covered, partial, pending, % coverage, average time. Filters by date range and position. Visualization on map or table. Drill-down down to the hotel / requisition level.

**Documentation:**
- PRD: PRD-RECL-02 Líder de Grupo
- Flow: Coverage by zone (group scope)
- Prototype: (Figma link)

**Flow:**
`Group dashboard` → MANUAL → `Filter: By zone` → AUTOMATICO → `System groups requisitions by zone of the Group Leader's group + Calculates KPIs` → MANUAL → `Map or table view` → `Click on zone for drill-down (hotel / requisition / Recruiter)`
