---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - UC RF-39
---

# 🪪 ID: RF-39
🏷️ **Name:** Take / Join an already-taken requisition (collaborative)

**Story:**
The Recruiter sees in the Authorized inbox a requisition that already has other recruiters working it, marked with the label "Shared · N recruiters". Instead of locking it or transferring it, the action is **Join**: they are added as an additional participating recruiter without displacing the existing ones or rolling back the status light (Collaborative Self-Pick, RR-15). Coverage progress is shared among all participating recruiters; each one can search the Pool and assign collaborators to positions, with a lock at the position/slot level (two recruiters do not assign the same collaborator to the same position). If they try to join a requisition they already participate in, the system blocks it; if the requisition is already closed, joining is not allowed either.

**Acceptance criteria:**
An already-taken requisition can be taken by another recruiter who is added without displacing the existing ones or rolling back the status light (AC-21). After joining, the requisition appears in "My Requisitions" with the label "Shared · N recruiters" and the system notifies the other participants. The event is recorded in the requisition's History with author (role + name) and date (RR-16). Joining when already participating is blocked; joining a closed requisition is blocked.

**Documentation:**
- PRD: PRD-RECL-02 Recruiter
- Flow: Join requisition (collaborative)
- Prototype: (Figma link)

**Flow:**
`Authorized inbox (Shared · N recruiters)` → MANUAL → `Click on "Join"` → `Confirm` → AUTOMATIC → `Validates that I am not already participating and that it is not closed` → `Adds me as an additional participating recruiter (does not displace anyone, does not roll back status light)` → `Appears in My Requisitions (Shared) + Notifies the other participants + Records in History with author (RR-16)`
