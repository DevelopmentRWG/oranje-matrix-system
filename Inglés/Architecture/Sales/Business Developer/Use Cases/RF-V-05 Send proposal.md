---
tags:
  - arquitectura
  - rol/business-developer
  - caso-de-uso
aliases:
  - CU RF-V-05
---

# 🪪 ID: RF-V-05
🏷️ **Name:** Send proposal to hotel

**Story:**
After drafting the Personalized Proposal, the BD sends it to the hotel by email from the platform. This send marks the change of the prospect's status to **Green** (Proposal Sent). The hotel receives the document and the follow-up window begins.

**Acceptance criteria:**
The proposal must be complete (services, prices, terms, validity). On send, the status automatically changes to Green. The BDC is notified of the send. The email is kept in the send history. The proposal becomes non-editable in this version (it can be duplicated as a template).

**Documentation:**
- PRD: PRD-VENTAS-02 Business Developer
- Flow: Send proposal
- Prototype: (Figma link)

**Flow:**
`Proposal preview (post RF-V-04)` → MANUAL → `Click "Send to hotel"` → `Confirm recipients (hotel email pre-filled)` → `Optional message for the hotel` → `Confirm` → AUTOMATICO → If proposal complete → `Sends email with attached proposal + Status changes to Green + Notifies the BDC + Locks editing of this version + Logs send in history` / If proposal incomplete → `Blocks with message "Complete services and prices"`
