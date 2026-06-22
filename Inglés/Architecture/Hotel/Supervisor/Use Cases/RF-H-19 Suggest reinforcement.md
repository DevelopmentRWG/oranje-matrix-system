---
tags:
  - arquitectura
  - rol/supervisor-hotel
  - caso-de-uso
aliases:
  - CU RF-H-19
---

# 🪪 ID: RF-H-19
🏷️ **Name:** Suggest staff reinforcement

**Story:**
When the Supervisor reviews the weekly Schedule and detects a vacant position or one with partial coverage, they can quickly start a new requisition from that same view. The system **prefills** the position's data (position, vacant days, dept) in the New Requisition form — the Supervisor only completes the missing fields and sends it for authorization.

**Acceptance criteria:**
The suggestion is triggered from the Schedule module. The system pre-fills: position, vacant days, standard modality. The Supervisor must add the justification (min. 20 characters) and complete the remaining fields. On continuing, the flow proceeds as a regular new requisition (RF-H-01 → RF-H-03).

**Documentation:**
- PRD: PRD-HOTEL-02 Supervisor
- Flow: Suggest reinforcement
- Prototype: (Figma link)

**Flow:**
`Sidebar → Schedule (review)` → MANUAL → `Detects vacant / partial position` → `Click "Suggest reinforcement"` → AUTOMATICO → `Pre-fills New Requisition form with position, vacant days, standard modality` → MANUAL → `Adds justification (min. 20 characters)` → `Completes remaining fields (quantity / English / schedule / start date)` → `Click "Continue to New Requisition"` → Follows RF-H-01 → RF-H-03 flow
