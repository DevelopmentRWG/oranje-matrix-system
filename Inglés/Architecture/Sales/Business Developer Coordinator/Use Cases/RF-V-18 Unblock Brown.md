---
tags:
  - arquitectura
  - rol/bdc
  - caso-de-uso
aliases:
  - CU RF-V-18
---

# 🪪 ID: RF-V-18
🏷️ **Name:** Unblock stalemate (Brown)

**Story:**
When a BD marks a prospect as **Brown** due to a stalemate, the case lands in the BDC's Brown inbox. The BDC investigates the context (BD notes, contact history, previous attempts), diagnoses the real cause, and agrees on a solution to resume the negotiation. This action is **exclusive to the BDC** (RR-V-04) and precedes reactivation (RF-V-19).

**Acceptance criteria:**
Only the BDC can unblock Brown (RR-V-04). Mandatory diagnosis (min. 50 characters). Mandatory agreed solution (min. 50 characters). Mandatory decision: Reactivate to Light Blue / Reassign to another BD / Close as Red. Notifies the original BD with the solution. Recorded in an auditable log.

**Documentation:**
- PRD: PRD-VENTAS-03 BDC
- Flow: Unblock Brown
- Prototype: (Figma link)

**Flow:**
`BDC's Brown inbox` → MANUAL → `Click on prospect` → `Investigates history, BD notes, contact attempts` → MANUAL → `Click "Unblock Brown"` → `Diagnosis (min. 50 characters)` → `Agreed solution (min. 50 characters)` → `Decision (catalog: Reactivate / Reassign / Close as Red)` → `Confirm` → AUTOMATICO → If Reactivate → `Status returns to Light Blue + Notifies the original BD (triggers RF-V-19)` / If Reassign → `Changes assigned BD + Status to Light Blue + Notifies both BDs` / If Close as Red → `Status changes to Red + Notifies the original BD`
