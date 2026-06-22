---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-36
---

# 🪪 ID: RF-36
🏷️ **Name:** View detailed workload of the Recruiter

**Story:**
From a Recruiter's detail in the "My Group" module, the Leader opens her **current workload**: the requisitions she has **in progress** (not closed), with hotel · zone, position, urgency (status light) and % of coverage. It lets him see at a glance whether a Recruiter is overloaded or has urgent cases with no progress, to decide whether to support her or reassign one of her requisitions (RF-37).

**Acceptance criteria:**
Scope restricted to Recruiters of the Leader's own group (rule RR-10). Shows **only requisitions in progress** (active), not the history of closed ones. For each requisition: ID, hotel · zone, position, urgency (🔴/🟡/🟢) and % of coverage. It is opened from the Recruiter's detail (RF-23). From here the reassignment can be triggered (RF-37).

**Documentation:**
- PRD: PRD-RECL-03 Group Leader
- Flow: Recruiter's current workload
- Prototype: (Figma link)

**Flow:**
`My Group → Click on Recruiter (RF-23)` → MANUAL → `Click "View detailed workload"` → AUTOMATICO → `System lists the IN PROGRESS requisitions of that Recruiter with urgency and % of coverage` → MANUAL → `(optional) Reassign a requisition (RF-37)` or `Close`
