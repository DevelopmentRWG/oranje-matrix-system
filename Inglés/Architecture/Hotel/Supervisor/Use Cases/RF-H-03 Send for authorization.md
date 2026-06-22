---
tags:
  - arquitectura
  - rol/supervisor-hotel
  - caso-de-uso
aliases:
  - CU RF-H-03
---

# 🪪 ID: RF-H-03
🏷️ **Name:** Send requisition for authorization

**Story:**
When the Supervisor finishes building the requisition (or correcting a rejected one), they send it to the Area Manager for authorization. The system validates that it has at least 1 position and, if valid, moves it to Apple Green — pending authorization status and notifies the Area Manager. The requisition becomes visible in the Manager's "Pending authorization" inbox.

**Acceptance criteria:**
The requisition must have at least 1 registered position (RR-H-03). If it does not, the system blocks with: *"It has no registered positions, register at least one position and try again"*. If it is OK, the status moves to Apple Green pending and notifies the Area Manager in under 1 min. The requisition is NO longer editable by the Supervisor until the Manager rejects or authorizes it.

**Documentation:**
- PRD: PRD-HOTEL-02 Supervisor
- Flow: Send for authorization
- Prototype: (Figma link)

**Flow:**
`Sidebar → Requisitions → Requisition detail (draft or rejected)` → MANUAL → `Click "Send for authorization"` → AUTOMATICO → `Validates that it has ≥1 position` → If OK → `Status moves to Apple Green — pending authorization + Notifies the Area Manager + Appears in their "Pending authorization" inbox + Blocks the Supervisor's editing` / If no positions → `Blocks with message "It has no registered positions..."`
