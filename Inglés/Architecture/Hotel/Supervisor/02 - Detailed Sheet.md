---
tags:
  - arquitectura
  - rol/supervisor-hotel
aliases:
  - Supervisor Detailed Sheet
---

# DETAILED SHEET — SUPERVISOR

---

| Field                          | Content                                                                                                                                                                                                                              |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Role ID**                    | ROL-H-01                                                                                                                                                                                                                               |
| **Role Name**                  | 🦺 Supervisor (SUP)                                                                                                                                                                                                                    |
| **Description**                | Operational role of the Hotel module. Creates the staffing requisitions and reports workplace accidents. Subordinate to the Area Manager / Department Manager.                                                                       |
| **Objective in the System**    | Formalize the hotel's staffing need through requisitions; report accidents with on-site detail.                                                                                                                      |
| **Modules Used**               | Dashboard · Requisitions · Schedule (read-only) · Timesheet (read-only) · My Staff · Accidents · Notifications                                                                                                                     |
| **Permissions (CRUD)**         | Create · View · Edit (no deletion except drafts) · Report accidents                                                                                                                            |
| **Main Actions**               | Create requisition · Edit draft · Send for authorization · Suggest reinforcement · Report accident Scenario A · Report accident Scenario B · Put on Stand-by                                                                      |
| **Access Level**               | 🟡 Medium (operational)                                                                                                                                                                                                                   |
| **Device**                     | Mobile (Supervisor app) / Tablet / Desktop                                                                                                                                                                                          |
| **Usage Frequency**            | High — daily                                                                                                                                                                                                                          |
| **Pain / Current Need**        | Creating requisitions takes a long time from Desktop if not near the office; when detecting an accident they must physically attend and record on paper; lack of visibility over rejected requisitions until they enter the system. |
| **UX Notes / Recommendations** | Mobile-first app with fast creation (3-4 steps), push notifications for accidents and rejections, accident form with photo capture and optional geolocation, dashboard with a prioritized "needs action" inbox. |
