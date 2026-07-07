---
tags:
  - architecture
  - role/collaborator
  - use-case
aliases:
  - CU RF-C-07
---

# 🪪 ID: RF-C-07
🏷️ **Name:** View My Timesheet

**Story:**
The Collaborator wants to review their recorded hours during the week. From the app they access "My Timesheet" and see the weekly table with the 6 possible clock-ins per shift, gross hours, the applied lunch deduction, and net hours per day. They can navigate between the current week and previous weeks. The view is **read-only**; the Collaborator cannot correct punches (exclusive to the [[Area Manager]]). Only THEIR own records are shown.

**Acceptance criteria:**
Read-only view (RR-C-01). Only shows the collaborator's own Timesheet. Information visible per shift: Clock-in, Lunch Out, Lunch In, Break Out, Break In, Clock-out; gross hours, lunch deduction, net hours. The collaborator can navigate between the current week and previous weeks. They have no access to the Extended Lunch Indicator (exclusive to Inspector, Coordinator, and Recruitment Manager). They cannot correct punches; if they detect an error, they must contact their supervisor. If there are no clock-ins in the selected week, the system shows an empty state.

**Documentation:**
- PRD: [[03 - PRD]]
- Flow: [[Timesheet]] — Collaborator View
- Prototype: (Figma link)

**Flow:**
`App → My Timesheet Section` → MANUAL → `Select week (current / previous weeks)` → AUTOMATIC → `System loads collaborator's Timesheet for the selected week` → `Shows table: clock-ins per shift (up to 6) · gross hours · lunch deduction · net hours` / If no records → `Shows empty state: "No attendance records for this week"`
