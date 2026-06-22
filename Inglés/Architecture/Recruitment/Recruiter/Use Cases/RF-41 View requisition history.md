---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - UC RF-41
---

# 🪪 ID: RF-41
🏷️ **Name:** View the requisition's History

**Story:**
The Recruiter opens the detail of a requisition and consults its **History**: an **immutable** chronological timeline that records each event with its **actor** (role + name) and timestamp. The History shows who took it / joined, who left, who assigned/unassigned which collaborator to which position and who closed it. In the collaborative model (RR-15) several participating recruiters work the same requisition at once, so the History is the shared traceability source (RR-16). It is visible to all participating recruiters, the [[Recruitment/Recruiters Group Leader|Group Leader]] and the [[Hotel/Area Manager|Area Manager]].

**Acceptance criteria:**
The History shows chronologically who took/left and who assigned/unassigned each collaborator, with date and author (AC-24). The timeline is immutable (it cannot be edited or deleted). It is visible to all participating recruiters, the Group Leader and the Area Manager.

**Documentation:**
- PRD: PRD-RECL-02 Recruiter
- Flow: View the requisition's history
- Prototype: (Figma link)

**Flow:**
`Requisition Detail` → MANUAL → `Click on "View history"` → AUTOMATIC → `Loads the immutable chronological timeline (RR-16)` → `Lists each event with actor (role + name) and timestamp: took / joined / left / assigned / unassigned (collaborator → position) / closed`
