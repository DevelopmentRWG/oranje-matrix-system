---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-05 (Group Leader)
---

# 🪪 ID: RF-05
🏷️ **Name:** Approve group coverage closure

**Story:**
When a Recruiter in the group marks a requisition as covered (all positions at 100%), the system leaves the requisition in **Pending approval** status and notifies the Group Leader. The Group Leader reviews that the coverage is real (verifies positions, assigned collaborators, Schedule data) and approves or rejects the closure. Only after the Group Leader's approval does the requisition move to Light Blue status light (Covered and closed).

**Acceptance criteria:**
Approval of the closure is exclusive to the Group Leader (updated rule — the Manager does NOT approve). The Group Leader can only approve requisitions taken by Recruiters in their group. The approval requires an optional comment. If rejected, the requisition returns to "In progress" status (Yellow) with a reason. The approval / rejection is kept in an auditable log. Notifies the Recruiter.

**Documentation:**
- PRD: PRD-RECL-02 Líder de Grupo
- Flow: Group closure approval
- Prototype: (Figma link)

**Flow:**
`"Pending approval" inbox` → MANUAL → `Selects requisition marked as covered` → `Verifies coverage (positions / assigned collaborators / Schedule)` → MANUAL → `Click "Approve closure" or "Reject"` → If Approves → `Optional comment` → AUTOMATICO → `Status light to Light Blue (Covered) + Notifies Recruiter + Closure log` / If Rejects → `Mandatory reason` → AUTOMATICO → `Returns to Yellow (In progress) + Notifies Recruiter + Log`
