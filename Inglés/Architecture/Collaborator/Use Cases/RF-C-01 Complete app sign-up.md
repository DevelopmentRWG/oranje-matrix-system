---
tags:
  - architecture
  - role/collaborator
  - use-case
aliases:
  - CU RF-C-01
---

# 🪪 ID: RF-C-01
🏷️ **Name:** Complete app sign-up — Phase 2

**Story:**
The Collaborator receives access to the app after the [[Recruiter]] captures their initial data (Phase 1). They must now complete their profile from the app by entering their work-related data: desired position, English level, experience level, type of transport, and hiring modality. Optionally they may enter their SSN and/or ITIN; if they do, the SSN/ITIN document upload field is enabled (photo or PDF of the card, also optional but recommended). If they provide neither SSN nor ITIN, the system shows a notice informing them that a 16% retention will be applied to their payment (refundable) and allows them to continue without blocking submission. Upon submitting the form, the system saves the data and notifies the [[Recruiter]] that there is a sign-up pending review. The collaborator is placed on hold awaiting validation.

**Acceptance criteria:**
SSN, ITIN, and the SSN/ITIN document are **optional**. If the collaborator provides neither SSN nor ITIN, the system displays a notice: *"Without SSN or ITIN, a 16% retention will be applied to your payment (refundable) — see [[Deductions]]"*; submission is **not blocked**. If they provide an ITIN, the retention is not applied (ITIN is a TaxID). If they enter an SSN or ITIN: valid SSN format: XXX-XX-XXXX; valid ITIN format: 9XX-XX-XXXX; both are masked after entry and stored encrypted (RNF-C-03). If they enter SSN or ITIN, the document upload field is enabled (optional · recommended); if uploaded, the file must be JPG, PNG, or PDF with a maximum size of 10 MB. Position, English level, experience level, type of transport, and modality are the **mandatory** catalog fields; without any of them, the system blocks submission and shows an error message next to the invalid field. Upon submitting, the collaborator's status transitions to → **White (Pre-assignment)**. The [[Recruiter]] receives a pending sign-up notification. The collaborator sees confirmation: *"Your sign-up was submitted. We will notify you when it is reviewed"*.

**Documentation:**
- PRD: [[03 - PRD]]
- Flow: [[Recruitment Flow|Recruitment Flow]] — Collaborator Sign-up
- Prototype: (Figma link)

**Flow:**
`App → Login → Dashboard` → MANUAL → `Sign-up Section → Phase 2` → `Enter SSN (optional, masked) and/or ITIN (optional, masked)` → If SSN/ITIN entered → `SSN/ITIN document upload field enabled (JPG/PNG/PDF, max. 10 MB — optional · recommended)` / If neither SSN nor ITIN → `System shows notice: "Without SSN or ITIN, a 16% retention will be applied to your payment (refundable)" · Collaborator may continue` → `Select Position (catalog · mandatory)` → `Select English level (catalog · mandatory)` → `Select Experience level (catalog · mandatory)` → `Select Type of transport (catalog · mandatory)` → `Select Modality (catalog · mandatory)` → `Submit` → AUTOMATIC → If mandatory fields valid → `Status → White · SSN/ITIN and document encrypted in storage (if provided) · 16% retention automatically activated if no SSN or ITIN (see [[Deductions]]) · Push notification to [[Recruiter]]: "Sign-up pending review" · Confirmation to collaborator: "Your sign-up was submitted"` / If mandatory field invalid or missing → `Blocks submission · Shows error message next to invalid field`
