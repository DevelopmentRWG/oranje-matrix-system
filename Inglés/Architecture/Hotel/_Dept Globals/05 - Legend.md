---
tags:
  - arquitectura
  - departamento/hotel
aliases:
  - Hotel Permissions Legend
---

# LEGEND – PERMISSIONS MATRIX

---

## Symbols / Colors

| Symbol / Color    | Meaning                                         | Applies To                                        |
| ----------------- | ----------------------------------------------- | ------------------------------------------------- |
| ✅ **CRUD**        | Full access: Create, View, Edit, Delete         | Administrator                                     |
| ➕ **Create**      | Can only create new records                     | Supervisor / Area Manager                       |
| 👁️ **View**      | Read-only / query                               | All roles                                         |
| 📝 **C · E**      | Create and Edit (no delete)                     | Supervisor / Area Manager                       |
| ✓ **Approve**     | Can approve the action (authorize requisition)  | Area Manager                                    |
| ✗ **Reject**      | Can reject the action                           | Area Manager                                    |
| 🚨 **Report**     | Can report a collaborator or accident           | Area Manager (Red) / Supervisor (accident)      |
| 🔍 **Supervise**  | Global visibility with escalation action        | General Manager                                   |
| ⚙️ **Auto**       | Action executed automatically by the system     | System (backend)                                 |
| —                 | No permission – access denied                   | Depending on context                             |
| ⏸️                | On hold (Admin)                                 | Administrator                                     |

---

## ROLES IN THIS DOCUMENT

| ID           | Role                                                         |
| ------------ | ------------------------------------------------------------ |
| **ROL-H-01** | 🦺 Supervisor (SUP)                                          |
| **ROL-H-02** | 🧑‍💼 Area Manager / Department Manager                      |
| **ROL-H-03** | 🧑‍✈️ General Manager (GM) — extended hierarchy only          |
| **ROL-H-04** | ⚙️ System                                                    |
| **ROL-H-05** | 🛠️ Administrator *(on hold)*                                 |

---

## Notes

- **Area Manager** and **Department Manager** are the same technical role. The difference is only the scope: in simple hierarchy it covers the whole hotel; in extended hierarchy it covers only its department (Housekeeping, Food, Maintenance, Front Desk).
- The **General Manager** exists only in extended hierarchy. In simple hierarchy, the Area Manager is the highest authority on the hotel side.
- The business rules (RR-H-XX) are in [[07 - Business Rules|07 - Business Rules]].
