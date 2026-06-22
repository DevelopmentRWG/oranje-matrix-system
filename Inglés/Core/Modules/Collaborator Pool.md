---
tags:
  - modulo/core
aliases:
  - Collaborator Pool
  - Pool
---

# Collaborator Pool

Pool where [[Recruitment/Recruitment|Recruitment]] sends all the recruits that passed the filter and were approved. It is the place where the information of approved collaborators is organized, and from which [[Recruiter|recruiters]] can take candidates to assign them to a hotel.

> [!info] Meeting point between flows
> The pool is the meeting point between the [[Recruitment Flow|Recruitment Flow]] (which **feeds** it with new collaborators) and the [[Requisition Flow|Requisition Flow]] (which **consumes** it to cover hotels).

## What it contains

- Only the recruits that **passed the filter and were approved** by [[Recruitment/Recruitment|Recruitment]] enter.
- It contains the **collaborator's record**.

## Dynamics

- The **collaborator's record stays stored** in the pool.
- What **keeps changing is their status**, which corresponds to their state in the [[Collaborator Status Light|Collaborator Status Light]].
- The status is **dynamic**.

## Use by Recruitment

- [[Recruiter|Recruiters]] take collaborators from the pool to assign them to a hotel when there is a match with a [[Requisition|Requisition]].

## Search and filters

The [[Recruiter|Recruiter]] can filter collaborators in the pool by combining the following criteria:

| Filter | Description |
|---|---|
| Position | Housekeeper, Houseman, etc. Allows finding collaborators with the profile the requisition requires |
| Zone | Geographic zone of the collaborator. Eases assignment to nearby hotels |
| Language | Language preference of the collaborator |
| Employment type | Temporary or Permanent |
| Availability | Current state of the [[Collaborator Status Light|Collaborator Status Light]]: only collaborators in an available state are candidates for assignment |

> [!info] The availability filter is based directly on the [[Collaborator Status Light|Collaborator Status Light]] state of each record in the pool.

## Related

- [[Collaborator Status Light|Collaborator Status Light]]
- [[Recruiter|Recruiter]]
- [[Recruitment Flow|Recruitment Flow]]
- [[Requisition Flow|Requisition Flow]]
- [[Requisition|Requisition]]
