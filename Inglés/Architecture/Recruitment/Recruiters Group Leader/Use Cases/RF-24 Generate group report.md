---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-24 (Group Leader)
---

# 🪪 ID: RF-24
🏷️ **Name:** Generate group report

**Story:**
The Group Leader generates consolidated reports of their group's performance: aggregated coverage, performance per Recruiter, escalated cases, average times, distribution by zone. Unlike the Manager —who generates global department reports— the Group Leader generates reports with group scope. The report can be exported or formally sent to the Manager (flow RF-25).

**Acceptance criteria:**
Scope restricted to the Group Leader's group. Report types: Group coverage, Individual performance per Recruiter, Escalated cases, Distribution by zone. Filters by date range, zone and position. Supports CSV / PDF export. Preview before exporting / sending. History of generated reports.

**Documentation:**
- PRD: PRD-RECL-02 Líder de Grupo
- Flow: Generate group report
- Prototype: (Figma link)

**Flow:**
`Reports module` → MANUAL → `Click "New report"` → `Type: Group` → `Selects subtype (Coverage / Individual performance / Escalated cases / By zone) + date range + filters` → AUTOMATICO → `System compiles data from the Group Leader's group` → MANUAL → `Preview` → `Action: Export (CSV/PDF) / Save draft / Send to Manager (triggers RF-25)`
