---
tags:
  - arquitectura
  - rol/bdc
  - caso-de-uso
aliases:
  - CU RF-V-12
---

# 🪪 ID: RF-V-12
🏷️ **Name:** Approve conversion to client

**Story:**
**The final yes.** After validating the T&C and creating the Hotel User, the BDC **approves the conversion** of the prospect to an active client. This action is **exclusive to the BDC** (RR-V-01) and triggers the **Automatic Conversion Trigger** (RF-V-13), which executes 3 actions in parallel: welcome email to the hotel, notification to the BD, and removal from the Pipeline. The status changes to Orange and the hotel is enabled to generate requisitions from the Hotel module.

**Acceptance criteria:**
Only the BDC can approve (RR-V-01). Precondition: Hotel User created (RR-V-02). Precondition: T&C validated. Final confirmation mandatory (checkbox). The Automatic Trigger executes the 3 actions in under 1 min (RR-V-03). Status changes to Orange automatically. The Contract is generated using the validated T&C as input (RR-V-15). Recorded in an auditable log.

**Documentation:**
- PRD: PRD-VENTAS-03 BDC
- Flow: Approve conversion
- Prototype: (Figma link)

**Flow:**
`Prospect detail in Pink with validated T&C and created Hotel User → Conversion Sidebar` → MANUAL → `Click "Approve conversion"` → AUTOMATICO → `System validates that a Hotel User exists (RR-V-02)` → If OK → MANUAL → `Optional closing notes` → `Marks final confirmation ("I confirm the hotel meets the requirements to be activated")` → `Confirm` → AUTOMATICO → `Status changes to Orange + Automatic Trigger executes the 3 actions in parallel (email + notif to the BD + leaves Pipeline) + Generates Contract with validated T&C + Hotel becomes active + Auditable log + Notifies the BDC of success` / If there is no Hotel User → `Blocks with "You must create the Hotel User before approving the conversion"` / If T&C not validated → `Blocks with "The T&C Document must be validated"`

> [!important]
> This is the exact moment when a prospect becomes an **active Oranje client**. Post-Orange operations (Recruitment, Schedule, Timesheet) become available for the hotel.
