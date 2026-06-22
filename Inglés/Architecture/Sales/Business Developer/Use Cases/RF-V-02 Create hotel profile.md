---
tags:
  - arquitectura
  - rol/business-developer
  - caso-de-uso
aliases:
  - CU RF-V-02
---

# 🪪 ID: RF-V-02
🏷️ **Name:** Create hotel profile (Light Blue)

**Story:**
After the cold visit to the prospect, the BD gathers the hotel's data and loads it into the system: email, phone, contact name and position, business need, size and estimated headcount. This action moves the prospect from Gray to **Light Blue**.

**Acceptance criteria:**
Mandatory data: email (valid format), phone (valid format), contact name, position, business need (min. 30 characters). Size and estimated headcount are optional. On save, the status automatically changes to Light Blue and notifies the BDC of the progress.

**Documentation:**
- PRD: PRD-VENTAS-02 Business Developer
- Flow: Create hotel profile
- Prototype: (Figma link)

**Flow:**
`Prospect detail in Gray` → MANUAL → `Click "Create profile"` → `Fill in email, phone, contact, position, business need (min. 30 characters)` → `Size and estimated headcount optional` → `Confirm` → AUTOMATICO → If validations OK → `Saves profile + Status changes to Light Blue + Notifies the BDC + Timeline updated` / If error → `Blocks with clear message`
