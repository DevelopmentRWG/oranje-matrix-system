---
tags:
  - arquitectura
  - departamento/hotel
aliases:
  - Hotel Cover
  - Hotel Department (Cover)
---

# ROLE MANAGEMENT – HOTEL DEPARTMENT

**Roles and User Profiles Template**

---

| Field            | Content                    |
| ---------------- | -------------------------- |
| **Document**     | Roles Template – Hotel     |
| **Department**   | Hotel                      |
| **Related**      | PRD-HOTEL-01 · HU-HOTEL-01 |
| **Version**      | 1.0                        |
| **Status**       | In definition              |

---

## ROLES DEFINED IN THIS DOCUMENT

| ID           | Role · Brief description                                                                                                                                              |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **ROL-H-01** | 🦺 **Supervisor (SUP)** — Creates staffing requisitions, sets Stand-by, reports collaborator (Red) and reports workplace accidents. Subordinate of the Area Manager. |
| **ROL-H-02** | 🧑‍💼 **Area Manager / Department Manager** — Creates, authorizes or rejects requisitions, manages Schedule and Timesheet, generates QR, reports collaborators and accidents. |
| **ROL-H-03** | 🧑‍✈️ **General Manager (GM)** — Highest authority on the hotel side. **Always exists** (in simple hierarchy also operates as Area Manager; in extended hierarchy supervises Area Managers). Has operation + global visibility + executive reports. |
| **ROL-H-04** | ⚙️ **System** — Internal automation: requisition numbering, urgency calculation, Inspector assignment, status lights, journals, notifications.              |
| **ROL-H-05** | 🛠️ **Administrator** — Full system management: users, catalogs, permissions. *(On hold until business rules stabilize.)*                            |

---

## Supported hierarchies

| Hierarchy | Structure | Applicable roles |
|---|---|---|
| **Simple** | General Manager (also operates as Area Manager) → Supervisor → Oranje Collaborators | ROL-H-01, ROL-H-03 (with dual role) |
| **Extended** | General Manager → Area Manager (one per dept) → Supervisor(s) → Collaborators | ROL-H-01, ROL-H-02, ROL-H-03 |

> [!info]
> In simple hierarchy, the **General Manager also operates as Area Manager** (same person, two roles). In extended hierarchy, they are different people: the General Manager supervises and an Area Manager is assigned for each operational department (Housekeeping, Food, Maintenance, Front Desk — see [[Hotel Departments|Hotel Departments]]).

> [!important]
> **Area Manager = Department Manager** (same technical role, two names). The responsibilities on the platform are the same.
