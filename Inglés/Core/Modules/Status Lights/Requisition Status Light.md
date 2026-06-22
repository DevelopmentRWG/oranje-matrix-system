---
tags:
  - modulo/core
aliases:
  - Requisition Status Light
  - Requisition Status Apple Green
  - Requisition Status Green
  - Requisition Status Yellow
  - Requisition Status Light Blue
  - Requisition Status Red
  - Requisition Status Purple
---

# Requisition Status Light

System of visual states that represents the life cycle of a [[Requisition|Requisition]], from when the [[Hotel/General Manager|General Manager]], the [[Hotel/Area Manager|Area Manager]] or the [[Hotel/Supervisor|Supervisor]] start drafting it until it is covered.

> [!info]
> This status light describes the **general life cycle** of the requisition. The other dimensions are handled in separate status lights: [[Requisition Urgency Status Light|Requisition Urgency Status Light]] (classification by time) and [[Requisition Positions Status Light|Requisition Positions Status Light]] (coverage percentage by position). For the collaborator's state see [[Collaborator Status Light|Collaborator Status Light]].

> [!note] Parallelism with [[Requisition Positions Status Light|Requisition Positions Status Light]]
> Each requisition state mirrors a position-level state: `Apple Green`↔`Gold` · `Green`↔`Orange` · `Light Blue`↔`Green` · `Red`↔`Yellow/Red` · `Purple`↔`Purple`.

## States

| Color       | State                | Responsible                                                 | Description                            |
| ----------- | -------------------- | ----------------------------------------------------------- | -------------------------------------- |
| Apple Green | In drafting          | [[Hotel/General Manager\|GM]], [[Hotel/Area Manager\|GH]] or [[Hotel/Supervisor\|SUP]] | In drafting by the hotel.          |
| Green       | Authorized           | [[Hotel/General Manager\|GM]] or [[Hotel/Area Manager\|GH]]                             | Authorized by the hotel.  |
| Yellow      | In process           | Active recruiters (several)                                 | In process of staff assignment.        |
| Light Blue  | Fully covered        | Active recruiters (several)                                 | Requisition fully covered.             |
| Red         | Partially covered    | Active recruiters (several)                                 | Requisition partially covered.         |
| Purple      | Removed              | —                                                           | Requisition physically removed.        |

## Detail by state

### Apple Green — In drafting
**Responsible:** [[Hotel/General Manager|GM]], [[Hotel/Area Manager|GH]] or [[Hotel/Supervisor|SUP]]

The hotel starts the creation of the requisition and its positions.

**Advance →** when the [[Hotel/General Manager|GM]] or the [[Hotel/Area Manager|GH]] authorizes the requisition, it moves to [[#Green — Authorized|Green]]. Only the GM or GH can authorize; if the SUP attempts it, the system blocks the action.

---

### Green — Authorized
**Responsible:** [[Hotel/General Manager|GM]] or [[Hotel/Area Manager|GH]]

The requisition is ready for assignment. The system automatically calculates the urgency (see [[Requisition Urgency Status Light|Requisition Urgency Status Light]]).

**Advance →** a [[Recruiter|Recruiter]] or [[Recruitment/Recruiters Group Leader|Group Leader]] takes the requisition from the shared inbox; it moves to [[#Yellow — In process|Yellow]]. The status change records the **actor** in the [[Core/Modules/Requisition/Requisition#Historial de la Requisición|Requisition History]].

> [!note] Return from Yellow
> Under the collaborative model (RR-15), the requisition only returns to **Green** (Authorized) when **the last** participating recruiter leaves. As long as at least one recruiter remains active, it stays in Yellow.

---

### Yellow — In process
**Responsible:** Active recruiters (several)

**Several participating recruiters** can work the requisition at the same time (collaborative model, RR-15); there is no single owner. The progress shown by the status light **consolidates the work of all** active recruiters. Each one searches for and assigns collaborators to the positions (see [[Requisition Positions Status Light|Requisition Positions Status Light]] and [[Collaborator Status Light|Collaborator Status Light]]). Each status change records the **actor** in the [[Core/Modules/Requisition/Requisition#Historial de la Requisición|Requisition History]].

### Decision

**Are all positions covered?**

- **YES →** [[#Light Blue — Fully covered|Light Blue]]
- **NO →** [[#Red — Partially covered|Red]]

---

### Light Blue — Fully covered
**Responsible:** Active recruiters (several)

All positions reached 100% (see `Green` in [[Requisition Positions Status Light|Requisition Positions Status Light]]); the result consolidates the work of all participating recruiters. The closure records the **actor** (who closed it) in the [[Core/Modules/Requisition/Requisition#Historial de la Requisición|Requisition History]].

**End of active cycle** — the requisition is closed successfully.

---

### Red — Partially covered
**Responsible:** Active recruiters (several)

The requisition closed with at least one position in `Yellow` or `Red` at the [[Requisition Positions Status Light|position]] level; the result consolidates the work of all participating recruiters. The closure records the **actor** (who closed it) in the [[Core/Modules/Requisition/Requisition#Historial de la Requisición|Requisition History]].

**End of active cycle** — with incomplete coverage.

---

### Purple — Removed

Cross-cutting state: it is reached from any previous state when the requisition is physically removed. The system records a journal entry.

## Related

- [[Requisition|Requisition]]
- [[Requisition Urgency Status Light|Requisition Urgency Status Light]]
- [[Requisition Positions Status Light|Requisition Positions Status Light]]
- [[Collaborator Status Light|Collaborator Status Light]]
- [[Recruitment Flow|Recruitment Flow]]
- [[Recruitment/Requisition Self-Pick|Requisition Self-Pick]]
- [[Recruiter|Recruiter]]
- [[Recruitment/Recruiters Group Leader|Recruiters Group Leader]]
- [[Recruitment Manager|Recruitment Manager]]
- [[Hotel/General Manager|General Manager]]
- [[Hotel/Area Manager|Area Manager]]
- [[Hotel/Supervisor|Supervisor]]
