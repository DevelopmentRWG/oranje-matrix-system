---
tags:
  - arquitectura
  - rol/supervisor-hotel
aliases:
  - Supervisor PRD
---

# PRODUCT REQUIREMENTS DOCUMENT
## PRD – SUPERVISOR

**Staff Management System · Supervisor (SUP) Role of the Hotel**

---

| Field                   | Content                                                                  |
| ----------------------- | -------------------------------------------------------------------------- |
| **PRD ID**              | PRD-HOTEL-02                                                               |
| **User Story**          | HU-HOTEL-02                                                                |
| **Department**          | Hotel                                                                      |
| **Functionality**       | Create staffing requisitions and report on-site workplace accidents  |
| **Main Actor**          | Supervisor (SUP)                                                           |
| **Device**              | Mobile (priority) / Tablet / Desktop                                    |
| **Status**              | In definition                                                              |
| **Version**             | 1.0                                                                        |

---

## Objective

Allow the Supervisor to **formalize the hotel's staffing need** through requisitions that the Area Manager will authorize so Recruitment can cover them. In addition, give the Supervisor the tools to **report workplace accidents in scenarios A and B** with on-site capture.

---

## General Flow

**Detects staffing need → Creates requisition (mobile) → Sends to Area Manager → Awaits authorization → If rejected, corrects and resends → Once authorized, it is in Recruitment's hands → Daily operation: consults Schedule, Timesheet, reports accidents**

---

## Use Cases

| ID | Use Case | Priority |
|---|---|---|
| RF-H-01 | Create requisition | 🔴 High |
| RF-H-02 | Edit requisition draft | 🔴 High |
| RF-H-03 | Send requisition for authorization | 🔴 High |
| RF-H-04 | Delete draft / empty requisition | 🟡 Medium |
| RF-H-13 | Consult Schedule | 🔴 High |
| RF-H-15 | Consult Timesheet | 🔴 High |
| RF-H-17 | Put collaborator on Stand-by (Pink) | 🔴 High |
| RF-H-19 | Suggest staffing reinforcement | 🟢 Low |
| RF-H-20 | Report accident — Scenario A | 🔴 High |
| RF-H-21 | Report accident — Scenario B | 🔴 High |

---

## Applicable Business Rules

- **RR-H-02:** The Supervisor CANNOT authorize requisitions (security layer).
- **RR-H-03:** The requisition must have ≥1 position to send for authorization.
- **RR-H-11:** Stand-by (Pink) shared with Area Manager.
- **RR-H-12:** Access to the requisitions module restricted to the Supervisor and Area Manager.
- **RR-H-15:** No access to the Extended Lunch Indicator.
- **RR-H-19:** Accident reporting in scenarios A and B.
- **RR-H-20:** Collaborator in an accident switches to Gray (3-absence protection).

---

## Restrictions / Permissions

- CANNOT authorize requisitions.
- CANNOT generate the Timesheet QR.
- CANNOT correct clock-ins.
- CANNOT report a collaborator (Red).
- CANNOT edit the Schedule (read-only).
