---
tags:
  - arquitectura
  - rol/manager-general
  - caso-de-uso
aliases:
  - UC RF-H-23
---

# 🪪 ID: RF-H-23
🏷️ **Name:** View global hotel Timesheet

**Story:**
The General Manager reviews the **consolidated Timesheet of all departments** of the hotel. They view the Compliance Indicator per collaborator and per department, gross / net hours and deductions. They detect departments with low compliance and request specific reports from the corresponding Manager.

**Acceptance criteria:**
View exclusive to the General Manager (extended hierarchy only). Consolidated hotel table with filters by department, collaborator, position, week. Timesheet Compliance Indicator with status light (Green / Yellow / Red). Per-department summary: payable hours, gross, deductions. Drill-down to individual shift. No access to the Extended Lunch Indicator (RR-H-15).

**Documentation:**
- PRD: PRD-HOTEL-04 General Manager
- Flow: Global Hotel Timesheet
- Prototype: (Figma link)

**Flow:**
`Sidebar → Global Timesheet` → AUTOMATICO → `System consolidates Timesheet of all departments + Calculates Compliance Indicator per collaborator and department` → MANUAL → `Apply filters (department / collaborator / position / week)` → `Click on collaborator to drill-down to shifts` → `Action: Export consolidated / Request report from the Manager / Generate executive report`
