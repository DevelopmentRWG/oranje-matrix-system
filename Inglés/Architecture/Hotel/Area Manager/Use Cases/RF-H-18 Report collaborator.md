---
tags:
  - arquitectura
  - rol/manager-de-area
  - caso-de-uso
aliases:
  - UC RF-H-18
---

# 🪪 ID: RF-H-18
🏷️ **Name:** Report collaborator (Red)

**Story:**
When a collaborator commits a serious offense (misconduct, theft, conflict, justified absence), the Area Manager **reports** them from the My Staff module. This action is **exclusive to the Area Manager** (rule RR-H-10 — the Supervisor CANNOT report). The collaborator moves to the **Red** status in the Collaborator Status Light and the zone Inspector's investigation is automatically started.

**Acceptance criteria:**
Only the Area Manager can report (RR-H-10). The reason is mandatory (catalog: Serious offense / Misconduct / Theft / Conflict / Other). The description must have at least 50 characters to start the investigation. Optional evidence (PDF/JPG/PNG, max. 10 MB). The collaborator must be assigned to the Manager's dept. It notifies the zone Inspector in less than 1 min. It is recorded in an auditable log.

**Documentation:**
- PRD: PRD-HOTEL-03 Area Manager
- Flow: Collaborator report (Red)
- Prototype: (Figma link)

**Flow:**
`Sidebar → My Staff → Collaborator detail` → MANUAL → `Click "Report"` → `Selects reason (catalog)` → `Writes detailed description (min. 50 characters)` → `Attaches optional evidence` → `Adds optional witnesses` → `Confirm` → AUTOMATICO → If validations OK → `Collaborator status to Red + Notifies the zone Inspector + Starts investigation + Records in auditable log + Notifies the dept Supervisor` / If description <50 characters → `Blocks with message`
