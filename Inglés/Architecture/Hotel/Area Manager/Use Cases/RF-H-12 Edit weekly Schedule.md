---
tags:
  - arquitectura
  - rol/manager-de-area
  - caso-de-uso
aliases:
  - UC RF-H-12
---

# 🪪 ID: RF-H-12
🏷️ **Name:** Edit weekly Schedule

**Story:**
The Area Manager adjusts the dept's weekly Schedule: reorders shifts, moves collaborators between days or shifts within the same position, marks rest days. The edit is a **live operation**: it changes the actual hours the collaborators work and is immediately reflected in their Timesheet and notifications.

**Acceptance criteria:**
The Area Manager sees the dept's weekly calendar (Monday → Sunday) with position rows and day columns. Edits persist in less than 2s. If the change generates an overlap (same collaborator in 2 shifts at the same time), the system blocks it with a clear message. Each edit notifies the affected collaborator. It recalculates the Timesheet Compliance Indicator if applicable.

**Documentation:**
- PRD: PRD-HOTEL-03 Area Manager
- Flow: Weekly Schedule edition
- Prototype: (Figma link)

**Flow:**
`Sidebar → Schedule` → MANUAL → `Selects week` → `Click on cell (collaborator × day × position)` → `Edits schedule / moves collaborator / marks rest` → `Confirm` → AUTOMATICO → `Validates there are no overlaps` → If OK → `Persists change + Notifies the collaborator + Recalculates Compliance Indicator` / If overlap → `Blocks with message "The collaborator is already assigned at this time in another position"`
