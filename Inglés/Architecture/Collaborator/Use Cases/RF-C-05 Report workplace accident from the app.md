---
tags:
  - architecture
  - role/collaborator
  - use-case
aliases:
  - CU RF-C-05
---

# 🪪 ID: RF-C-05
🏷️ **Name:** Report workplace accident from the app

**Story:**
The Collaborator suffers an accident while assigned to the hotel and reports the incident directly from the app (**Scenario A** of the [[Workplace Accident Flow]]). They complete the report form with the date, time, and description of the accident; they may attach photos and optionally allow geolocation capture. Upon submitting, the system creates the [[Workplace Accident]] card, transitions the collaborator's status to **Gray — Injured**, and simultaneously notifies the hotel [[Supervisor]] and the zone [[Inspector]]. The collaborator is protected from the 3-absences rule → [[Blacklist]] while remaining in Gray.

> [!info]
> This use case corresponds to **Scenario A** of the [[Workplace Accident Flow]]: the collaborator detects and reports first. The collaborator's role in the full flow is limited to generating the initial signal and briefly describing the incident. Detailed on-site information (exact location, circumstances, witnesses, immediate care) is captured by the [[Supervisor]] who attends in person. The [[Inspector]] completes the medical follow-up and is the final responsible for closing the card.

**Acceptance criteria:**
Accident date: mandatory, cannot be in the future. Accident time: mandatory, HH:MM format. Description: mandatory, minimum 50 characters. Photo evidence: optional, JPG/PNG, maximum 10 MB per file; if the limit is exceeded, the system rejects the file and shows a message. Geolocation: optional, automatically captured from the device if the collaborator grants permission. Upon successful submission: system creates an accident card with an automatic report number; collaborator's status transitions to Gray (from any active state → Gray); simultaneous notification to the hotel Supervisor and zone Inspector in under 1 minute; protection against the 3-absences rule activated. Confirmation to the collaborator: *"Your report was submitted. The zone Inspector will receive the case"*.

**Documentation:**
- PRD: [[03 - PRD]]
- Flow: [[Workplace Accident Flow]] — Scenario A
- Prototype: (Figma link)

**Flow:**
`App → Report Accident Section` → MANUAL → `Enter accident date` → `Enter accident time` → `Describe the accident (min. 50 characters)` → `Attach photo/evidence optional (JPG/PNG, max. 10 MB)` → `Allow optional geolocation` → `Submit report` → AUTOMATIC → If fields valid → `Accident card created with automatic number · Collaborator status → Gray (Injured) · Simultaneous notification to hotel [[Supervisor]] and zone [[Inspector]] (< 1 min) · 3-absences rule protection activated · Confirmation to collaborator: "Your report was submitted. The zone Inspector will receive the case"` / If description < 50 characters → `Blocks · Shows: "Description must be at least 50 characters"` / If future date → `Blocks · Shows: "Accident date cannot be in the future"` / If photo > 10 MB → `Rejects file · Shows: "Maximum photo size: 10 MB"`
