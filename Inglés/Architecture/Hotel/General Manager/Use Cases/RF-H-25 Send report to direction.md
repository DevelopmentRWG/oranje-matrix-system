---
tags:
  - arquitectura
  - rol/manager-general
  - caso-de-uso
aliases:
  - UC RF-H-25
---

# 🪪 ID: RF-H-25
🏷️ **Name:** Send report to direction

**Story:**
After generating an executive report (RF-H-24), the General Manager formally sends it to direction by email or internal link. They can schedule a recurring send (weekly / monthly / quarterly) so the system generates and sends it automatically. It is the official channel through which direction receives the hotel's operational information.

**Acceptance criteria:**
The report must be generated beforehand (RF-H-24). Mandatory recipients (min. 1 director or valid email). Mandatory subject (min. 10 characters). If a recurring send is scheduled, the frequency is mandatory. Stays in history with recipient, subject, date and status (sent / read).

**Documentation:**
- PRD: PRD-HOTEL-04 General Manager
- Flow: Executive report sending
- Prototype: (Figma link)

**Flow:**
`Sidebar → Reports → Report preview (post RF-H-24)` → MANUAL → `Click "Send to direction"` → `Select recipients (list of directors or valid emails)` → `Fill in subject (min. 10 characters)` → `Optional message (max. 1000 characters)` → `Check "Schedule recurring send" optional` → If recurring → `Select frequency (Weekly / Monthly / Quarterly)` → `Confirm` → AUTOMATICO → `Sends report by email/internal link + Records in history (recipient / subject / date / status) + If recurring, schedules next send + Notifies the GM when it is read`
