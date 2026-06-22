---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - UC RF-16
---

# 🪪 ID: RF-16
🏷️ **Name:** Assign to Schedule

**Story:**
When assigning a collaborator to a position, the system automatically generates the corresponding entry in the hotel's weekly Schedule. The collaborator appears both in the hotel's Schedule and in their own personal Schedule.

**Acceptance criteria:**
The Schedule entry is generated in under 10s after the assignment. It appears in both the hotel's and the collaborator's Schedule. It reflects the correct shift, position and modality.

**Documentation:**
- PRD: PRD-RECL-02 Recruiter
- Flow: Automatic Schedule
- Prototype: (Figma link)

**Flow:**
`Collaborator assignment (RF-15)` → AUTOMATIC → `System generates entry in the hotel's Schedule` → `Reflects in the collaborator's personal Schedule` → `Notifies the Area Manager`
