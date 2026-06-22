---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - UC RF-17
---

# 🪪 ID: RF-17
🏷️ **Name:** Request collaborator reassignment

**Story:**
When a collaborator needs to be rotated from one hotel to another (by request of the hotel, of the collaborator or by operational decision), the Recruiter requests the reassignment. The history remains visible and, if it is a sensitive case (VIP hotel), it is escalated to the Manager for approval.

**Acceptance criteria:**
The reassignment is recorded in the history. If the case is sensitive, the system notifies the Manager for approval. The Schedule of both hotels is updated automatically.

**Documentation:**
- PRD: PRD-RECL-02 Recruiter
- Flow: Reassignment
- Prototype: (Figma link)

**Flow:**
`Active assignment` → MANUAL → `Click "Reassign"` → `Select new hotel` → `Confirm` → AUTOMATIC → If sensitive → `Notifies the Manager` → MANUAL Manager → `Approves` → AUTOMATIC → `Updates Schedule in both hotels + Records history`
