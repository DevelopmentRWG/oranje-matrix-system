---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - UC RF-07
---

# 🪪 ID: RF-07
🏷️ **Name:** Create collaborator (Phase 1 — Initial interview)

**Story:**
The Recruiter conducts an initial interview with the candidate. They capture basic data (name, age, gender, address, phone) and create the record in the system. After creating it, a link is sent to the candidate to complete Phase 2 (sign-up in App) and Phase 3 (emergency data).

**Acceptance criteria:**
The record is created with status "Pending sign-up in app". A link is sent to the candidate by email/SMS. The Recruiter receives a notification when the candidate completes their sign-up.

**Documentation:**
- PRD: PRD-RECL-02 Recruiter
- Flow: Create collaborator
- Prototype: (Figma link)

**Flow:**
`Recruitment Module → Pool` → MANUAL → `Click on "New Collaborator"` → `Fill out Phase 1 form` → `Confirm` → AUTOMATIC → `Creates record + Sends link to candidate + Notifies Recruiter when Phase 2 is completed`
