---
tags:
  - arquitectura
  - rol/business-developer
  - caso-de-uso
aliases:
  - CU RF-V-15
---

# 🪪 ID: RF-V-15
🏷️ **Name:** Manage rejection (Red)

**Story:**
When a hotel rejects the proposal or shows no interest, the BD marks the prospect as **Red**, indicating the reason. The status remains as rejected but can be reactivated later if conditions change. Managing Red is **exclusive to the BD** (RR-V-06).

**Acceptance criteria:**
Mandatory reason (catalog: Not interested / No budget / Another company / Other). Mandatory comment (min. 30 characters). Option to mark "Reactivate later" so it appears in the list of reactivation candidates. Notifies the BDC of the rejection. Stays in the timeline.

**Documentation:**
- PRD: PRD-VENTAS-02 Business Developer
- Flow: Manage rejection (Red)
- Prototype: (Figma link)

**Flow:**
`Prospect detail (any pre-Orange status)` → MANUAL → `Click "Mark Red"` → `Select reason (catalog)` → `Mandatory comment (min. 30 characters)` → `Mark "Reactivate later" optional` → `Confirm` → AUTOMATICO → `Status changes to Red + Notifies the BDC + Timeline updated + If "reactivate" marked, appears in the list of reactivation candidates`

**Reactivation (RF-V-16):**
`List of Reds → Click on prospect → Click "Reactivate"` → AUTOMATICO → `Status returns to Light Blue (RR-V-07) + History keeps the rejection + Notifies the BDC`
