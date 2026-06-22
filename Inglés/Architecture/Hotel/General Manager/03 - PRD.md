---
tags:
  - arquitectura
  - rol/manager-general
aliases:
  - PRD General Manager
---

# PRODUCT REQUIREMENTS DOCUMENT
## PRD – GENERAL MANAGER

**Personnel Management System · General Manager (GM) Role of the Hotel**

---

| Field                   | Content                                                                  |
| ----------------------- | ------------------------------------------------------------------------ |
| **PRD ID**              | PRD-HOTEL-04                                                             |
| **User Story**          | HU-HOTEL-04                                                              |
| **Department**          | Hotel                                                                    |
| **Functionality**       | Global visibility of the hotel, supervision of Managers, executive reports |
| **Main Actor**          | General Manager (GM) — extended hierarchy only                          |
| **Device**              | Web – Desktop / Tablet                                                   |
| **Status**              | In definition                                                            |
| **Version**             | 1.0                                                                      |

---

## Objective

Allow the General Manager to **supervise the entire hotel** with consolidated visibility of the Schedule, Timesheet and requisitions of all departments. Detect operational problems in time, escalate critical cases, generate executive reports and keep direction informed.

---

## General Flow

**Login → Global dashboard → Detect imbalances → Supervise Managers → Comment/Escalate/Request report → Generate executive reports → Send to direction**

---

## Use Cases

| ID | Use Case | Priority |
|---|---|---|
| RF-H-22 | View global hotel Schedule | 🟡 Medium |
| RF-H-23 | View global hotel Timesheet | 🟡 Medium |
| RF-H-24 | Generate executive report | 🟡 Medium |
| RF-H-25 | Send report to direction | 🟡 Medium |
| RF-H-26 | Comment on requisition file | 🟢 Low |
| RF-H-27 | Escalate delayed requisition | 🟡 Medium |
| RF-H-28 | Request report from Department Manager | 🟢 Low |

---

## Applicable Business Rules

- **RR-H-13:** The system supports simple and extended hierarchy; this role only applies in extended.
- **RR-H-14:** The General Manager does NOT authorize requisitions (that responsibility falls on each Department Manager).
- **RR-H-15:** No access to the Extended Lunch Indicator.

---

## Restrictions / Permissions

- Does NOT create requisitions.
- Does NOT authorize requisitions (RR-H-14).
- Does NOT generate Timesheet QR.
- Does NOT edit Schedule (consultation only).
- Does NOT correct punches.
- Does NOT put Stand-by nor report collaborator (Red).
- CANNOT add/remove Managers or Supervisors (that is the Administrator's).
- Does NOT see the Extended Lunch Indicator (RR-H-15).
