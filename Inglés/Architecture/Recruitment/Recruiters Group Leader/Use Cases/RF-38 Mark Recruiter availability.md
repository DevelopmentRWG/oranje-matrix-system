---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-38
---

# 🪪 ID: RF-38
🏷️ **Name:** Mark availability of the Recruiter

**Story:**
The Leader marks a Recruiter in his group as **on vacation** (or **back / available**) from her detail card. While on vacation, the Recruiter **does not receive reassignments** and her status is reflected in the group list and in the Leader's KPIs.

**Acceptance criteria:**
Only applies to Recruiters of the Leader's own group (rule RR-10). It is an **Active ↔ Vacation toggle**. The change is reflected in the **list** (Status column) and in the group's **KPIs** (active Recruiters / on vacation). It is recorded in the log.

> [!note]
> It is not equivalent to a **deactivation** from the system: creating/editing/permanently removing department users is exclusive to the Manager (RF-29). This only marks temporary operational availability.

**Documentation:**
- PRD: PRD-RECL-03 Group Leader
- Flow: Recruiter availability
- Prototype: (Figma link)

**Flow:**
`My Group → Click on Recruiter` → MANUAL → `Click "Mark vacation" / "Mark available"` → AUTOMATICO → `Changes the Recruiter's status + Updates the group list and KPIs + Records in log`
