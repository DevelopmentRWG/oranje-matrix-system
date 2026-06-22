---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-37
---

# 🪪 ID: RF-37
🏷️ **Name:** Reassign requisition to another Recruiter

**Story:**
When a Recruiter is overloaded, absent (on vacation) or a case requires another zone/profile, the Leader **reassigns one of her in-progress requisitions to another Recruiter in the group**. He chooses the requisition, the target Recruiter and the reason; the system transfers the requisition and notifies both.

**Acceptance criteria:**
Reassignment happens only **between Recruiters of the Leader's own group** (rule RR-10). It only applies to requisitions **in progress** (not closed). The **reason is mandatory** (workload balancing / Recruiter absent / specialization by zone / other). On confirmation, the requisition moves to "My Requisitions" of the target Recruiter, **the source and target Recruiters are notified**, and it is recorded in an auditable log.

> [!note]
> Different from **RF-17 (Reassign collaborator)**, which moves a **collaborator** between hotels. Here a **requisition** (the work of covering it) is reassigned between Recruiters.

**Documentation:**
- PRD: PRD-RECL-03 Group Leader
- Flow: Requisition reassignment between Recruiters
- Prototype: (Figma link)

**Flow:**
`My Group → Recruiter detail` (or from "View detailed workload", RF-36) → MANUAL → `Click "Reassign requisition"` → `Select requisition in progress + target Recruiter + reason` → `Confirm` → AUTOMATICO → `Transfers the requisition to the target Recruiter + Notifies source and target + Records in log`
