---
tags:
  - arquitectura
  - rol/bdc
  - caso-de-uso
aliases:
  - CU RF-V-11
---
H
# 🪪 ID: RF-V-11
🏷️ **Name:** Create Hotel User

**Story:**
Before approving the conversion of a prospect to a client, the BDC must create the **Hotel User** in the system. This user will be the main person responsible for the hotel on the platform (Area Manager or General Manager) and will receive the credentials after approval. It is the **mandatory precondition** of the conversion (RR-V-02): without a Hotel User, the "Approve conversion" button stays locked.

**Acceptance criteria:**
Only the BDC can create the Hotel User (exclusive action). Email unique in the system. Mandatory role: Area Manager or General Manager (simple or extended hierarchy). On creation, the system saves the user but does NOT send credentials yet — it waits for conversion approval. The "Approve conversion" button is enabled as soon as the Hotel User exists.

**Documentation:**
- PRD: PRD-VENTAS-03 BDC
- Flow: Create Hotel User
- Prototype: (Figma link)

**Flow:**
`Prospect detail in Pink with validated T&C → Conversion Sidebar` → MANUAL → `Click "Create Hotel User"` → `Fills in email (unique), full name, assigned role (Area Manager / General Manager), optional phone, optional notes` → `Confirm` → AUTOMATICO → If email unique → `User created + Enables "Approve conversion" button + Auditable log` / If email duplicate → `Blocks with "This email is already registered in the system"`

> [!info]
> The welcome email to the hotel user is NOT sent at this moment. It is sent when the BDC approves the conversion (RF-V-12) as part of the Automatic Trigger.
