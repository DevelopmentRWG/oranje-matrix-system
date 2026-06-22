---
tags:
  - arquitectura
  - rol/manager-de-area
aliases:
  - Area Manager Detailed Sheet
---

# DETAILED SHEET — AREA MANAGER

---

| Field                          | Content                                                                                                                                                                                                                                              |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Role ID**                    | ROL-H-02                                                                                                                                                                                                                                               |
| **Role Name**                  | 🧑‍💼 Area Manager / Department Manager                                                                                                                                                                                                              |
| **Description**                | Supervision role on the hotel side. Authorizes/rejects the Supervisor's requisitions (security layer), manages Schedule and Timesheet, generates the punch QR and administers the assigned collaborators.                                            |
| **Objective in the System**    | Validate staff requests, manage the dept's Schedule and Timesheet, and keep the daily operation running.                                                                                                                                              |
| **Modules It Uses**            | Dashboard · Requisitions · Schedule · Timesheet · My Staff · Notifications                                                                                                                                                  |
| **Permissions (CRUD)**         | Create · View · Edit · Approve · Reject · Report                                                                                                                                                                                                   |
| **Main Actions**               | Authorize requisition · Reject with observations · Generate QR · Edit Schedule · Correct punch · Put on Stand-by (Pink) · Report (Red) · Delete requisition with positions                                                                    |
| **Access Level**               | 🟠 High (in its dept)                                                                                                                                                                                                                                  |
| **Device**                     | Desktop / Tablet                                                                                                                                                                                                                                       |
| **Frequency of Use**           | High — daily                                                                                                                                                                                                                                          |
| **Current Pain / Need**        | Lack of visibility over requisitions pending review, frequent errors in the Schedule (crossed shifts), manual punch correction without traceability, absence of early alerts on Timesheet compliance.                |
| **UX Notes / Recommendations** | Pending inbox with a red badge if it has gone >24h without review; consolidated Schedule + Timesheet view; renewable QR with 1 click; punch correction with mandatory justification visible in the log; push alerts on mobile when a critical notification is issued. |
