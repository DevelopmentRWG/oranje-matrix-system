---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-23 (Group Leader)
---

# 🪪 ID: RF-23
🏷️ **Name:** Individual metrics per Recruiter

**Story:**
The Group Leader consults the performance detail of a specific Recruiter in their group: coverage for the month, average assignment time, escalated cases, covered vs partial requisitions, trends relative to the previous month. Unlike the Manager —who sees any Recruiter in the department— the Group Leader only accesses those in their group (hierarchy rule RR-10).

**Acceptance criteria:**
Access restricted to Recruiters in the Group Leader's own group. Minimum metrics: % coverage, average assignment time, covered / partial / pending requisitions, escalated cases, comparison against the previous month. Filters by date range and position. Metrics updated daily. From the detail you can: View detailed load (RF-36), Reassign requisition (RF-37), Mark availability (RF-38) and Generate individual report.

**Documentation:**
- PRD: PRD-RECL-02 Líder de Grupo
- Flow: Individual metrics (group scope)
- Prototype: (Figma link)

**Flow:**
`My Group → Click on Recruiter` → AUTOMATICO → `System validates that they belong to the Group Leader's group + Compiles individual metrics (coverage, average time, cases)` → MANUAL → `Applies filters (date range / position)` → `Actions: View detailed load (RF-36) / Reassign (RF-37) / Mark availability (RF-38) / Generate individual report`
