---
tags:
  - arquitectura
  - rol/supervisor-hotel
aliases:
  - Supervisor Detailed Permissions
---

# DETAILED PERMISSIONS BY ROLE

## ROL-H-01 · 🦺 Supervisor (SUP)

---

| Module                | Functionality                                       | Permission  | Description                                                       |
| --------------------- | --------------------------------------------------- | ----------- | ----------------------------------------------------------------- |
| **Requisitions**      | View my requisitions                                | 👁️ View    | Filtered by the ones I created                                   |
| Requisitions          | View global hotel view                              | —           | No access (only Area Manager and General Manager)               |
| Requisitions          | Create requisition                                  | ➕ Create    | Main action of the role                                          |
| Requisitions          | Edit draft                                          | 📝 C · E    | Free editing before sending                                     |
| Requisitions          | Send for authorization                              | ➕ Create    | Sends to the Area Manager                                       |
| Requisitions          | Delete draft                                        | ➕ Create    | Auto if requisition is empty (RR-H-07)                           |
| Requisitions          | Authorize                                           | —           | No access (RR-H-02)                                              |
| Requisitions          | Reject                                              | —           | No access                                                        |
| **Schedule**          | View department Schedule                            | 👁️ View    | Weekly calendar view of the department                            |
| Schedule              | Edit Schedule                                       | —           | No access (only Area Manager)                               |
| Schedule              | Suggest staffing reinforcement                      | ➕ Create    | Generates a new requisition prefill from a vacant position         |
| Schedule              | Export Schedule                                     | 👁️ View    | PDF / CSV                                                          |
| **Timesheet**         | View department Timesheet                           | 👁️ View    | Weekly table × collaborator with 6 clock-ins                         |
| Timesheet             | Generate QR                                         | —           | No access (RR-H-09)                                              |
| Timesheet             | Correct clock-in                                    | —           | No access (only Area Manager)                               |
| Timesheet             | View Compliance Indicator                           | 👁️ View    | Status-lit per collaborator                                       |
| Timesheet             | View Extended Lunch Indicator                       | —           | No access (RR-H-15)                                              |
| Timesheet             | Export Timesheet                                    | 👁️ View    | PDF / CSV                                                          |
| **My Staff**          | View assigned collaborators                         | 👁️ View    | Department list                                                   |
| My Staff              | Put collaborator on Stand-by (Pink)                 | 📝 C · E    | Shared with Area Manager and General Manager (RR-H-11)        |
| My Staff              | **Report collaborator (Red)**                       | 🚨 Report   | **NEW** — Shared with Area Manager and General Manager (RR-H-10)|
| My Staff              | View collaborator history                           | 👁️ View    | Assignments and incidents                                        |
| **Accidents**         | View department accidents                           | 👁️ View    | List of open and closed cases                                |
| Accidents             | Report accident — Scenario A                        | ➕ Create    | On-site capture after simultaneous notification with Inspector     |
| Accidents             | Report accident — Scenario B                        | ➕ Create    | Creates card when detected first                               |
| Accidents             | Capture on-site evidence                            | 📝 C · E    | Photo / video / notes                                              |
| **Dashboard**         | View personal KPIs                                  | 👁️ View    | My requisitions, reported accidents                          |
| **System** (cross-cutting) | Receive notification                           | 👁️ View    | Alerts and notifications                                          |
