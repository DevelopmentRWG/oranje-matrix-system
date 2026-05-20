---
tags:
  - module/core
aliases:
  - Requisition Positions Status Indicator
  - Positions Status Indicator
  - Positions Status Gold
  - Positions Status Orange
  - Positions Status Green
  - Positions Status Yellow
  - Positions Status Red
  - Positions Status Purple
---

# Requisition Positions Status Indicator

Visual state of the coverage percentage of each position within a [[Requisición]]. Indicates how close each position is to being fully covered by the [[Reclutadora]].

> [!info]
> This is one of the requisition Status Indicators. See also: [[Semáforo de Requisición]], [[Semáforo de Urgencia de Requisición]] and [[Semáforo del Colaborador]].

> [!note] Equivalence with the technical system
> The documentation uses color names in Spanish, while the internal system names them in English: Dorado=Gold · Naranja=Orange · Verde=Green · Amarillo=Yellow · Rojo=Red · Morado=Purple. Both names are valid aliases.

## States

| Color  | State               | Responsible                                                                    | Description                                                                                          |
| ------ | ------------------- | ------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------- |
| Gold   | In preparation      | [[Hotel/Manager General\|GM]], [[Hotel/Manager de Área\|GH]] or [[Hotel/Supervisor\|SUP]] | Position being prepared by the hotel.                                                         |
| Orange | Authorized          | [[Hotel/Manager General\|GM]] or [[Hotel/Manager de Área\|GH]]                             | Position authorized by the hotel. The system calculates priority ([[Semáforo de Urgencia de Requisición]]). |
| Green  | 100% covered        | [[Reclutadora]]                                                                | Position covered at 100%.                                                                            |
| Yellow | Up to 25% missing   | [[Reclutadora]]                                                                | Up to 25% of staff missing.                                                                          |
| Red    | More than 25% missing | [[Reclutadora]]                                                              | More than 25% of staff missing.                                                                      |
| Purple | Deleted             | —                                                                              | Position physically deleted.                                                                         |

## Detail by state

### Gold — In preparation
**Responsible:** [[Hotel/Manager General|GM]], [[Hotel/Manager de Área|GH]] or [[Hotel/Supervisor|SUP]]

The position is created alongside the requisition and prepared with its data (profile, quantity, start date).

**Advance →** when the [[Hotel/Manager General|GM]] or the [[Hotel/Manager de Área|GH]] authorizes the complete requisition, each position moves to [[#Orange — Authorized|Orange]] and the system calculates its priority.

---

### Orange — Authorized
**Responsible:** [[Hotel/Manager General|GM]] or [[Hotel/Manager de Área|GH]]

The position is ready for assignment. The system automatically associates an urgency level (see [[Semáforo de Urgencia de Requisición]]).

**Advance →** based on coverage managed by the [[Reclutadora]]:
- 100% covered → [[#Green — 100% covered|Green]]
- Up to 25% missing → [[#Yellow — Up to 25% missing|Yellow]]
- More than 25% missing → [[#Red — More than 25% missing|Red]]

---

### Green — 100% covered
**Responsible:** [[Reclutadora]]

All associates assigned to this position are confirmed.

---

### Yellow — Up to 25% missing
**Responsible:** [[Reclutadora]]

Up to 25% of staff is missing. The recruiter continues searching for coverage.

---

### Red — More than 25% missing
**Responsible:** [[Reclutadora]]

More than 25% is missing. Requires priority attention.

---

### Purple — Deleted

Cross-cutting state. Reached from any state when the position is physically deleted; the system logs a journal entry.

## Business Rules

- **Relationship with [[Semáforo de Requisición]]:**
  - The requisition becomes **Light Blue** when **all** its positions reach `Green`.
  - The requisition becomes **Red** if at least one position closes in `Yellow` or `Red`.
- **Priority** (Urgency) is calculated automatically when moving to `Orange`.
- **Deletion**: can happen in any state (→ `Purple`).

## Related

- [[Requisición]]
- [[Posiciones]]
- [[Semáforo de Requisición]]
- [[Semáforo de Urgencia de Requisición]]
- [[Reclutadora]]
