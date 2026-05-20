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

Visual status system that represents the lifecycle of a [[Requisition]], from when the [[Hotel/General Manager|General Manager]], the [[Hotel/Area Manager|Area Manager]] or the [[Hotel/Supervisor|Supervisor]] begin drafting it until it is fully covered.

> [!info]
> This Status Indicator describes the **general lifecycle** of the requisition. The other dimensions are managed in separate Status Indicators: [[Requisition Urgency Indicator]] (classification by time) and [[Requisition Position Indicator]] (coverage percentage per position). For the associate's state see [[Associate Status Indicator]].

> [!note] Parallelism with [[Requisition Position Indicator]]
> Each requisition state has its mirror at the position level: `Apple Green`↔`Gold` · `Green`↔`Orange` · `Light Blue`↔`Green` · `Red`↔`Yellow/Red` · `Purple`↔`Purple`.

## States

| Color       | State               | Responsible                                                                 | Description                                  |
| ----------- | ------------------- | --------------------------------------------------------------------------- | -------------------------------------------- |
| Apple Green | In preparation      | [[Hotel/General Manager\|GM]], [[Hotel/Area Manager\|GH]] or [[Hotel/Supervisor\|SUP]] | Being drafted by the hotel.           |
| Green       | Authorized          | [[Hotel/General Manager\|GM]] or [[Hotel/Area Manager\|GH]]                            | Authorized by the hotel.              |
| Yellow      | In progress         | [[Recruiter]] (taken from the shared tray)                                | In the process of staff assignment.          |
| Light Blue  | Fully covered       | [[Recruiter]]                                                             | Requisition fully covered.                   |
| Red         | Partially covered   | [[Recruiter]]                                                             | Requisition partially covered.               |
| Purple      | Deleted             | —                                                                           | Requisition physically deleted.              |

## Detail by state

### Apple Green — In preparation
**Responsible:** [[Hotel/General Manager|GM]], [[Hotel/Area Manager|GH]] or [[Hotel/Supervisor|SUP]]

The hotel begins creating the requisition and its positions.

**Advance →** when the [[Hotel/General Manager|GM]] or the [[Hotel/Area Manager|GH]] authorizes the requisition, it moves to [[#Green — Authorized|Green]]. Only the GM or GH can authorize; if the SUP attempts it, the system blocks the action.

---

### Green — Authorized
**Responsible:** [[Hotel/General Manager|GM]] or [[Hotel/Area Manager|GH]]

The requisition is ready for assignment. The system automatically calculates urgency (see [[Requisition Urgency Indicator]]).

**Advance →** a [[Recruiter]] or [[Recruitment/Recruiter Team Lead|Recruiter Team Lead]] takes the requisition from the shared tray; moves to [[#Yellow — In progress|Yellow]].

---

### Yellow — In progress
**Responsible:** [[Recruiter]]

The recruiter searches for and assigns associates to the positions (see [[Requisition Position Indicator]] and [[Associate Status Indicator]]).

### Decision

**Are all positions covered?**

- **YES →** [[#Light Blue — Fully covered|Light Blue]]
- **NO →** [[#Red — Partially covered|Red]]

---

### Light Blue — Fully covered
**Responsible:** [[Recruiter]]

All positions reached 100% (see `Green` in [[Requisition Position Indicator]]).

**End of active cycle** — the requisition is closed satisfactorily.

---

### Red — Partially covered
**Responsible:** [[Recruiter]]

The requisition closed with at least one position in `Yellow` or `Red` at the [[Requisition Position Indicator|position]] level.

**End of active cycle** — with incomplete coverage.

---

### Purple — Deleted

Cross-cutting state: reached from any previous state when the requisition is physically deleted. The system logs a journal entry.

## Related

- [[Requisition]]
- [[Requisition Urgency Indicator]]
- [[Requisition Position Indicator]]
- [[Associate Status Indicator]]
- [[Recruitment Flow]]
- [[Recruiter]]
- [[Recruitment Manager]]
- [[Hotel/General Manager|General Manager]]
- [[Hotel/Area Manager|Area Manager]]
- [[Hotel/Supervisor|Supervisor]]
