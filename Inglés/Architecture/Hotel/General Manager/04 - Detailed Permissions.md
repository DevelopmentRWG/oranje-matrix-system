---
tags:
  - arquitectura
  - rol/manager-general
aliases:
  - Detailed Permissions General Manager
---

# DETAILED PERMISSIONS BY ROLE

## ROL-H-03 · 🧑‍✈️ General Manager (GM)

> [!info]
> The General Manager **always exists** (simple and extended hierarchy). In simple, also operates as Area Manager (same user, two roles). In extended, supervises the Area Managers and keeps global visibility, but can also execute operational actions when applicable.

---

| Module                | Functionality                                       | Permission     | Description                                                                                                                                          |
| --------------------- | --------------------------------------------------- | -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Requisitions**      | View global view of the hotel                       | 👁️ View        | All requisitions, all departments                                                                                                                   |
| Requisitions          | Filter by Area Manager / department / status / urgency | 👁️ View     | Broad filters for analysis                                                                                                                           |
| Requisitions          | **Create requisition**                               | ➕ Create       | Shared with Area Manager and Supervisor                                                                                                             |
| Requisitions          | Edit requisition draft                               | 📝 C · E       | Before sending for authorization                                                                                                                    |
| Requisitions          | **Authorize requisition**                            | ✓ Approve      | Shared with Area Manager — RR-H-02                                                                                                                  |
| Requisitions          | **Reject with observations**                         | ✗ Reject       | Shared with Area Manager                                                                                                                            |
| Requisitions          | Delete requisition with positions                    | 📝 C · E       | With individual journal per position                                                                                                                |
| Requisitions          | Comment on file                                      | 📝 C · E       | Visible to the Area Manager                                                                                                                         |
| Requisitions          | Escalate delayed requisition                         | 🔍 Supervise   | Notifies the Recruitment Manager                                                                                                                    |
| **Schedule**          | View global hotel Schedule                           | 👁️ View        | Consolidated of all departments (exclusive to the GM)                                                                                               |
| Schedule              | View Schedule of any department                      | 👁️ View        | Drill-down by department                                                                                                                            |
| Schedule              | **Edit Schedule**                                    | 📝 C · E       | When operating as Area Manager or intervening on specific occasions                                                                                 |
| Schedule              | Export consolidated Schedule                         | 👁️ View        | PDF / CSV / Excel                                                                                                                                     |
| **Timesheet**         | View global hotel Timesheet                          | 👁️ View        | Consolidated of all departments                                                                                                                     |
| Timesheet             | **Generate / Renew QR**                              | ➕ Create       | Shared with Area Manager — RR-H-09                                                                                                                  |
| Timesheet             | **Correct punch**                                    | 📝 C · E       | With mandatory justification — auditable log                                                                                                        |
| Timesheet             | View Compliance Indicator (consolidated)            | 👁️ View        | By department and by collaborator                                                                                                                   |
| Timesheet             | View Extended Lunch Indicator                       | —              | No access (RR-H-15)                                                                                                                                 |
| Timesheet             | Export consolidated Timesheet                        | 👁️ View        | PDF / CSV / Excel                                                                                                                                     |
| **My Personnel**      | View hotel collaborators                             | 👁️ View        | Global view of all departments                                                                                                                      |
| My Personnel          | **Put collaborator in Stand-by (Pink)**             | 📝 C · E       | Shared with Supervisor and Area Manager — RR-H-11                                                                                                   |
| My Personnel          | **Report collaborator (Red)**                        | 🚨 Report      | Shared with Supervisor and Area Manager — RR-H-10                                                                                                   |
| **Accidents**         | View hotel accidents                                 | 👁️ View        | Global, all departments                                                                                                                              |
| Accidents             | **Report accident — Scenarios A and B**             | ➕ Create       | Shared with Supervisor and Area Manager — RR-H-19                                                                                                   |
| **My Hotel Team**     | View Area Managers                                   | 👁️ View        | List with metrics (coverage, authorization time, cases)                                                                                             |
| My Hotel Team         | View Supervisors                                     | 👁️ View        | List with metrics                                                                                                                                   |
| My Hotel Team         | Communicate with Area Manager / Supervisor          | 📝 C · E       | Chat / internal note                                                                                                                                |
| My Hotel Team         | Request specific report                              | ➕ Create       | Notifies the recipient with the request                                                                                                             |
| My Hotel Team         | Add / remove                                         | —              | No access (that is the Administrator's)                                                                                                             |
| **Reports**           | Generate executive report                            | ➕ Create       | Templates (coverage, performance, accidents, quality, indicators) — exclusive to the GM                                                            |
| Reports               | Export (CSV / PDF / Excel)                           | 👁️ View        | —                                                                                                                                                     |
| Reports               | Send to direction                                    | ➕ Create       | Email / internal link                                                                                                                               |
| Reports               | Schedule recurring send                              | 📝 C · E       | Weekly / monthly / quarterly                                                                                                                        |
| Reports               | View report history                                  | 👁️ View        | List with recipient and status                                                                                                                      |
| **Dashboard**         | View global hotel KPIs                               | 👁️ View        | Coverage, compliance, quality, accidents — exclusive executive view                                                                               |
| Dashboard             | Heatmap by department and day                        | 👁️ View        | Executive visualization                                                                                                                             |
| Dashboard             | Ranking of Area Managers                             | 👁️ View        | By authorization speed and coverage                                                                                                                 |
| **System** (cross-cutting) | Receive notification                            | 👁️ View        | Global critical alerts                                                                                                                              |
