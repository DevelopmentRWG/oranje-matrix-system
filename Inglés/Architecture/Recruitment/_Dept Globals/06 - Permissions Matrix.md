---
tags:
  - arquitectura
  - departamento/reclutamiento
aliases:
  - Recruitment Permissions Matrix
---

# PERMISSIONS MATRIX — RECRUITMENT DEPARTMENT

**PRD-RECL-01 · Personnel Management System**

> [!info]
> The **Administrator (ROL-05)** role is **paused** while the business rules stabilize. The Admin permissions will be completed at the end.

---

| Module | Functionality / Action | ROL-01 Recruiter | ROL-02 Group Leader | ROL-03 Manager | ROL-04 System | ROL-05 Admin |
|---|---|---|---|---|---|---|
| **REQUISITION** | 👁️ View Authorized queue | View | View | View | Auto | ⏸️ |
| | 🎯 Take requisition (Collaborative Self-Pick) | Create (adds participant) | Create (adds participant) | Create | Auto | ⏸️ |
| | 🤝 Take/Join an already-taken requisition | Create | Create | — | Auto | ⏸️ |
| | 📝 Release taken requisition (Leave) | C · E | C · E | C · E | Auto | ⏸️ |
| | 👁️ View active recruiters | View | View | View | Auto | ⏸️ |
| | 👁️ View Requisition History | View | View | View | Auto | ⏸️ |
| | 📝 Mark requisition in progress | C · E | C · E | — | Auto | ⏸️ |
| | ✅ Mark requisition as covered | C · E (requests) | ✓ Approve (closure) | View | Auto | ⏸️ |
| | 👁️ View global view | — | View | View | Auto | ⏸️ |
| | ⚠️ Assign manually (exception) | — | — | C · E | — | ⏸️ |
| | 🚦 Calculate Urgency Status Light | — | — | — | Auto | ⏸️ |
| | 🚦 Calculate Positions Status Light | — | — | — | Auto | ⏸️ |
| | 📝 Force status light change | — | — | C · E | Auto | ⏸️ |
| **RECRUITMENT** | 👁️ View Collaborator Pool | View | View | View | Auto | ⏸️ |
| | 🔍 Search / filter candidates | View | View | View | Auto | ⏸️ |
| | ➕ Create collaborator (Phase 1 registration) | Create | Create | Create | — | ⏸️ |
| | 📝 Edit collaborator | C · E | C · E | C · E | — | ⏸️ |
| | 📝 Validate app registration (Phase 2) | C · E | C · E | — | Auto | ⏸️ |
| | ➕ Enable access | Create | Create | — | Auto | ⏸️ |
| | ➕ Register interview | Create | Create | — | Auto | ⏸️ |
| | 👁️ View interview history | View | View | View | Auto | ⏸️ |
| | ➕ Assign collaborator to hotel | Create | Create | C · E | Auto | ⏸️ |
| | ➕ Assign to Schedule | Create | Create | C · E | Auto | ⏸️ |
| | 📝 Reassign collaborator | C · E | C · E | C · E | — | ⏸️ |
| | 📝 Unassign collaborator | C · E | C · E | C · E | — | ⏸️ |
| **BLACKLIST** | 👁️ Check Blacklist | View | View | View | Auto | ⏸️ |
| | ➕ Add to Blacklist | Create | Create | Create | — | ⏸️ |
| | 🔍 Resolve dispute | — | — | Investigate | — | ⏸️ |
| | 📝 Remove from Blacklist | — | — | C · E | — | ⏸️ |
| **MY GROUP** *(Leader)* | 👁️ View group Recruiters | — | View | — | — | ⏸️ |
| | 👁️ View individual metrics | — | View | View | Auto | ⏸️ |
| | 👁️ View detailed Recruiter workload | — | View | — | — | ⏸️ |
| | 📝 Reassign requisition to Recruiter | — | C · E | — | — | ⏸️ |
| | 📝 Mark Recruiter availability | — | C · E | — | — | ⏸️ |
| **MY TEAM** *(Manager)* | 👁️ View Leaders + Recruiters | — | — | View | — | ⏸️ |
| | ➕ Register Leader/Recruiter | — | — | Create | — | ⏸️ |
| | 📝 Edit dept user | — | — | C · E | — | ⏸️ |
| | 📝 Move Recruiter to another Leader | — | — | C · E | — | ⏸️ |
| **INCIDENTS** *(Manager)* | ✓ Resolve incident | — | — | Approve | — | ⏸️ |
| | 🚨 Escalate to commercial | — | C · E | C · E | — | ⏸️ |
| **REPORTS** | ➕ Generate group report | — | Create | Create | Auto | ⏸️ |
| | ✅ Send report to the Manager | — | Approve | — | — | ⏸️ |
| | 👁️ View individual coverage | View | View | View | Auto | ⏸️ |
| | 👁️ View coverage by zone | — | View | View | Auto | ⏸️ |
| | 👁️ View global coverage | — | — | View | Auto | ⏸️ |
| **DASHBOARD** | 👁️ View personal KPIs | View | View | View | Auto | ⏸️ |
| | 👁️ View group KPIs | — | View | View | Auto | ⏸️ |
| | 👁️ View global KPIs | — | — | View | Auto | ⏸️ |
| **SYSTEM** *(cross-cutting)* | 👁️ Receive notification | View | View | View | Auto | ⏸️ |
| | ⚙️ Send automatic notification | — | — | — | Auto | ⏸️ |
| **CONFIGURATION** *(Admin PAUSED)* | ⏸️ Configure alerts | — | — | — | — | ⏸️ To be confirmed |
| | ⏸️ User CRUD | — | — | — | — | ⏸️ To be confirmed |
| | ⏸️ Edit catalogs | — | — | — | — | ⏸️ To be confirmed |

---

## Changes from the previous version

- **Collaborative requisition** — `Take requisition (Collaborative Self-Pick)` now adds a participating recruiter (it is not exclusive) and `Release` becomes `Leave`. `Take/Join an already-taken requisition` (Recruiter/Leader), `View active recruiters` and `View Requisition History` are added (RR-15 and RR-16).
- **Blacklist** — The `Add to Blacklist` column is now `Create` for the 3 dept roles (Recruiter, Leader, Manager). Before, only the Manager could. The updated rule (RR-03) leaves the Manager as the only one who **resolves disputes** and **removes**.
- **Reorganized submodules** — Pool, Interviews and Assignment now sit inside the **RECRUITMENT** module. Requisition taking and the status lights sit inside the **REQUISITION** module.
- **Notifications** is no longer a sidebar module — it moved to the "System (cross-cutting)" section.
- **Schedule** is no longer a separate module — it is a contextual view inside the assignment process.
- **Admin paused** — all ROL-05 cells marked with ⏸️.
