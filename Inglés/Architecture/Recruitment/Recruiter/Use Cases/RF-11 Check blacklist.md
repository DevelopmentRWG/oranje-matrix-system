---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - UC RF-11
---

# 🪪 ID: RF-11
🏷️ **Name:** Check Blacklist

**Story:**
Before assigning a candidate, the Recruiter MUST check the Blacklist (rule RR-02). If the candidate appears on the Blacklist, the system blocks the assignment with a visible alert and shows the reason for the ban.

**Acceptance criteria:**
The check is mandatory before each assignment. If the candidate is on the Blacklist, the system blocks with a visible alert and shows the reason + date of the ban.

**Documentation:**
- PRD: PRD-RECL-02 Recruiter
- Flow: Blacklist check
- Prototype: (Figma link)

**Flow:**
`Recruitment Module` (when assigning collaborator) → AUTOMATIC → `System checks whether candidate is on the Blacklist` → If yes → `Blocks with alert + Shows reason for the ban` / If not → `Allows continuing with assignment`
