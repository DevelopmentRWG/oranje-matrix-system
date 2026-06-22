---
tags:
  - arquitectura
  - rol/manager-de-area
  - caso-de-uso
aliases:
  - UC RF-H-06
---
H
# 🪪 ID: RF-H-06
🏷️ **Name:** Reject requisition with observations

**Story:**
When a requisition created by the Supervisor has errors (wrong positions, incorrect modality, incomplete data, insufficient justification), the Area Manager rejects it with observations. The requisition returns to the Supervisor in **In progress** status and the latter can correct and resubmit it. It is the formal mechanism to maintain the quality of requisitions before they reach Recruitment.

**Acceptance criteria:**
The reason and observations are mandatory (min. 20 characters). Upon rejecting, the requisition returns to the Supervisor with the observations visible in the detail. It notifies the Supervisor in less than 1 min. It is recorded in an auditable log with author, date and reason.

**Documentation:**
- PRD: PRD-HOTEL-03 Area Manager
- Flow: Requisition rejection
- Prototype: (Figma link)

**Flow:**
`Sidebar → Requisitions → "Pending authorization" inbox` → MANUAL → `Click on requisition` → `Reviews content` → MANUAL → `Click "Reject"` → `Selects reason (Wrong positions / Incorrect modality / Incomplete data / Missing justification / Other)` → `Writes mandatory observations (min. 20 characters)` → `Attaches optional evidence` → `Confirm` → AUTOMATICO → `Changes status to In progress + Notifies the Supervisor + Records in log with author/date/reason`
