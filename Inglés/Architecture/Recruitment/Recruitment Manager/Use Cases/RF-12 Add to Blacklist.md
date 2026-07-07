---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - UC RF-12
---

# 🪪 ID: RF-12
🏷️ **Name:** Add to Blacklist

**Story:**
Any role in the Recruitment department (Recruiter, Group Leader or Manager) can manually register a collaborator in the [[Core/Modules/Blacklist|Blacklist]] when they have committed a serious offense. The Manager executes this same flow without additional privileges: they must provide the ban reason, a detailed description and mandatory evidence. The collaborator transitions to the Black state permanently; the record is kept in an auditable log and blocks future assignments. The 3-absences rule is handled automatically by the system and requires no Manager action. Dispute resolution (Red state) is the exclusive responsibility of the [[Inspector]], not the Manager.

**Acceptance criteria:**
The form blocks submission if the reason, description (min. 30 characters) or evidence attachment (min. 1 file) is missing. Upon confirmation, the collaborator transitions to Black (permanent) in the Collaborator Status Light. The system notifies the collaborator and blocks future assignments immediately. The entry is kept in an auditable log with author, date and evidence. The Manager CANNOT remove the collaborator from the Blacklist once registered.

**Documentation:**
- PRD: PRD-RECL-04 Manager
- Flow: Blacklist
- Prototype: (Figma link)

**Flow:**
`Blacklist Module` → MANUAL → `Click "Add to Blacklist"` → `Search collaborator in Pool (Collaborator field)` → `Select ban reason (Catalog: 3 absences / Dispute / Serious offense)` → `Write detailed description (min. 30 characters)` → `Attach evidence (min. 1 file, max. 10 MB each)` → `Select incident date` → `Confirm` → AUTOMATIC → `Collaborator transitions to Black (permanent) in Collaborator Status Light + Blocks future assignments + Notifies collaborator + Records in auditable log (author, date, reason, evidence)`
