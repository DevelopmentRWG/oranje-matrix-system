---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-41
---

# 🪪 ID: RF-41
🏷️ **Name:** View requisition History (timeline)

**Story:**
Since a requisition can have several participating recruiters working it at once (collaborative model, RR-15), the Leader needs to see **who did what and when**. He opens the requisition detail and enters the **History** section: an **immutable** chronological timeline that shows each event with its **actor** (role + name) and timestamp. It serves to audit and follow up without depending on a single owner.

**Acceptance criteria:**
The History shows chronologically who **took / joined**, who **left**, who **assigned/unassigned** each collaborator to which position, and who **closed** it, each event with **date and author** (AC-24, RR-16). The timeline is **immutable**: events are not edited or deleted. It is visible to all participating recruiters, the Group Leader and the [[Recruitment Manager|Recruitment Manager]]. The order is strictly chronological.

> [!note]
> In the History, "collaborator" refers to the Pool worker assigned to a position; the people working the requisition are the **participating recruiters**.

**Documentation:**
- PRD: PRD-RECL-03 Group Leader
- Flow: Requisition history / traceability
- Prototype: (Figma link)

**Flow:**
`My Requisitions → Requisition detail` → MANUAL → `Click "View history"` → AUTOMATICO → `Opens the immutable chronological timeline with each event (took/joined, left, assigned/unassigned collaborator↔position, closed) + actor (role + name) + timestamp`
