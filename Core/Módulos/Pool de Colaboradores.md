---
tags:
  - module/core
aliases:
  - Associate Pool
  - Pool
---

# Associate Pool

A pool where [[Recruitment/Recruitment|Recruitment]] sends all recruits that passed the screening and were approved. It is where approved associates' information is organized, and from which [[Recruiter|recruiters]] can pick candidates to assign them to a hotel.

> [!info] Meeting point between flows
> The pool is the meeting point between the [[Recruitment Flow]] (which **feeds** it with new associates) and the [[Requisition Flow]] (which **consumes** it to fill hotel positions).

## What It Contains

- Only recruits that **passed the screening and were approved** by [[Recruitment/Recruitment|Recruitment]] enter the pool.
- Contains the **associate's record**.

## Dynamics

- The **associate's record stays** in the pool.
- What **changes is their status**, which corresponds to their state in the [[Associate Status Indicator]].
- The status is **dynamic**.

## Use by Recruitment

- [[Recruiter|Recruiters]] pick associates from the pool to assign them to a hotel when there is a match with a [[Requisition]].

## Search and Filters

The [[Recruiter]] can filter associates in the pool by combining the following criteria:

| Filter | Description |
|---|---|
| Position | Housekeeper, Houseman, etc. Finds associates matching the position the requisition requires |
| Zone | Associate's geographic zone. Facilitates assignment to nearby hotels |
| Language | Associate's language preference |
| Employment type | Temporary or Permanent |
| Availability | Current [[Associate Status Indicator]] status: only associates in an available state are candidates for assignment |

> [!info] The availability filter is based directly on each record's [[Associate Status Indicator]] status in the pool.

## Related

- [[Associate Status Indicator]]
- [[Recruiter]]
- [[Recruitment Flow]]
- [[Requisition Flow]]
- [[Requisition]]
