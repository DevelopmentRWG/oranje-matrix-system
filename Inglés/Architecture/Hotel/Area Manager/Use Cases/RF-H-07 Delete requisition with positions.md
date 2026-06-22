---
tags:
  - arquitectura
  - rol/manager-de-area
  - caso-de-uso
aliases:
  - UC RF-H-07
---

# 🪪 ID: RF-H-07
🏷️ **Name:** Delete requisition with positions

**Story:**
When a requisition already has registered positions but must be cancelled (change of plans by the hotel, serious error detected after authorization, decision not to cover it), the Area Manager deletes it manually. Unlike the automatic physical deletion (without journal) of empty requisitions, this one requires justification and leaves an individual journal for each position.

**Acceptance criteria:**
Only the Area Manager can delete requisitions with positions. Justification is mandatory. Each position moves to the **Purple** status (cross-cutting — RR-H-08) with an individual journal. The requisition also moves to Purple. Confirmation message: *"Upon confirming the deletion of the requisition, the registered positions and the requisition will be physically deleted"*. It notifies the Supervisor.

**Documentation:**
- PRD: PRD-HOTEL-03 Area Manager
- Flow: Deletion of requisition with positions
- Prototype: (Figma link)

**Flow:**
`Sidebar → Requisitions → Requisition detail` → MANUAL → `Click "Delete requisition"` → `Mandatory justification (min. 20 characters)` → `Checks confirmation checkbox` → `Confirm` → AUTOMATICO → `Status of each position to Purple + Individual journal per position + Requisition status to Purple + Notifies the Supervisor + Records in auditable log`
