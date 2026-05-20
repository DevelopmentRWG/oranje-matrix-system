---
tags:
  - module/core
aliases:
  - Requisition Urgency Status Indicator
  - Requisition Urgency Indicator
  - Urgency Status Red
  - Urgency Status Yellow
  - Urgency Status Dark Green
---

# Requisition Urgency Status Indicator

Visual classification of the urgency level with which a [[Requisition]] needs to be covered, based on the time available before the start date.

> [!info]
> This is one of the requisition Status Indicators. See also: [[Requisition Status Indicator]], [[Requisition Position Indicator]] and [[Associate Status Indicator]].

## States

| Color      | Level  | Time         |
| ---------- | ------ | ------------ |
| Red        | Urgent | < 72 hrs     |
| Yellow     | Medium | 72 – 120 hrs |
| Dark Green | Normal | > 120 hrs    |

## Business Rules

- **Automatic calculation by system** when the requisition is authorized ([[Requisition Status Indicator#Verde — Autorizada|Green]]).
- **Parameters:** `requisition authorization date` vs `position start date`.
- **Formula:**
	- `> 120 hrs` → **Dark Green** (Normal)
	- `72 – 120 hrs` → **Yellow** (Medium)
	- `< 72 hrs` → **Red** (Urgent)
- **No human intervention**: the system automatically re-evaluates and adjusts the color as time advances.

## Related

- [[Requisition]]
- [[Requisition Status Indicator]]
- [[Requisition Position Indicator]]
- [[Recruiter]]
