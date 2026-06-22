---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - UC RF-08
---

# 🪪 ID: RF-08
🏷️ **Name:** Validate sign-up in App (Phase 2)

**Story:**
After the candidate's self-registration in the Oranje app (where they complete SSN, ITIN, position, English, experience, transportation, modality), the Recruiter reviews the data and uploaded documents. If everything is fine, they approve the collaborator and they become enabled in the Pool.

**Acceptance criteria:**
After approval, the collaborator becomes enabled for assignment. Accesses are propagated automatically. Status light state: Strong Green (Available).

**Documentation:**
- PRD: PRD-RECL-02 Recruiter
- Flow: Validate collaborator
- Prototype: (Figma link)

**Flow (approval):**
`"Pending validation" inbox` → MANUAL → `Open candidate` → `Review data and documents` → MANUAL → `Click "Approve"` → AUTOMATIC → `System enables collaborator + Propagates accesses + Notifies the collaborator` → `Status Light: Strong Green (Available)`

**Flow (rejection):**
`"Pending validation" inbox` → MANUAL → `Open candidate` → `Review data and documents` → MANUAL → `Click "Reject"` → `Enter reason (mandatory field)` → AUTOMATIC → `System notifies the collaborator with the reason so they can correct data/documents in the app` → `Accesses are NOT enabled` → `The record remains in "Pending validation" until a new review`

> [!info]
> Rejection is NOT a permanent removal. The collaborator can correct their data or documents in the app and return to "Pending validation" status for a new review by the Recruiter.
