---
tags:
  - modulo/core
aliases:
  - Requisition Positions Status Light
  - Positions Status Light
  - Positions Status Gold
  - Positions Status Orange
  - Positions Status Green
  - Positions Status Yellow
  - Positions Status Red
  - Positions Status Purple
---

# Requisition Positions Status Light

Visual status of the coverage percentage of each position within a [[Requisition|Requisition]]. Indicates how close each position is to being fully covered by the [[Recruiter|Recruiter]].

> [!info]
> This is one of the requisition's status lights. See also: [[Requisition Status Light|Requisition Status Light]], [[Requisition Urgency Status Light|Requisition Urgency Status Light]] and the [[Collaborator Status Light|Collaborator Status Light]].

> [!note] Equivalence with the technical system
> The documentation uses color names, and the internal system names them the same: Gold · Orange · Green · Yellow · Red · Purple. Both names are valid aliases.

## States

| Color  | State               | Responsible                                                           | Description                                                                                         |
| ------ | ------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Gold   | In preparation      | [[Hotel/General Manager\|GM]], [[Hotel/Area Manager\|GH]] or [[Hotel/Supervisor\|SUP]] | Position in preparation by the hotel.                                                               |
| Orange | Authorized          | [[Hotel/General Manager\|GM]] or [[Hotel/Area Manager\|GH]]                                       | Position authorized by the hotel. The system calculates priority ([[Requisition Urgency Status Light\|Requisition Urgency Status Light]]). |
| Green  | 100% covered        | [[Recruiter\|Recruiter]]                                            | Position 100% covered.                                                                              |
| Yellow | Up to 25% missing   | [[Recruiter\|Recruiter]]                                            | Up to 25% of staff missing.                                                                         |
| Red    | More than 25% missing | [[Recruiter\|Recruiter]]                                          | More than 25% of staff missing.                                                                     |
| Purple | Removed             | —                                                                     | Position physically removed.                                                                        |

## Detail by state

### Gold — In preparation
**Responsible:** [[Hotel/General Manager|GM]], [[Hotel/Area Manager|GH]] or [[Hotel/Supervisor|SUP]]

The position is created together with the requisition and is prepared with its data (profile, quantity, start date).

**Advance →** when the [[Hotel/General Manager|GM]] or the [[Hotel/Area Manager|GH]] authorizes the complete requisition, each position moves to [[#Orange — Authorized|Orange]] and the system calculates its priority.

---

### Orange — Authorized
**Responsible:** [[Hotel/General Manager|GM]] or [[Hotel/Area Manager|GH]]

The position is ready for assignment. The system automatically associates an urgency level (see [[Requisition Urgency Status Light|Requisition Urgency Status Light]]).

> [!note] Collaborative granularity
> Under the collaborative model (RR-15), **each position/slot can have its own assigned recruiter**: several participating recruiters work the same requisition and each one covers the positions they take. **Assigning** or **removing** a collaborator from a position records the **actor** (role and name) in the [[Core/Modules/Requisition/Requisition#Historial de la Requisición|Requisition History]] (RR-16). The concurrency lock operates at this level: two recruiters do not assign the same collaborator to the same slot — the first wins, the second sees "position already covered".

**Advance →** according to the coverage managed by the participating recruiters:
- 100% covered → [[#Green — 100% covered|Green]]
- Up to 25% missing → [[#Yellow — Up to 25% missing|Yellow]]
- More than 25% missing → [[#Red — More than 25% missing|Red]]

---

### Green — 100% covered
**Responsible:** [[Recruiter|Recruiter]]

All collaborators assigned to this position are confirmed.

---

### Yellow — Up to 25% missing
**Responsible:** [[Recruiter|Recruiter]]

Up to 25% of staff is missing. The recruiter continues searching for coverage.

---

### Red — More than 25% missing
**Responsible:** [[Recruiter|Recruiter]]

More than 25% is missing. Requires priority attention.

---

### Purple — Removed

Cross-cutting state. It is reached from any state when the position is physically removed; the system records a journal entry.

## Key rules

- **Relationship with [[Requisition Status Light|Requisition Status Light]]:**
  - The requisition becomes **Light Blue** when **all** its positions reach `Green`.
  - The requisition becomes **Red** if at least one position closes in `Yellow` or `Red`.
- **Priority** (Urgency) is calculated automatically when moving to `Orange`.
- **Removal**: can happen in any state (→ `Purple`).
- **Collaborative granularity (RR-15):** each position/slot can have its assigned recruiter; the concurrency lock is per position/slot, not per complete requisition.
- **Traceability (RR-16):** assigning/removing a collaborator from a position records the **actor** in the [[Core/Modules/Requisition/Requisition#Historial de la Requisición|Requisition History]].

## Related

- [[Requisition|Requisition]]
- [[Posiciones|Positions]]
- [[Requisition Status Light|Requisition Status Light]]
- [[Requisition Urgency Status Light|Requisition Urgency Status Light]]
- [[Recruiter|Recruiter]]
