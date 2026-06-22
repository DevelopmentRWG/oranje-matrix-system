---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-25
---

# 🪪 ID: RF-25
🏷️ **Name:** Send report to the Manager

**Story:**
After generating a group report (RF-24), the Group Leader formally sends it to the Recruitment Manager. The submission creates a notification with a link to the report, is recorded in the history and triggers its reading by the Manager. It is the official channel through which the Group Leader reports their group's performance.

**Acceptance criteria:**
Only the Group Leader can send (exclusive action). The report must have been generated beforehand (RF-24). The submission notifies the Manager in under 1 min. It is kept in the history of sent reports with date, recipient and status (sent / read). Optional comment to the Manager.

**Documentation:**
- PRD: PRD-RECL-02 Líder de Grupo
- Flow: Formal report submission
- Prototype: (Figma link)

**Flow:**
`Report preview (post RF-24)` → MANUAL → `Click "Send to Manager"` → `Optional comment` → `Confirm` → AUTOMATICO → `Notifies the Manager with a link to the report + Records in history (date / recipient / status) + Changes report status to "Sent"`
