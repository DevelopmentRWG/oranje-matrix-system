---
tags:
  - arquitectura
  - rol/manager-reclutamiento
aliases:
  - Incident States Manager
  - Incident Lifecycle
  - Incident States Catalog
---

# 13. INCIDENT STATES — RECRUITMENT MANAGER

Catalog of the incident case lifecycle from the moment it is escalated to the Manager until its closure.

> [!note]
> The states below are **inferred** from the flow of [[Use Cases/RF-30 Resolve incident|RF-30]] and [[Use Cases/RF-31 Escalate to sales|RF-31]]. The only state explicitly named in the RFs is **"Escalated to sales"**; the remaining names come from the mockup and are **subject to validation**. Colors are those used in the mockup (kanban board).

---

## States

| State | Color (mockup) | Description | How it is entered |
| ------------------------- | ------------------- | -------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| **Open** | `#E11919` (red) | Newly escalated, not yet investigated. Initial state upon receipt. | A Leader, Inspector, or the System escalates the case (RF-30, [[11 - System Responses]]). |
| **Under investigation** | `#3B7DDD` (blue) | The Manager reviews evidence, comments, history, and involved parties. | On clicking "Investigate" (RF-30). |
| **Awaiting info** | `#E6B422` (yellow) | The Manager requested more information; the case remains open pending a reply. | Decision "Request more information" (RF-30). |
| **Escalated to sales** | `#7B2CBF` (purple) | Notified to the hotel's BD/BDC; the case moves to the sales area. | Decision "Escalate to sales" ([[Use Cases/RF-31 Escalate to sales|RF-31]]). |
| **Escalated to Management** | `#FF7A00` (orange) | Full case sent to the Director. | Action "Escalate to Management" ([[08 - User Actions]], [[11 - System Responses]]). |
| **Resolved (closed)** | — (leaves the tray) | Case closed with a final decision and mandatory comment. | Decision "Resolve" (RF-30). |

---

## Transition rules

- **Open → Under investigation**: the Manager clicks "Investigate" (RF-30).
- **Under investigation → Resolved**: decision "Resolve" with mandatory comment (RF-30).
- **Under investigation → Escalated to sales**: decision "Escalate to sales", triggers RF-31.
- **Under investigation → Awaiting info**: decision "Request more information" (RF-30).
- **Under investigation → Escalated to Management**: action "Escalate to Management" (docs 08/11).
- **Awaiting info → Under investigation**: upon receipt of the requested information.
- **Escalated to sales → Resolved**: the sales area closes the case.
- **Escalated to sales → Escalated to Management**: the Manager additionally elevates it to Management.
- **Escalated to Management → Resolved**: Management issues the final resolution.
- **Every closure** notifies the involved parties (Leader, Recruiter, Inspector, hotel if applicable) and is recorded in the auditable log (RF-30).

---

## Related

- [[Use Cases/RF-30 Resolve incident|RF-30 — Resolve incident]]
- [[Use Cases/RF-31 Escalate to sales|RF-31 — Escalate to sales]]
- [[08 - User Actions]]
- [[09 - Form Fields]]
- [[11 - System Responses]]
- [[14 - Incident SLA]]
- [[12 - Mockup and UI Decisions]]
