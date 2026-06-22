---
tags:
  - arquitectura
  - rol/supervisor-hotel
  - caso-de-uso
aliases:
  - CU RF-H-17 (Supervisor)
---

# 🪪 ID: RF-H-17
🏷️ **Name:** Put collaborator on Stand-by (Pink) — Supervisor

**Story:**
The Supervisor can put a collaborator on **Stand-by (Pink)** by operational decision: collaborator's vacation, low season, hotel's decision. This action is **shared with the Area Manager** (RR-H-11). The collaborator stays without Schedule or Timesheet until their status is changed.

**Acceptance criteria:**
Shared with the Area Manager (RR-H-11). The reason is mandatory (catalog: Vacation / Low season / Hotel's decision / Other). The collaborator cannot already be on Stand-by. The action notifies the collaborator and the Area Manager. It is kept in an auditable log. The position stays without an assigned collaborator in the Schedule.

**Documentation:**
- PRD: PRD-HOTEL-02 Supervisor
- Flow: Stand-by (Pink)
- Prototype: (Figma link)

**Flow:**
`Sidebar → My Staff → Collaborator detail` → MANUAL → `Click "Put on Stand-by"` → `Selects reason (catalog)` → `Optional notes` → `Confirm` → AUTOMATICO → If OK → `Collaborator's status to Pink + Without Schedule or Timesheet + Notifies the collaborator and the Area Manager + Auditable log` / If already on Stand-by → `Blocks with message`
