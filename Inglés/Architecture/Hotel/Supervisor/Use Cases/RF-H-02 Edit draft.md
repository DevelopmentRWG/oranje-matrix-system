---
tags:
  - arquitectura
  - rol/supervisor-hotel
  - caso-de-uso
aliases:
  - CU RF-H-02
---

# 🪪 ID: RF-H-02
🏷️ **Name:** Edit requisition draft

**Story:**
Before sending a requisition for authorization, the Supervisor can edit it freely to add/remove positions, adjust schedules, change modalities or supplement the notes. They can also edit requisitions **rejected** by the Area Manager (which returned to Apple Green — In progress status with observations), correcting what the Manager flagged.

**Acceptance criteria:**
Only the Supervisor who created the requisition can edit it in draft or rejected status. Changes persist in under 2s. The status is kept after editing. The Area Manager's observations (in case of rejection) are visible during editing to guide the correction. If the requisition moves to Authorized or any other later status, it can no longer be edited by the Supervisor.

**Documentation:**
- PRD: PRD-HOTEL-02 Supervisor
- Flow: Requisition editing
- Prototype: (Figma link)

**Flow:**
`Sidebar → Requisitions → My Requisitions → Drafts or Rejected` → MANUAL → `Click on requisition` → `Click "Edit"` → `Modifies fields (positions / schedules / modality / notes)` → If it was rejected → `Reads Manager's observations visible in the detail` → MANUAL → `Save changes` → AUTOMATICO → `Changes persist + Status is kept` → MANUAL → `Resend for authorization` (triggers RF-H-03)
