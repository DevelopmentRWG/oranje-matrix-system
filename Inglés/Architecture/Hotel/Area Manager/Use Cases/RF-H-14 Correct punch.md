---
tags:
  - arquitectura
  - rol/manager-de-area
  - caso-de-uso
aliases:
  - UC RF-H-14
---

# 🪪 ID: RF-H-14
🏷️ **Name:** Correct Timesheet punch

**Story:**
When a collaborator forgets to punch, punches incorrectly or has a technical problem with the QR, the Area Manager manually corrects the punch. It is an exceptional action with **mandatory justification** that is recorded in an auditable log. Only the Area Manager can do it (not the Supervisor, not the General Manager).

**Acceptance criteria:**
Justification is mandatory (min. 20 characters). The change is recorded in an auditable log with author, date, reason, previous value and new value. It notifies the collaborator of the change. If the corrected time is outside the range of the collaborator's workday, the system shows a warning and requests additional confirmation. It recalculates gross hours, Lunch deduction and net hours.

**Documentation:**
- PRD: PRD-HOTEL-03 Area Manager
- Flow: Punch correction
- Prototype: (Figma link)

**Flow:**
`Sidebar → Timesheet` → MANUAL → `Click on workday with problem` → `Identifies punch to correct` → `Click "Correct punch"` → `Selects type (Clock in / Lunch out / Lunch in / Break out / Break in / Clock out)` → `Enters corrected time (HH:MM)` → `Mandatory justification` → `Attaches optional evidence` → `Confirm` → AUTOMATICO → If time valid → `Applies change + Recalculates gross hours, lunch, net + Auditable log + Notifies the collaborator` / If time out of range → `Warning + additional confirmation`
