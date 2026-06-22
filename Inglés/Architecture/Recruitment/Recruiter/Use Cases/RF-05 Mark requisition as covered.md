---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - UC RF-05
---

# 🪪 ID: RF-05
🏷️ **Name:** Mark requisition as covered

**Story:**
The Recruiter finishes assigning all collaborators required by the requisition. When all positions are at 100%, they mark the requisition as "Covered". **The Group Leader receives the request to validate the closure.**

**Acceptance criteria:**
Marking as Covered is only allowed if all positions are at 100% (rule RR-04). When marking, the **Group Leader** is notified for closure validation.

**Documentation:**
- PRD: PRD-RECL-02 Recruiter
- Flow: Close requisition
- Prototype: (Figma link)

**Flow:**
`My Requisitions (100% covered)` → MANUAL → `Click on "Mark covered"` → AUTOMATIC → `Requests validation from the Group Leader` → MANUAL Leader → `Approves closure` → AUTOMATIC → `Light Blue Status Light + Notifies the hotel`
