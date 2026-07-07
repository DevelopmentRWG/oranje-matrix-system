---
tags:
  - architecture
  - department/inspection
  - use-case
aliases:
  - UC RF-13
  - Resolve dispute Inspector
---

# ID: RF-13
**Name:** Resolve collaborator dispute

**Primary actor:** [[Inspector]]

**Story:**
When a hotel reports a collaborator (status **Red** in the [[Semáforo del Colaborador|Collaborator Status Light]]), the zone Inspector investigates the case. The investigation can confirm the offense (permanent Blacklist ban) or clear the collaborator (reinstatement). Decision authority is exclusive to the Inspector; it does not escalate to the [[Manager de Reclutamiento|Recruitment Manager]].

> [!info]
> The Red status is activated by the hotel's [[Hotel/Manager General|General Manager]], [[Hotel/Manager de Área|Area Manager]], or [[Hotel/Supervisor|Supervisor]]. The 3-absence rule does NOT go through Red: it goes directly to Black automatically (without Inspector involvement). Only manual hotel reports generate the Red status that triggers this flow.

**Preconditions:**
- The collaborator is in **Red** status in the [[Semáforo del Colaborador|Collaborator Status Light]].
- The Inspector is assigned to the geographic zone of the affected hotel.
- If the zone's assigned Inspector is unavailable, the [[Inspección/Coordinador|Coordinator]] temporarily reassigns another Inspector.

**Postconditions:**
- The collaborator transitions to **Black** ([[Core/Módulos/Blacklist|Blacklist]]) — permanent ban — if the dispute is resolved in the hotel's favor.
- The collaborator transitions to **Strong Green** (reinstated to the pool) if the dispute is resolved in their favor.
- The outcome is recorded in the system log with the actor, date, and resolution.

> [!info]
> Once the collaborator reaches **Black** status, the ban is permanent: there is no removal or rehabilitation. The transition Black → any other status does not exist in the system.

**Flow:**

`Red status notification` → AUTOMATIC → `System notifies the assigned zone Inspector` → MANUAL → `Inspector accesses the collaborator's case` → `Reviews collaborator history, hotel evidence, and report context` → MANUAL → `Inspector issues verdict`

Branch A — In the hotel's favor:
`Verdict: Blacklist` → MANUAL → `Inspector records outcome with mandatory reason` → AUTOMATIC → `System transitions collaborator Red → Black` → `Collaborator is permanently banned` → `System notifies involved parties (hotel, responsible Recruiter)` → `Recorded in auditable log`

Branch B — In the collaborator's favor:
`Verdict: Reinstatement` → MANUAL → `Inspector records outcome with mandatory reason` → AUTOMATIC → `System transitions collaborator Red → Strong Green` → `Collaborator is available in the pool for new assignment` → `System notifies involved parties (hotel, responsible Recruiter)` → `Recorded in auditable log`

**Validations:**
- Only the Inspector assigned to the hotel's zone can issue the verdict (or the temporary Inspector designated by the Coordinator).
- Reason/justification is mandatory in both branches.
- The system blocks the transition if the collaborator is no longer in Red status at the time of verdict entry.

> [!info]
> The exact fields of the resolution form (what evidence the Inspector captures, whether a "days investigated" field exists, etc.) are not defined in the current source. This detail is pending specification.

**Acceptance criteria:**
- Only the zone Inspector (or a temporary substitute authorized by the Coordinator) can execute the resolution.
- Justification is mandatory in both decision branches.
- The status change (Red → Black or Red → Strong Green) is recorded in the log with actor, date, and reason.
- Involved parties (hotel, Recruiter) receive a notification of the outcome.
- Resulting Blacklist cases are reviewed by the [[Manager de Reclutamiento|Recruitment Manager]] (for tracking context, not as a decision authority).

**Documentation:**
- Source: [[Inspector]] · [[Inspección/Reglas de Inspección|Inspection Rules]]
- Status light: [[Semáforo del Colaborador|Collaborator Status Light]]
- Module: [[Core/Módulos/Blacklist|Blacklist]]

## Related

- [[Inspector]]
- [[Semáforo del Colaborador|Collaborator Status Light]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Inspección/Reglas de Inspección|Inspection Rules]]
- [[Hotel/Manager de Área|Area Manager]]
- [[Hotel/Manager General|General Manager]]
- [[Hotel/Supervisor|Supervisor]]
- [[Manager de Reclutamiento|Recruitment Manager]]
- [[00 - Inspector Architecture]]
