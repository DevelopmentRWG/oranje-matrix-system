---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - UC RF-15
---

# 🪪 ID: RF-15
🏷️ **Name:** Assign collaborator to hotel

**Story:**
The Recruiter finds a collaborator in the Pool that meets the requirements of a requisition position. They assign them to the hotel and the requisition updates its coverage percentage. The assignment locks the collaborator for other hotels (exclusivity rule RR-05).

**Acceptance criteria:**
When assigning, the requisition updates its coverage % in real time. The collaborator is locked for other hotels. An automatic entry is generated in the hotel's Schedule.

**Documentation:**
- PRD: PRD-RECL-02 Recruiter
- Flow: Assign collaborator
- Prototype: (Figma link)

**Flow:**
`Requisition Detail` → MANUAL → `Click "Assign collaborator"` → `Pool filtered by position/zone` → `Select candidate` → AUTOMATIC → `Checks Blacklist (RF-11)` → `Checks exclusivity (RR-05)` → `Assigns + Updates coverage + Generates Schedule (RF-16)`
