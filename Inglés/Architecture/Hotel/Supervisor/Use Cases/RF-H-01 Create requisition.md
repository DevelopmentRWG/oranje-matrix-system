---
tags:
  - arquitectura
  - rol/supervisor-hotel
  - caso-de-uso
aliases:
  - CU RF-H-01
---

# 🪪 ID: RF-H-01
🏷️ **Name:** Create requisition

**Story:**
When the hotel detects a staffing need (shift coverage, seasonal reinforcement, replacement due to leave), the Supervisor creates a new requisition from the app. They capture the positions, quantity, modality, English level, schedules, start date and additional notes. The requisition stays as a **draft** (Apple Green — In progress) until the Supervisor sends it for the Area Manager's authorization.

**Acceptance criteria:**
The system automatically assigns the requisition number with the format `YYYYMMDDHHMM + Homoclave` (RR-H-04). A requisition can have multiple positions. The start date must be in the future. If the requisition has no positions when leaving the editor, it is physically deleted (RR-H-07). The Supervisor can create from mobile (RNF-H-04) or desktop.

**Documentation:**
- PRD: PRD-HOTEL-02 Supervisor
- Flow: Requisition creation
- Prototype: (Figma link)

**Flow:**
`Sidebar → Requisitions → Click "New Requisition"` → MANUAL → `Fills header (additional notes)` → `Adds positions (Position + Quantity + Modality + English + Schedule + Start date)` → `Save draft` → AUTOMATICO → `System assigns auto number + Draft status (Apple Green — In progress)` → MANUAL (later) → `Click "Send for authorization"` (triggers RF-H-03)
