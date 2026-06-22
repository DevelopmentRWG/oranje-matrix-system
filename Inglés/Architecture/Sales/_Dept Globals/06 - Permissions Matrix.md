---
tags:
  - arquitectura
  - departamento/ventas
aliases:
  - Sales Permissions Matrix
---

# PERMISSIONS MATRIX — SALES DEPARTMENT

**PRD-VENTAS-01 · Personnel Management System**

> [!info]
> The **Administrator (ROL-V-04)** role is **on hold** while business rules stabilize.

---

| Module                               | Functionality / Action                 | ROL-V-01 BD | ROL-V-02 BDC | ROL-V-03 System  | ROL-V-04 Admin   |
| ------------------------------------ | -------------------------------------- | ----------- | ------------ | ---------------- | ---------------- |
| **PIPELINE**                         | 👁️ View Pipeline (my territory)       | View        | View (all)   | Auto             | ⏸️               |
|                                      | 👁️ View global Pipeline               | —           | View         | Auto             | ⏸️               |
|                                      | ➕ Identify prospect (Gray)             | Create      | Create       | —                | ⏸️               |
|                                      | 📝 Create hotel profile (Light Blue)   | C · E       | C · E        | —                | ⏸️               |
|                                      | ➕ Register cold visit                  | Create      | Create       | —                | ⏸️               |
|                                      | ➕ Register contact attempts            | Create      | Create       | —                | ⏸️               |
|                                      | 📝 Advance to Yellow (interest)        | C · E       | C · E        | —                | ⏸️               |
|                                      | 📝 Start negotiation (Pink)            | C · E       | C · E        | —                | ⏸️               |
|                                      | 📝 Mark rejection (Red)                | C · E       | —            | —                | ⏸️               |
|                                      | 📝 Reactivate from Red                 | C · E       | —            | —                | ⏸️               |
|                                      | 📝 Mark stall (Brown)                  | C · E       | C · E        | —                | ⏸️               |
|                                      | 🔍 Unblock stall                       | —           | Investigate  | —                | ⏸️               |
|                                      | 📝 Reactivate from Brown               | —           | C · E        | —                | ⏸️               |
|                                      | 📝 Mark Black client                   | —           | C · E        | —                | ⏸️               |
|                                      | 📝 Reactivate from Black               | —           | C · E        | —                | ⏸️               |
| **PROPOSALS**                        | 👁️ View proposals                     | View        | View         | Auto             | ⏸️               |
|                                      | ➕ Draft Personalized Proposal          | Create      | —            | —                | ⏸️               |
|                                      | 📤 Send proposal to hotel              | C · E       | —            | —                | ⏸️               |
| **T&C DOCUMENTS**                    | 👁️ View T&C Documents                 | View        | View         | Auto             | ⏸️               |
|                                      | ➕ Create T&C Document                  | Create      | Create       | —                | ⏸️               |
|                                      | 📝 Edit T&C Document                   | C · E       | C · E        | —                | ⏸️               |
|                                      | ✓ Validate T&C                         | —           | Approve      | —                | ⏸️               |
| **CONVERSION**                       | ➕ Create Hotel User                    | —           | Create       | —                | ⏸️               |
|                                      | ✓ Approve conversion (Pink → Orange)   | —           | Approve      | —                | ⏸️               |
|                                      | 🤖 Automatic Conversion Trigger        | —           | —            | Auto             | ⏸️               |
|                                      | 🤖 Automatic change to Orange          | —           | —            | Auto             | ⏸️               |
| **MY TERRITORY** *(BD)*              | 👁️ View my territory / routes         | View        | —            | Auto             | ⏸️               |
|                                      | 👁️ View prospects by route            | View        | View (all)   | Auto             | ⏸️               |
| **MY TEAM** *(BDC)*                  | 👁️ View BDs in charge                 | —           | View         | —                | ⏸️               |
|                                      | 👁️ View individual metrics per BD     | —           | View         | Auto             | ⏸️               |
|                                      | 📝 Communicate with BD                 | —           | C · E        | —                | ⏸️               |
| **ACTIVE CLIENTS**                   | 👁️ View active clients (contact)      | View        | View         | Auto             | ⏸️               |
| **REPORTS** *(BDC)*                  | ➕ Generate Sales report                | —           | Create       | Auto             | ⏸️               |
|                                      | 📤 Send to management                  | —           | Create       | —                | ⏸️               |
|                                      | 📅 Schedule recurring sending          | —           | C · E        | —                | ⏸️               |
|                                      | 👁️ View report history                | —           | View         | Auto             | ⏸️               |
| **DASHBOARD**                        | 👁️ View personal KPIs                 | View        | View         | Auto             | ⏸️               |
|                                      | 👁️ View global department KPIs        | —           | View         | Auto             | ⏸️               |
| **SYSTEM** *(cross-cutting)*         | 👁️ Receive notification               | View        | View         | Auto             | ⏸️               |
|                                      | ⚙️ Status change traceability          | —           | —            | Auto             | ⏸️               |
|                                      | ⚙️ Send automatic notification         | —           | —            | Auto             | ⏸️               |
| **CONFIGURATION** *(Admin ON HOLD)*  | ⏸️ CRUD users                          | —           | —            | —                | ⏸️ To confirm    |
|                                      | ⏸️ Edit catalogs                       | —           | —            | —                | ⏸️ To confirm    |

---

## Key notes

- **Conversion (RR-V-01):** ONLY the BDC approves. The BD never has access to this action.
- **Conversion precondition (RR-V-02):** The system blocks "Approve conversion" if the previously created Hotel User does not exist.
- **Automatic Trigger (RR-V-03):** 3 parallel actions executed by System, not by BD or BDC.
- **Brown and Black (RR-V-04, RR-V-05):** exclusive to the BDC.
- **Red (RR-V-06):** managed by BD.
- **Reactivations (RR-V-07):** always return to Light Blue, not to Gray.
- **Post-Orange (RR-V-12):** BD and BDC remain as commercial contacts with no operation permissions in the Hotel module.
