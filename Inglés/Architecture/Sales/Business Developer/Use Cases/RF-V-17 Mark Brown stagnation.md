---
tags:
  - arquitectura
  - rol/business-developer
  - caso-de-uso
aliases:
  - CU RF-V-17 (BD)
---

# 🪪 ID: RF-V-17
🏷️ **Name:** Mark stagnation (Brown)

**Story:**
When a prospect does not advance after multiple contact attempts (no response, contact change, indecision), the BD marks it as **Brown (Stagnation)**. From that moment, **the case passes to the BDC**, who is the only one that can investigate the cause, provide a solution and reactivate (RF-V-18, RF-V-19). The BD can no longer modify this prospect until the BDC unblocks it.

**Acceptance criteria:**
Mandatory reason (catalog: No response / Contact change / Undefined / Other). Notes for the BDC mandatory (min. 30 characters) — they help the BDC understand the context. Notifies the BDC in less than 1 min. Blocks editing by the BD until unblocking. Stays in the timeline.

**Documentation:**
- PRD: PRD-VENTAS-02 Business Developer
- Flow: Mark stagnation (Brown)
- Prototype: (Figma link)

**Flow:**
`Stagnant prospect detail` → MANUAL → `Click "Mark Brown"` → `Select reason (catalog)` → `Notes for the BDC (min. 30 characters)` → `Confirm` → AUTOMATICO → `Status changes to Brown + Notifies the BDC + Blocks the BD's editing + Appears in the BDC's Brown inbox + Timeline updated`

> [!info]
> The BDC unblocks Brown (RF-V-18) and then reactivates the prospect (RF-V-19), returning it to Light Blue. From there, the BD regains control and can continue the process.
