---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-22
---

# 🪪 ID: RF-22
🏷️ **Name:** View Recruiters in the group

**Story:**
The Group Leader consults the "My Group" module to see all the Recruiters under their charge in a single view, with their operational metrics (number of active requisitions, % coverage for the month, escalated cases, current status). It is the entry point for any supervision action: detect overload, identify low performance or select a Recruiter to review in detail.

**Acceptance criteria:**
View exclusive to the Group Leader, showing only the Recruiters in their group. List with: name, zone, number of active requisitions, % coverage for the month, pending escalated cases, status (active / on vacation / inactive). Filters by zone, status and load. Search by name. Clicking on a Recruiter opens their detailed profile (RF-23).

**Documentation:**
- PRD: PRD-RECL-02 Líder de Grupo
- Flow: My Group
- Prototype: (Figma link)

**Flow:**
`Sidebar → Click "My Group"` → AUTOMATICO → `System lists only the Recruiters of the Group Leader's group with aggregated metrics` → MANUAL → `Applies filters (zone / status / load)` or `Click on Recruiter` → `Opens detailed profile with individual metrics (RF-23)`
