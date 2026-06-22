---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - UC RF-18
---

# 🪪 ID: RF-18
🏷️ **Name:** Request collaborator unassignment

**Story:**
When a collaborator ends their assignment (end of contract, operational issue, hotel request), the Recruiter unassigns them from the hotel. The position is freed in the requisition and the collaborator returns to Strong Green (Available) in the Pool.

**Acceptance criteria:**
The unassignment frees the position; it notifies the hotel. The collaborator returns to Available (Strong Green) in the Pool. If it was a requisition covered at 100%, the coverage drops.

**Documentation:**
- PRD: PRD-RECL-02 Recruiter
- Flow: Unassignment
- Prototype: (Figma link)

**Flow:**
`Active assignment` → MANUAL → `Click "Unassign"` → `Select reason` → `Confirm` → AUTOMATIC → `Frees position in requisition + Notifies the hotel + Collaborator returns to Strong Green + Updates Schedule`
