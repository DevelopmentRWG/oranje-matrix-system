---
tags:
  - module/core
aliases:
  - Associate Pool
  - Pool
---

# Associate Pool

A pool where [[Reclutamiento/Reclutamiento|Recruitment]] sends all recruits that passed the screening and were approved. It is where approved associates' information is organized, and from which [[Reclutadora|recruiters]] can pick candidates to assign them to a hotel.

> [!info] Meeting point between flows
> The pool is the meeting point between the [[Flujo de Reclutamiento]] (which **feeds** it with new associates) and the [[Flujo de Requisición]] (which **consumes** it to fill hotel positions).

## What It Contains

- Only recruits that **passed the screening and were approved** by [[Reclutamiento/Reclutamiento|Recruitment]] enter the pool.
- Contains the **associate's record**.

## Dynamics

- The **associate's record stays** in the pool.
- What **changes is their status**, which corresponds to their state in the [[Semáforo del Colaborador]].
- The status is **dynamic**.

## Use by Recruitment

- [[Reclutadora|Recruiters]] pick associates from the pool to assign them to a hotel when there is a match with a [[Requisición]].

## Search and Filters

The [[Reclutadora]] can filter associates in the pool by combining the following criteria:

| Filter | Description |
|---|---|
| Position | Housekeeper, Houseman, etc. Finds associates matching the position the requisition requires |
| Zone | Associate's geographic zone. Facilitates assignment to nearby hotels |
| Language | Associate's language preference |
| Employment type | Temporary or Permanent |
| Availability | Current [[Semáforo del Colaborador]] status: only associates in an available state are candidates for assignment |

> [!info] The availability filter is based directly on each record's [[Semáforo del Colaborador]] status in the pool.

## Related

- [[Semáforo del Colaborador]]
- [[Reclutadora]]
- [[Flujo de Reclutamiento]]
- [[Flujo de Requisición]]
- [[Requisición]]
