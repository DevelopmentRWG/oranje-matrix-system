---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - UC RF-04
---

# 🪪 ID: RF-04
🏷️ **Name:** Take requisition in process (Collaborative Self-Pick)

**Story:**
The Recruiter sees the Authorized inbox with all available requisitions. They select one they can cover and "take" it freely (Collaborative Self-Pick, RR-15). The requisition appears in My Requisitions and the status light automatically changes to Yellow (In process). Taking it **does not lock it**: other Recruiters can join as additional participating recruiters.

**Acceptance criteria:**
When taking the requisition, it appears in "My Requisitions" in under 2s and the status light automatically changes to Yellow. Other Recruiters can join the same requisition (it does not get locked). The event is recorded in the requisition's History with author and date.

**Documentation:**
- PRD: PRD-RECL-02 Recruiter
- Flow: Take requisition
- Prototype: (Figma link)

**Flow:**
`Authorized inbox` → MANUAL → `Click on "Take"` → `Confirm selection` → AUTOMATIC → `Adds me as participating recruiter + Moves to My Requisitions + Yellow Status Light + Records in History (RR-16)`
