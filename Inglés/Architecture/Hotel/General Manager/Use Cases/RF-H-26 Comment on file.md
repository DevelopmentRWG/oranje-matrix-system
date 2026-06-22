---
tags:
  - arquitectura
  - rol/manager-general
  - caso-de-uso
aliases:
  - UC RF-H-26
---

# 🪪 ID: RF-H-26
🏷️ **Name:** Comment on the requisition file

**Story:**
When the General Manager detects a delayed, poorly assembled requisition or one that requires the attention of the responsible Department Manager, they add a comment to the requisition file. The comment is visible to the Manager and stays in the requisition journal. It is the formal channel of **supervision without operation**: the General Manager does not authorize or modify, but leaves a trace.

**Acceptance criteria:**
The comment must have at least 20 characters. It appears in the requisition journal with author and date. Notifies the responsible Department Manager. Can notify other parties involved (Supervisor, etc.) if selected. Optional attachments (PDF/JPG/PNG, max. 5 MB).

**Documentation:**
- PRD: PRD-HOTEL-04 General Manager
- Flow: Comment on the file
- Prototype: (Figma link)

**Flow:**
`Sidebar → Requisitions → Requisition detail (global view)` → MANUAL → `Click "Comment"` → `Write comment (min. 20 characters)` → `Select additional recipients optional` → `Attach file optional` → `Confirm` → AUTOMATICO → `Comment appears in journal + Notifies the Department Manager + Notifies additional recipients if applicable + Stays in log with author and date`
