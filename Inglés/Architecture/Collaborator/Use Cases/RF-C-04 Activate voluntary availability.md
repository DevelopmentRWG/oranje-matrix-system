---
tags:
  - architecture
  - role/collaborator
  - use-case
aliases:
  - CU RF-C-04
---

# 🪪 ID: RF-C-04
🏷️ **Name:** Activate voluntary availability (Yellow)

**Story:**
The Collaborator who is free (Strong Green, Orange, or Pink) wants to declare that they are available to receive a temporary assignment. From the app they activate the voluntary availability toggle. The system requests explicit confirmation before executing the change. Upon confirming, the collaborator's status transitions to **Yellow (Voluntary available)** immediately, without approval from any other role (RR-C-02). This is the **only status transition the Collaborator activates autonomously**. Yellow is a declaration of availability, not an assignment; the collaborator is visible in the Pool as a voluntary available but still has no [[Schedule]] or active [[Timesheet]] until the [[Recruiter]] assigns them (→ Café). The collaborator can also deactivate Yellow to return to Strong Green when they no longer wish to be available.

**Acceptance criteria:**
The toggle is only available if the collaborator is in Strong Green, Orange, or Pink state; in any other state the system blocks it with the corresponding message. The system requires modal confirmation with a "Confirm availability" button before executing the change (RR-C-02). Upon confirming, the status transitions immediately to Yellow. Confirmation to the collaborator: *"You have been registered as available. Recruitment may assign you"*. In Yellow, the collaborator has no active assignment and cannot clock in. If the collaborator deactivates the toggle, the status returns to Strong Green and the confirmation appears: *"You are no longer showing as a voluntary available"*.

**Documentation:**
- PRD: [[03 - PRD]]
- Flow: [[Collaborator Status Light]] — Yellow Transition
- Prototype: (Figma link)

**Flow:**
`App → Availability Section` → MANUAL → `Activates "I am available" toggle` → `System shows modal confirmation: "Do you confirm you are available for a temporary assignment?"` → `Collaborator taps "Confirm availability"` → AUTOMATIC → If valid state (Strong Green / Orange / Pink) → `Status → Yellow · Collaborator appears in Pool as voluntary available · Confirmation: "You have been registered as available. Recruitment may assign you"` / If invalid state (Café / Purple / Red / Gray / Black) → `Blocks · Shows: "You cannot modify your availability in your current state. Contact Recruitment"` / If already in Café (active assignment) → `Blocks · Shows: "You cannot declare yourself available while you have an active assignment"`
