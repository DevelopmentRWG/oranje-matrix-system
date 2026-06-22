---
tags:
  - arquitectura
  - rol/manager-de-area
aliases:
  - Area Manager Detailed Permissions
---

# DETAILED PERMISSIONS BY ROLE

## ROL-H-02 · 🧑‍💼 Area Manager / Department Manager

---

| Module                | Functionality                                       | Permission    | Description                                                                                                                                          |
| --------------------- | --------------------------------------------------- | ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Requisitions**      | View dept requisitions                              | 👁️ View       | View by state (pending, authorized, in process, covered, rejected)                                                                                  |
| Requisitions          | **Create requisition**                               | ➕ Create      | **NEW** — Shared with Supervisor and General Manager                                                                                                 |
| Requisitions          | Edit requisition draft                               | 📝 C · E      | Before sending for authorization                                                                                                                     |
| Requisitions          | Authorize requisition                                | ✓ Approve     | Shared with General Manager — RR-H-02                                                                                                                |
| Requisitions          | Reject with observations                             | ✗ Reject      | Returns to the creator with reason                                                                                                                   |
| Requisitions          | Delete requisition with positions                    | 📝 C · E      | Each position moves to Purple with an individual journal (RR-H-08)                                                                                   |
| **Schedule**          | View dept Schedule                                   | 👁️ View       | Full weekly calendar of the dept                                                                                                                     |
| Schedule              | Edit weekly Schedule                                  | 📝 C · E      | Reorders shifts, moves collaborators between days, marks days off                                                                                    |
| Schedule              | Export Schedule                                       | 👁️ View       | PDF / CSV                                                                                                                                             |
| **Timesheet**         | View dept Timesheet                                  | 👁️ View       | Weekly table with 6 punches per shift                                                                                                                |
| Timesheet             | Generate / Renew QR                                   | ➕ Create      | Action of the Area Manager and General Manager — RR-H-09                                                                                             |
| Timesheet             | Correct punch                                         | 📝 C · E      | With mandatory justification — auditable log                                                                                                         |
| Timesheet             | View Compliance Indicator                            | 👁️ View       | Status-lighted per collaborator and shift                                                                                                            |
| Timesheet             | View Extended Lunch Indicator                        | —             | No access (RR-H-15)                                                                                                                                  |
| Timesheet             | Export Timesheet                                      | 👁️ View       | PDF / CSV                                                                                                                                             |
| **My Staff**          | View assigned collaborators                          | 👁️ View       | List with Collaborator Status Light                                                                                                                  |
| My Staff              | Put collaborator on Stand-by (Pink)                  | 📝 C · E      | Shared with Supervisor and General Manager — RR-H-11                                                                                                 |
| My Staff              | Report collaborator (Red)                            | 🚨 Report     | Shared with Supervisor and General Manager — RR-H-10                                                                                                 |
| My Staff              | View collaborator history                            | 👁️ View       | Previous assignments + incidents                                                                                                                     |
| **Accidents**         | View dept accidents                                  | 👁️ View       | List of open and closed cases                                                                                                                        |
| Accidents             | **Report accident — Scenario A**                      | ➕ Create      | **NEW** — Attends after simultaneous notification with Supervisor and Inspector. On-site capture                                                     |
| Accidents             | **Report accident — Scenario B**                      | ➕ Create      | **NEW** — Detects accident and creates the card. Notifies the Inspector                                                                              |
| Accidents             | Capture on-site evidence                             | 📝 C · E      | Photo / video / notes                                                                                                                                |
| **Dashboard**         | View dept KPIs                                        | 👁️ View       | Coverage, requisitions, accidents, compliance                                                                                                        |
| **System** (transv.)  | Receive notification                                 | 👁️ View       | Critical alerts and automatic notifications                                                                                                          |
