---
tags:
  - arquitectura
  - rol/manager-de-area
aliases:
  - Area Manager PRD
---

# PRODUCT REQUIREMENTS DOCUMENT
## PRD – AREA MANAGER

**Staff Management System · Area Manager / Department Manager Role**

---

| Field                   | Content                                                                            |
| ----------------------- | ------------------------------------------------------------------------------------ |
| **PRD ID**              | PRD-HOTEL-03                                                                         |
| **User Story**          | HU-HOTEL-03                                                                          |
| **Department**          | Hotel                                                                                |
| **Functionality**       | Authorize requisitions, manage Schedule and Timesheet, administer assigned staff |
| **Main Actor**          | Area Manager / Department Manager                                          |
| **Device**              | Web – Desktop / Tablet                                                               |
| **Status**              | In definition                                                                        |
| **Version**             | 1.0                                                                                  |

---

## Objective

Allow the Area Manager to **review and authorize** the requisitions the Supervisor creates (security layer before Recruitment), **manage the dept's Schedule and Timesheet**, **generate the punch QR**, and **administer the assigned collaborators** (Stand-by, Report).

---

## General Flow

**Receives requisition from the Supervisor → Reviews → Authorizes/Rejects → Recruitment takes it → Collaborators assigned → Generates QR → Weekly management of Schedule + Timesheet → Stand-by / Report when applicable**

---

## Use Cases

| ID | Use Case | Priority |
|---|---|---|
| RF-H-05 | Authorize requisition | 🔴 High |
| RF-H-06 | Reject requisition with observations | 🔴 High |
| RF-H-07 | Delete requisition with positions | 🟡 Medium |
| RF-H-11 | Generate / Renew Timesheet QR | 🔴 High |
| RF-H-12 | Edit weekly Schedule | 🔴 High |
| RF-H-14 | Correct Timesheet punch | 🟡 Medium |
| RF-H-15 | Consult Timesheet | 🔴 High |
| RF-H-17 | Put collaborator on Stand-by (Pink) | 🔴 High |
| RF-H-18 | Report collaborator (Red) | 🔴 High |

---

## Applicable Business Rules

- **RR-H-02:** Only the Area Manager can authorize requisitions (security layer).
- **RR-H-03:** The requisition must have ≥1 position to authorize.
- **RR-H-09:** QR generation exclusive to the Area Manager.
- **RR-H-10:** Collaborator report (Red) exclusive to the Area Manager.
- **RR-H-11:** Stand-by (Pink) shared with the Supervisor.
- **RR-H-15:** No access to the Extended Lunch Indicator.

---

## Restrictions / Permissions

- CANNOT create requisitions (that is the Supervisor's).
- Does NOT access the Extended Lunch Indicator.
- CANNOT register users (that is the Administrator's).
