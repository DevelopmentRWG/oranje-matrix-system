---
tags:
  - propuesta
  - modulo/reclutamiento
aliases:
  - Self-Pick
  - Requisition Self-Pick
status: aprobada
---

# Requisition Self-Pick

Requisition assignment model in the [[Recruitment/Recruitment|Recruitment]] module. The [[Recruiter|Recruiters]] and [[Recruitment/Recruiters Group Leader|Group Leaders]] freely take requisitions from a shared inbox, without intermediation from the [[Recruitment Manager|Recruitment Manager]].

## Flow

```
Area Manager authorizes requisition
      ↓
Arrives at the system and stays in the "Authorized" queue (visible to all of Recruitment)
      ↓
The queue is automatically prioritized by the Requisition Urgency Status Light
      ↓
Recruiters and Group Leaders freely take the requisitions
      ↓
On taking, the requisition moves to Yellow (In process) in the Requisition Status Light
      ↓
Are there already recruiters working it? → another recruiter can JOIN
(added as a participating recruiter; does NOT lock, does NOT displace, does NOT reset)
      ↓
Several participating recruiters cover it with collaborators from the Pool
(shared progress; lock only at position/slot level)
      ↓
Each recruiter can LEAVE; the requisition stays Yellow if others remain,
and returns to Authorized only when the LAST recruiter leaves
```

## Operational rules

- **No limit on simultaneous requisitions** — each Recruiter handles all those that come to them according to demand.
- **No restrictions by zone or language** — Recruiters receive candidates from everywhere and assign them according to the [[Core/Modules/Business Rules|Business Rules]].
- **Global inbox with filters** — all Recruiters see all available requisitions. They can filter by zone, urgency, position and other criteria, but the inbox is not segmented by group or by Recruiter.
- **Collaborative model (RR-15)** — a requisition can have **several participating recruiters** working it at the same time; there is no single owner. Taking a requisition that is **already taken does NOT transfer or lock it**: the recruiter **joins** ("Join" action) as an additional participant, without displacing the existing ones or rolling back the status light. No one "loses" the requisition.
- **Leave (not release)** — a participating recruiter can **leave** ("Leave" action); only they are removed. The requisition stays **Yellow** (In process) if other recruiters remain and **what others have already assigned is not reset**; it only returns to **Authorized** when the **last** recruiter leaves.
- **Lock only at position/slot level** — coverage progress is **shared** among all participating recruiters. The concurrency lock operates at the **position/slot** level, not the whole requisition: if two recruiters assign the same position, the **first wins** and the second sees "position already covered". Two recruiters do not assign the same [[Collaborator Pool|collaborator]] to the same position.
- **Auto-assignment at 24 hours** — if a requisition has gone more than 24 hours without being taken (counted from authorization), the system automatically assigns it to the Recruiter with the lowest load of active requisitions at that moment (they become the initial participating recruiter). The [[Recruitment Manager|Recruitment Manager]] receives no notification; the process is transparent.

## Manager intervention

The [[Recruitment Manager|Recruitment Manager]] only intervenes in exceptional cases:

- Balancing between groups
- Absent leader
- Correction of an assignment error

## Escalation to the Group Leader

When the [[Recruiter|Recruiter]] does not find a match in the [[Collaborator Pool|Collaborator Pool]] and has actively searched outside the system (social media, external groups, etc.), an escalation timeout toward the [[Recruitment/Recruiters Group Leader|Group Leader]] applies. The deadline depends on the state of the [[Core/Modules/Status Lights/Requisition Urgency Status Light|Requisition Urgency Status Light]]:

| Urgency color | Condition | Deadline to escalate |
|---|---|---|
| Red | Less than 72h to start | 24h without covering |
| Yellow | Between 72h and 120h to start | 48h without covering |
| Strong Green | More than 120h to start | 72h without covering |

> [!important] Throughout this entire process the requisition remains in **Yellow** state in the [[Core/Modules/Status Lights/Requisition Status Light|Requisition Status Light]]. The escalation goes to the [[Recruitment/Recruiters Group Leader|Group Leader]], not to the [[Recruitment Manager|Recruitment Manager]].

## Requisition history

Each requisition maintains an **immutable chronological timeline** with **actor** (role and name) and timestamp of each action (RR-16):

- Who **took** it and who **joined** afterward as a participating recruiter.
- Who **left** the requisition.
- Who **assigned** or **unassigned** which [[Collaborator Pool|collaborator]] to which position/slot.
- Status changes and who **closed** it.

The history is **visible to all participating recruiters, the [[Recruitment/Recruiters Group Leader|Group Leader]] and the [[Recruitment Manager|Recruitment Manager]]**. It gives full traceability of the collaborative work without any recruiter losing their contribution. See RF-41.

## Updated documents

The following vault files reflect this model:

- [[Recruitment/Recruitment Rules|Recruitment Rules]] — section "Requisitions — intake and assignment (Self-Pick)"
- [[Core/Modules/Business Rules|Business Rules]] — sections "Requisition distribution" and "Assignment"
- [[Core/Modules/Status Lights/Requisition Status Light|Requisition Status Light]] — Green → Yellow trigger
- [[Core/Modules/Requisition/Requisition Flow|Requisition Flow]] — section 5
- [[Recruiter|Recruiter]] — first responsibility
- [[Recruitment Manager|Recruitment Manager]] — responsibilities

## Related

- [[Recruitment/Recruitment Rules|Recruitment Rules]]
- [[Core/Modules/Business Rules|Business Rules]]
- [[Core/Modules/Status Lights/Requisition Urgency Status Light|Requisition Urgency Status Light]]
- [[Core/Modules/Status Lights/Requisition Status Light|Requisition Status Light]]
- [[Recruitment Manager|Recruitment Manager]]
- [[Recruitment/Recruiters Group Leader|Recruiters Group Leader]]
- [[Recruiter|Recruiter]]
- [[Collaborator Pool|Collaborator Pool]]
- [[Core/Modules/Requisition/Requisition|Requisition]]
