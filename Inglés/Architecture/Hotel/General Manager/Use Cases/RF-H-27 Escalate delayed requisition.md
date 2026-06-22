---
tags:
  - arquitectura
  - rol/manager-general
  - caso-de-uso
aliases:
  - UC RF-H-27
---

# 🪪 ID: RF-H-27
🏷️ **Name:** Escalate delayed requisition

**Story:**
When an authorized requisition has been in the Recruitment inbox for a long time without being taken (especially if it is Red urgency or a VIP hotel), the General Manager **escalates it to the Recruitment Manager** to prioritize it. The escalation formally notifies the Recruitment Manager with context and reason, and the system marks the requisition as "Escalated".

**Acceptance criteria:**
Action exclusive to the General Manager. Mandatory reason (catalog: Excessive time in queue / Red urgency / VIP Hotel / Other). Mandatory message to the Recruitment Manager (min. 30 characters). Notifies the Recruitment Manager in less than 1 min. Changes the requisition indicator to "Escalated". Stays in auditable log.

**Documentation:**
- PRD: PRD-HOTEL-04 General Manager
- Flow: Escalate delayed requisition
- Prototype: (Figma link)

**Flow:**
`Sidebar → Requisitions → Authorized requisition detail (untaken for a long time)` → MANUAL → `Click "Escalate to Recruitment"` → `Select reason (catalog)` → `Write message to the Recruitment Manager (min. 30 characters)` → `Confirm` → AUTOMATICO → `Notifies the Recruitment Manager with link to the file + Changes indicator to "Escalated" + Stays in auditable log + Notifies the responsible Department Manager`
