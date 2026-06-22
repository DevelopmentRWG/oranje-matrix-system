---
tags:
  - arquitectura
  - departamento/hotel
aliases:
  - Hotel Permissions Matrix
---

# PERMISSIONS MATRIX — HOTEL DEPARTMENT

**PRD-HOTEL-01 · Staff Management System**

> [!info]
> The **Administrator (ROL-H-05)** role is **on hold** while business rules stabilize. The Admin permissions will be completed at the end.

> [!note]
> The **General Manager (ROL-H-03)** **always exists** (simple and extended hierarchy). In simple hierarchy, it also operates as Area Manager (same person, two roles).

---

| Module | Functionality / Action | ROL-H-01 Supervisor | ROL-H-02 Area Manager | ROL-H-03 General Manager | ROL-H-04 System | ROL-H-05 Admin |
|---|---|---|---|---|---|---|
| **REQUISITIONS** | 👁️ View my requisitions | View | View | View | Auto | ⏸️ |
| | 👁️ View global hotel view | — | Their dept only | View global | Auto | ⏸️ |
| | ➕ Create requisition | Create | Create | Create | — | ⏸️ |
| | 📝 Edit draft | C · E | C · E | C · E | — | ⏸️ |
| | 📤 Send to authorization | Create | Create | Create | — | ⏸️ |
| | ✓ Authorize requisition | — | Approve | Approve | — | ⏸️ |
| | ✗ Reject with remarks | — | Reject | Reject | — | ⏸️ |
| | 🗑️ Delete empty requisition | Create | Create | Create | Auto | ⏸️ |
| | 🗑️ Delete requisition with positions | — | C · E | C · E | Auto | ⏸️ |
| | 🚦 Calculate Urgency Status Light | — | — | — | Auto | ⏸️ |
| | 🤖 Assign Inspector by zone | — | — | — | Auto | ⏸️ |
| | 💬 Comment on the file | — | — | C · E | — | ⏸️ |
| | 🚨 Escalate delayed requisition | — | — | Supervise | — | ⏸️ |
| **SCHEDULE** | 👁️ View dept Schedule | View | View | View | Auto | ⏸️ |
| | 👁️ View global hotel Schedule | — | — | View | Auto | ⏸️ |
| | 📝 Edit weekly Schedule | — | C · E | C · E | — | ⏸️ |
| | 🔄 Reflect authorized positions | — | — | — | Auto | ⏸️ |
| | 🔔 Suggest staff reinforcement | Create | Create | — | — | ⏸️ |
| | 📥 Export Schedule | View | View | View | — | ⏸️ |
| **TIMESHEET** | 👁️ View dept Timesheet | View | View | View | Auto | ⏸️ |
| | 👁️ View global hotel Timesheet | — | — | View | Auto | ⏸️ |
| | 📷 Generate / Renew QR | — | Create | Create | — | ⏸️ |
| | 📝 Correct punch | — | C · E | C · E | Auto | ⏸️ |
| | 🚦 Calculate Compliance Indicator | — | — | — | Auto | ⏸️ |
| | ⏰ View Extended Lunch Indicator | — | — | — | Auto | ⏸️ |
| | 📥 Export Timesheet | View | View | View | — | ⏸️ |
| **MY STAFF** | 👁️ View assigned collaborators | View | View | View | Auto | ⏸️ |
| | 🩷 Put on Stand-by (Pink) | C · E | C · E | C · E | — | ⏸️ |
| | 🔴 Report collaborator (Red) | Report | Report | Report | — | ⏸️ |
| | 👁️ View collaborator history | View | View | View | Auto | ⏸️ |
| **ACCIDENTS** | 👁️ View dept accidents | View | View | View | Auto | ⏸️ |
| | ➕ Create accident card — Scenario A | Create | Create | Create | — | ⏸️ |
| | ➕ Create accident card — Scenario B | Create | Create | Create | — | ⏸️ |
| | 📷 Capture on-site evidence | C · E | C · E | C · E | — | ⏸️ |
| | 🤖 Notify the Inspector | — | — | — | Auto | ⏸️ |
| **MY HOTEL TEAM** *(GM)* | 👁️ View Department Managers | — | — | View | — | ⏸️ |
| | 👁️ View hotel Supervisors | — | — | View | — | ⏸️ |
| | 💬 Communicate with Manager / SUP | — | — | C · E | — | ⏸️ |
| | 📊 Request specific report | — | — | Create | — | ⏸️ |
| **REPORTS** *(GM)* | ➕ Generate executive report | — | — | Create | Auto | ⏸️ |
| | 📤 Send to management | — | — | Create | — | ⏸️ |
| | 📅 Schedule recurring submission | — | — | C · E | — | ⏸️ |
| | 👁️ View report history | — | — | View | Auto | ⏸️ |
| **DASHBOARD** | 👁️ View personal KPIs | View | View | View | Auto | ⏸️ |
| | 👁️ View dept KPIs | — | View | View | Auto | ⏸️ |
| | 👁️ View global hotel KPIs | — | — | View | Auto | ⏸️ |
| **SYSTEM** *(cross-cutting)* | 👁️ Receive notification | View | View | View | Auto | ⏸️ |
| | ⚙️ Send automatic notification | — | — | — | Auto | ⏸️ |
| | 🔢 Automatic requisition numbering | — | — | — | Auto | ⏸️ |
| **CONFIGURATION** *(Admin ON HOLD)* | ⏸️ Configure alerts | — | — | — | — | ⏸️ To be confirmed |
| | ⏸️ User CRUD | — | — | — | — | ⏸️ To be confirmed |
| | ⏸️ Edit catalogs | — | — | — | — | ⏸️ To be confirmed |

---

## Key notes

- **Create requisition:** now all **3 roles** can (Supervisor, Area Manager, General Manager).
- **Authorization (RR-H-02):** Area Manager **or** General Manager. The Supervisor CANNOT authorize.
- **Timesheet QR (RR-H-09):** Area Manager **or** General Manager.
- **Report collaborator / Red (RR-H-10):** all **3 roles** can report (shared).
- **Stand-by / Pink (RR-H-11):** shared among the **3 roles**.
- **Report accidents (RR-H-19):** all **3 roles** can report (Scenarios A and B).
- **Extended Lunch Indicator (RR-H-15):** restricted for all Hotel roles — only the Inspector, Inspection Coordinator and Recruitment Manager see it.
- **General Manager:** has **operation + supervision**. Shares all operational actions with the Area Manager, plus exclusive executive functions (global visibility, reports to management, supervision of Area Managers).
- **In simple hierarchy:** the General Manager also operates as Area Manager (same person, two roles).
