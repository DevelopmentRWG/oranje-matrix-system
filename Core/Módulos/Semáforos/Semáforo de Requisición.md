---
tags:
  - module/core
aliases:
  - Requisition Status Indicator
  - Requisition Status Apple Green
  - Requisition Status Green
  - Requisition Status Yellow
  - Requisition Status Light Blue
  - Requisition Status Red
  - Requisition Status Purple
---

# Requisition Status Indicator

Visual status system that represents the lifecycle of a [[Requisición]], from when the [[Hotel/Manager General|General Manager]], the [[Hotel/Manager de Área|Area Manager]] or the [[Hotel/Supervisor|Supervisor]] begin drafting it until it is fully covered.

> [!info]
> This Status Indicator describes the **general lifecycle** of the requisition. The other dimensions are managed in separate Status Indicators: [[Semáforo de Urgencia de Requisición]] (classification by time) and [[Semáforo de Posiciones de la Requisición]] (coverage percentage per position). For the associate's state see [[Semáforo del Colaborador]].

> [!note] Parallelism with [[Semáforo de Posiciones de la Requisición]]
> Each requisition state has its mirror at the position level: `Apple Green`↔`Gold` · `Green`↔`Orange` · `Light Blue`↔`Green` · `Red`↔`Yellow/Red` · `Purple`↔`Purple`.

## States

| Color       | State               | Responsible                                                                 | Description                                  |
| ----------- | ------------------- | --------------------------------------------------------------------------- | -------------------------------------------- |
| Apple Green | In preparation      | [[Hotel/Manager General\|GM]], [[Hotel/Manager de Área\|GH]] or [[Hotel/Supervisor\|SUP]] | Being drafted by the hotel.           |
| Green       | Authorized          | [[Hotel/Manager General\|GM]] or [[Hotel/Manager de Área\|GH]]                            | Authorized by the hotel.              |
| Yellow      | In progress         | [[Reclutadora]] (taken from the shared tray)                                | In the process of staff assignment.          |
| Light Blue  | Fully covered       | [[Reclutadora]]                                                             | Requisition fully covered.                   |
| Red         | Partially covered   | [[Reclutadora]]                                                             | Requisition partially covered.               |
| Purple      | Deleted             | —                                                                           | Requisition physically deleted.              |

## Detail by state

### Apple Green — In preparation
**Responsible:** [[Hotel/Manager General|GM]], [[Hotel/Manager de Área|GH]] or [[Hotel/Supervisor|SUP]]

The hotel begins creating the requisition and its positions.

**Advance →** when the [[Hotel/Manager General|GM]] or the [[Hotel/Manager de Área|GH]] authorizes the requisition, it moves to [[#Green — Authorized|Green]]. Only the GM or GH can authorize; if the SUP attempts it, the system blocks the action.

---

### Green — Authorized
**Responsible:** [[Hotel/Manager General|GM]] or [[Hotel/Manager de Área|GH]]

The requisition is ready for assignment. The system automatically calculates urgency (see [[Semáforo de Urgencia de Requisición]]).

**Advance →** a [[Reclutadora]] or [[Reclutamiento/Líder de Grupo de Reclutadoras|Recruiter Team Lead]] takes the requisition from the shared tray; moves to [[#Yellow — In progress|Yellow]].

---

### Yellow — In progress
**Responsible:** [[Reclutadora]]

The recruiter searches for and assigns associates to the positions (see [[Semáforo de Posiciones de la Requisición]] and [[Semáforo del Colaborador]]).

### Decision

**Are all positions covered?**

- **YES →** [[#Light Blue — Fully covered|Light Blue]]
- **NO →** [[#Red — Partially covered|Red]]

---

### Light Blue — Fully covered
**Responsible:** [[Reclutadora]]

All positions reached 100% (see `Green` in [[Semáforo de Posiciones de la Requisición]]).

**End of active cycle** — the requisition is closed satisfactorily.

---

### Red — Partially covered
**Responsible:** [[Reclutadora]]

The requisition closed with at least one position in `Yellow` or `Red` at the [[Semáforo de Posiciones de la Requisición|position]] level.

**End of active cycle** — with incomplete coverage.

---

### Purple — Deleted

Cross-cutting state: reached from any previous state when the requisition is physically deleted. The system logs a journal entry.

## Related

- [[Requisición]]
- [[Semáforo de Urgencia de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
- [[Semáforo del Colaborador]]
- [[Flujo de Reclutamiento]]
- [[Reclutadora]]
- [[Manager de Reclutamiento]]
- [[Hotel/Manager General|Manager General]]
- [[Hotel/Manager de Área|Manager de Área]]
- [[Hotel/Supervisor|Supervisor]]
