---
tags:
  - arquitectura
  - rol/manager-reclutamiento
aliases:
  - Incident SLA Manager
  - Incident Timelines
  - Incident SLA Rules
---

# 14. INCIDENT SLA — RECRUITMENT MANAGER

> [!warning] PROPOSAL — pending business validation
> The figures in this document are **not defined in the vault**; they are a starting point for Management and the Manager to confirm or discard. What is already documented today is explicitly indicated in the corresponding section.

---

## What IS documented today

The following timeframes come directly from the formalized use cases:

- The incident reaches the Manager in **< 1 min** after escalation — [[Use Cases/RF-30 Resolve incident|RF-30]].
- Notification to the BD/BDC is sent in **< 1 min** upon escalating to sales — [[Use Cases/RF-31 Escalate to sales|RF-31]].
- The system issues an automatic alert for an urgent requisition left untaken "after N configured hours" ([[11 - System Responses]]) — **N has no defined value**.

---

## Not defined (open decisions)

The following points have no documented value or rule in the vault and require a business decision:

- Maximum resolution time for an incident.
- Maximum time allowed in the "Under investigation" state before action is required.
- Whether automatic escalation by timeout exists (the system changes state if no one acts within X hours).
- The exact definition of "SLA at risk" (what condition triggers it and how it is notified).

---

## Proposed SLA by priority

> [!warning] The figures in the table below are a proposal subject to validation; they do not represent approved rules.

| Priority | Respond (move to Under investigation) | Resolve |
| -------- | ------------------------------------- | ------- |
| Critical | < 4 h | < 24 h |
| High | < 8 h | < 48 h |
| Medium | < 24 h | < 5 days |
| Low | < 48 h | < 10 days |

**Proposed definition of "SLA at risk":** a case that has exceeded its target response time without having moved to "Under investigation", or that has exceeded its target resolution time without having been closed.

> [!note]
> The "Priority" field is also a mockup resource pending confirmation as an official data field — see [[09 - Form Fields]] (Incident case section) and [[13 - Incident States]].

---

## Questions to resolve

- [ ] Do incidents have a formal SLA with defined time limits, or are they handled by priority without time constraints?
- [ ] Is there automatic escalation by timeout? (the system moves the state if the Manager does not act within X hours)
- [ ] What is the value of N for the untaken urgent requisition alert? (see [[11 - System Responses]])
- [ ] Who defines and adjusts the N values? The Manager, Management, or system configuration?

---

## Related

- [[13 - Incident States]]
- [[Use Cases/RF-30 Resolve incident|RF-30 — Resolve incident]]
- [[Use Cases/RF-31 Escalate to sales|RF-31 — Escalate to sales]]
- [[09 - Form Fields]]
- [[11 - System Responses]]
- [[12 - Mockup and UI Decisions]]
