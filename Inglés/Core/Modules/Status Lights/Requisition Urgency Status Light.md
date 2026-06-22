---
tags:
  - modulo/core
aliases:
  - Requisition Urgency Status Light
  - Urgency Status Light
  - Urgency Status Red
  - Urgency Status Yellow
  - Urgency Status Strong Green
---

# Requisition Urgency Status Light

Visual classification of the urgency level with which a [[Requisition|Requisition]] needs to be covered, based on the time available before the start date.

> [!info]
> This is one of the requisition's status lights. See also: [[Requisition Status Light|Requisition Status Light]], [[Requisition Positions Status Light|Requisition Positions Status Light]] and the [[Collaborator Status Light|Collaborator Status Light]].

## States

| Color        | Level   | Time         |
| ------------ | ------- | ------------ |
| Red          | Urgent  | < 72 hrs     |
| Yellow       | Medium  | 72 – 120 hrs |
| Strong Green | Normal  | > 120 hrs    |

## Key rules

- **Automatic calculation by the system** when authorizing the requisition ([[Requisition Status Light#Green — Authorized|Green]]).
- **Parameters:** `requisition authorization date` vs `position start date`.
- **Formula:**
	- `> 120 hrs` → **Strong Green** (Normal)
	- `72 – 120 hrs` → **Yellow** (Medium)
	- `< 72 hrs` → **Red** (Urgent)
- **No human intervention**: the system reevaluates automatically and adjusts the color as time passes.

## Related

- [[Requisition|Requisition]]
- [[Requisition Status Light|Requisition Status Light]]
- [[Requisition Positions Status Light|Requisition Positions Status Light]]
- [[Recruiter|Recruiter]]
