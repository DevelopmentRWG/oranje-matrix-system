---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-39
---

# 🪪 ID: RF-39
🏷️ **Name:** Take / Join an already taken requisition (collaborative)

**Story:**
The Leader views the Authorized inbox and opens a requisition that other recruiters are already working on (label "Shared · N recruiters"). Instead of being blocked, the system offers him to **Join** as an additional participating recruiter. On confirmation, the requisition appears in "My Requisitions" and the Leader starts working it alongside the rest, with the coverage progress **shared** (collaborative model, RR-15). If no one is working the requisition yet, the action is **Take** and the status light changes to Yellow (In progress).

**Acceptance criteria:**
An already taken requisition can be taken by another recruiter, who **is added without displacing the existing ones or rolling back the status light** (AC-21). The card lists **all active recruiters** (AC-22). Taking/joining does NOT transfer or block the requisition: no one loses the requisition. Coverage progress is shared; the concurrency lock is at the **position/slot** level, not the whole requisition: if two assign the same position, the first one wins and the second sees "position already covered" (AC-23). You cannot join an already closed requisition (covered or partial). Each join is recorded in the **History** with actor and timestamp (RR-16).

> [!note]
> The people working a requisition are called **participating recruiters** (not "collaborators"). "Collaborator" is reserved for the Pool worker assigned to a position.

**Documentation:**
- PRD: PRD-RECL-03 Group Leader
- Flow: Join collaborative requisition
- Prototype: (Figma link)

**Flow:**
`Authorized inbox` → MANUAL → `Open requisition "Shared · N recruiters"` → `Click "Join"` (or "Take" if no one is working it) → `Confirm` → AUTOMATICO → `Adds the Leader as a participating recruiter + Appears in My Requisitions + Keeps Yellow status light and what is already assigned + Records in the History who joined (author + date)`
