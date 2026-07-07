---
tags:
  - architecture
  - role/collaborator
  - use-case
aliases:
  - CU RF-C-06
---

# 🪪 ID: RF-C-06
🏷️ **Name:** View My Schedule

**Story:**
The Collaborator wants to review their assigned shifts for the week. From the app they access the "My Schedule" section and see the weekly calendar with their own assignments: hotel, position, schedule, and dates. The collaborator can navigate between the current week and the next. The view is **read-only**; the Collaborator cannot edit the Schedule (RR-C-01). Only THEIR assignments are shown, never data from other collaborators.

**Acceptance criteria:**
Read-only view (RR-C-01). Only shows the collaborator's own assignments. Information visible per shift: hotel, position, schedule (expected clock-in and clock-out time), dates. The collaborator can navigate between the current week and the next week. Available in list view and calendar view. If there are no assignments in the selected week, the system shows an empty state: *"You have no assigned shifts this week"*. They have no access to other collaborators' Schedules or the Schedule editing tool.

**Documentation:**
- PRD: [[03 - PRD]]
- Flow: [[Schedule]] — Collaborator View
- Prototype: (Figma link)

**Flow:**
`App → My Schedule Section` → MANUAL → `Select week (current / next)` → `Select view (list / calendar)` → AUTOMATIC → `System loads collaborator's assignments for the selected week` → `Shows: hotel, position, schedule, dates per shift` / If no assignments → `Shows: "You have no assigned shifts this week"`
