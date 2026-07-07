---
tags:
  - architecture
  - role/collaborator
  - use-case
aliases:
  - CU RF-C-10
---

# 🪪 ID: RF-C-10
🏷️ **Name:** View My profile and status

**Story:**
The Collaborator wants to review their personal data and know their current status in the [[Collaborator Status Light]]. From "My Profile" they see all their data captured across the three phases: basic data from Phase 1 (captured by the Recruiter, read-only), work data from Phase 2, and emergency data from Phase 3. They also see the color and name of their current status light state. The Collaborator can edit in a limited way: their own phone number and their emergency data (contact, phone, relationship). Sensitive data such as SSN/ITIN is locked after Phase 2 approval and can only be modified with intervention from the [[Recruiter]].

**Acceptance criteria:**
View of all their data (Phase 1, 2, and 3) grouped by section. Status light state visible: color and name of the current state (example: "Orange — Fixed"). Fields editable by the collaborator themselves: own phone number, name/phone/relationship of the emergency contact. Changes to contact and emergency data do not require re-validation; they are saved immediately and recorded in the collaborator's journal. SSN/ITIN field: locked after Phase 2 approval; shows: *"To modify this data, contact your Recruiter"*. Phone with invalid format blocks saving with an error message. Saving emergency data without the contact name: blocks with an error message. Only sees their own data (RR-C-01).

**Documentation:**
- PRD: [[03 - PRD]]
- Flow: My Profile — Collaborator
- Prototype: (Figma link)

**Flow:**
`App → My Profile Section` → AUTOMATIC → `System loads collaborator data (Phase 1 + 2 + 3) and status light state` → MANUAL → `Collaborator reviews data in sections (basic data / work data / emergency data / status light state)` → `Taps "Edit" on allowed fields (own phone / emergency data)` → `Modifies the value` → `Save` → AUTOMATIC → If data valid → `System saves the change · Records in collaborator's journal · Confirmation: "Data updated"` / If phone with invalid format → `Blocks · Shows: "Enter a valid phone number"` / If attempts to edit SSN/ITIN → `Field locked · Shows: "To modify this data, contact your Recruiter"`
