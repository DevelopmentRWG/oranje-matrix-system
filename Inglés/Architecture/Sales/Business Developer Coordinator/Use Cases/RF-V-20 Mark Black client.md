---
tags:
  - arquitectura
  - rol/bdc
  - caso-de-uso
aliases:
  - CU RF-V-20
---

# 🪪 ID: RF-V-20
🏷️ **Name:** Mark client Black

**Story:**
When an active client (Orange status) stops operating — due to hotel closure, change of administration, pause, or dispute — the BDC marks them as **Black**. This action is **exclusive to the BDC** (RR-V-05). The client becomes paused / inactive and leaves the active clients view. It can later be reactivated (RF-V-21), returning to Light Blue status as a prospect.

**Acceptance criteria:**
Only the BDC can mark Black (RR-V-05). Mandatory reason (catalog: Hotel closure / Change of administration / Pause / Dispute / Other). Mandatory comment (min. 30 characters). Optional pause date. Notifies the assigned BD. Recorded in an auditable log. The hotel leaves the active clients view and moves to the "Black" sub-view of the Active Clients module.

**Documentation:**
- PRD: PRD-VENTAS-03 BDC
- Flow: Mark client Black
- Prototype: (Figma link)

**Flow:**
`Active client detail (Orange)` → MANUAL → `Click "Mark Black"` → `Selects reason (catalog)` → `Mandatory comment (min. 30 characters)` → `Optional pause date` → `Confirm` → AUTOMATICO → `Status changes to Black + Client leaves active view + Appears in Black sub-view + Notifies the assigned BD + Auditable log`

**Reactivation (RF-V-21):**
`Black sub-view → Click on client → Click "Reactivate"` → `Optional justification` → `Confirm` → AUTOMATICO → `Status returns to Light Blue as a prospect (RR-V-07) + Notifies the original BD + Timeline keeps the Black history`
