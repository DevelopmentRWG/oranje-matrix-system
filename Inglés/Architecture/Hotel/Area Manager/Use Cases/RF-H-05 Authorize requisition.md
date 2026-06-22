---
tags:
  - arquitectura
  - rol/manager-de-area
  - caso-de-uso
aliases:
  - UC RF-H-05
---

# 🪪 ID: RF-H-05
🏷️ **Name:** Authorize requisition

**Story:**
The Supervisor creates a requisition and sends it to the Area Manager for authorization. The Manager reviews that the requisition is complete, justified and correct. Upon authorizing it, the requisition is automatically sent to the Recruitment inbox (Self-Pick model), where Recruiters and Group Leaders can take it freely. The authorization is the **security layer** of the system (rule RR-H-02): it guarantees that Oranje only receives requisitions validated by the hotel.

**Acceptance criteria:**
Only the Area Manager can authorize (RR-H-02). The requisition must have at least 1 registered position (RR-H-03). Upon authorizing, the system automatically calculates the urgency per position (>120h Strong Green, 72-120h Yellow, <72h Red), assigns the Inspector by zone, reflects the positions in the weekly Schedule and sends the requisition to the Recruitment inbox — all in less than 30s. It notifies the Supervisor of the status change.

**Documentation:**
- PRD: PRD-HOTEL-03 Area Manager
- Flow: Requisition authorization
- Prototype: (Figma link)

**Flow:**
`Sidebar → Requisitions → "Pending authorization" inbox` → MANUAL → `Click on requisition` → `Reviews header + positions + notes + Supervisor who created it` → MANUAL → `Click "Authorize"` → AUTOMATICO → `Validates it has ≥1 position` → If OK → `Changes status to Authorized + Calculates urgency (RF-H-08) + Assigns Inspector by zone (RF-H-09) + Reflects in Schedule (RF-H-10) + Sends to Recruitment inbox (RI-H-01) + Notifies the Supervisor` / If it has no positions → `Blocks with message "It has no registered positions..."`
