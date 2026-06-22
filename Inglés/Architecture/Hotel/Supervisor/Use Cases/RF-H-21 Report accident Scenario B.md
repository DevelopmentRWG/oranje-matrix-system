---
tags:
  - arquitectura
  - rol/supervisor-hotel
  - caso-de-uso
aliases:
  - CU RF-H-21
---

# 🪪 ID: RF-H-21
🏷️ **Name:** Report workplace accident — Scenario B

**Story:**
**Scenario B:** the Supervisor detects an accident on the property first (before the collaborator manages to report it from their app, or when the collaborator cannot report it). The Supervisor creates the accident card from their app with all the in-person data. The signal reaches the zone [[Inspector]] automatically so they can start the investigation.

**Acceptance criteria:**
The Supervisor must identify the affected collaborator from the list of assigned ones. The description of circumstances must have at least 50 characters. The immediate care is mandatory. The accident date cannot be in the future. The card is created with an auto number (same format as requisitions — RR-H-04). It notifies the zone Inspector in under 1 min. The collaborator moves to **Gray** status (RR-H-20).

**Documentation:**
- PRD: PRD-HOTEL-02 Supervisor
- Flow: Workplace Accident — Scenario B
- Prototype: (Figma link)

**Flow:**
`Sidebar → Workplace Accidents (Supervisor detects the accident on the property)` → MANUAL → `Opens app → Click "Report Accident"` → `Selects Scenario B` → `Selects affected collaborator from the list of assigned ones` → `Fills accident date and time (not in the future)` → `Exact location (min. 10 characters)` → `Circumstances (min. 50 characters)` → `Immediate care provided (min. 20 characters)` → `Optional witnesses` → `Attaches evidence (photo/video, max. 10 MB)` → `Confirm` → AUTOMATICO → `Accident card created with auto number + Collaborator's status to Gray + Notifies the zone Inspector + Starts investigation + Auditable log`
