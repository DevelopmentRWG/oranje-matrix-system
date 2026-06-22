---
tags:
  - arquitectura
  - rol/supervisor-hotel
  - caso-de-uso
aliases:
  - CU RF-H-20
---

# 🪪 ID: RF-H-20
🏷️ **Name:** Report workplace accident — Scenario A

**Story:**
**Scenario A:** a collaborator assigned to the hotel suffers an accident and reports it first from the collaborator app. The signal reaches the department Supervisor and the zone [[Inspector]] **simultaneously**. The Supervisor must **go physically** to the incident location and capture in-person information: exact location, circumstances, witnesses and immediate care provided.

**Acceptance criteria:**
Simultaneous notification to the Supervisor and the Inspector in under 1 min after the collaborator's report. The Supervisor must complete the in-person form (all mandatory fields). The description of circumstances must have at least 50 characters. The immediate care is mandatory. The collaborator moves to the **Gray (Injured)** status in the Collaborator Status Light, which protects them from the 3-absences rule (RR-H-20).

**Documentation:**
- PRD: PRD-HOTEL-02 Supervisor
- Flow: Workplace Accident — Scenario A
- Prototype: (Figma link)

**Flow:**
`Sidebar → Workplace Accidents ← Push notification: "Collaborator X reported an accident"` → AUTOMATICO → `Collaborator's status to Gray + Accident card created with data from the collaborator's report + Zone Inspector notified simultaneously` → MANUAL → `Supervisor goes physically to the location` → `Opens the accident card from the app` → `In-person capture: exact location + circumstances (min. 50 characters) + immediate care (min. 20 characters) + optional witnesses` → `Attaches evidence (photo/video, max. 10 MB)` → `Confirms scenario A` → `Confirm` → AUTOMATICO → `Card updated with in-person capture + Notifies the Inspector of the progress + Kept in auditable log`
