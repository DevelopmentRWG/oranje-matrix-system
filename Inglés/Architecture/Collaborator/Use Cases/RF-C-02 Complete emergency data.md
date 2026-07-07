---
tags:
  - architecture
  - role/collaborator
  - use-case
aliases:
  - CU RF-C-02
---

# 🪪 ID: RF-C-02
🏷️ **Name:** Complete emergency data — Phase 3

**Story:**
Once the Collaborator has completed Phase 2, they complete their emergency and health profile from the app: name, phone number and relationship of the emergency contact, blood type, and allergies or medical conditions (optional). Once both phases are complete (Phase 2 + Phase 3), the collaborator's status remains **White** pending validation by the [[Recruiter]]. The [[Recruiter]] validates the sign-up and, upon approval, transitions the collaborator from White → Strong Green (see [[RF-08 Validate app sign-up]]). Emergency data remains available for use in case of a [[Workplace Accident]].

**Acceptance criteria:**
Emergency contact name: mandatory, minimum 3 characters. Contact phone number: mandatory, valid phone format. Relationship: mandatory, catalog (Mother / Father / Spouse / Brother/Sister / Son/Daughter / Friend / Other). Blood type: mandatory, catalog (A+, A–, B+, B–, AB+, AB–, O+, O–, Don't know). Allergies or medical conditions: optional, maximum 500 characters. On save, the system confirms: *"Emergency data saved"*. Phase 3 data complements the sign-up; it does not change the status light state on its own. The [[Recruiter]] is the one who transitions from White → Strong Green upon approving the complete sign-up (Phase 2 + Phase 3).

**Documentation:**
- PRD: [[03 - PRD]]
- Flow: [[Recruitment Flow|Recruitment Flow]] — Collaborator Sign-up
- Prototype: (Figma link)

**Flow:**
`App → Sign-up Section → Phase 3` → MANUAL → `Enter emergency contact name` → `Enter contact phone number` → `Select relationship (catalog)` → `Select blood type (catalog)` → `Enter allergies / medical conditions (optional)` → `Save` → AUTOMATIC → If fields valid → `Data saved · Confirmation: "Emergency data saved" · Sign-up Phase 2 + Phase 3 complete · Status remains White · [[Recruiter]] notified of complete sign-up pending review` / If field invalid or missing → `Blocks save · Shows error message next to invalid field`
