---
tags:
  - modulo/core
aliases:
  - Requisition
  - Requisitions
---

# Requisition

Request that the [[Hotel/Supervisor|Supervisor]] sends to the [[Recruitment/Recruitment|Recruitment]] team to cover one or more [[Posiciones|Positions]]. A requisition is composed of **one header** and **one or more requested positions**.

## Structure

A requisition is composed of:

- **Header**: general data of the requisition (hotel, assigned roles, state).
- **Requested positions**: one or more positions, each with its own detail (quantity, date, schedule, etc.).

## Header

General data that identify the requisition:

| Field                | Description                                                                                  |
| -------------------- | -------------------------------------------------------------------------------------------- |
| Requisition number   | Unique identifier of the requisition.                                                      |
| Hotel                | Hotel requesting the staff.                                                              |
| SUP                  | [[Hotel/Supervisor\|Supervisor]] who created the requisition.              |
| GH (Area Manager)    | Responsible [[Hotel/Area Manager\|Area Manager]].                                             |
| Recruiters           | List of [[Recruiter\|participating recruiters]] who work the requisition at the same time (collaborative model). There is no single owner; several recruiters can be active simultaneously. See [[Recruitment/Requisition Self-Pick\|Requisition Self-Pick]] and RR-15. |
| Inspector            | [[Inspector]] corresponding to the hotel's [[Zones\|zone]].                             |
| Status (color)       | Current state according to the [[Requisition Status Light\|Requisition Status Light]].                                          |

> [!note] About the Inspector in the header
> Each hotel belongs to a [[Zones|zone]] and each zone corresponds to an [[Inspector]]. For any dispute that occurs, the inspector of the hotel's zone must be made aware and follow up on it — that is why it is recorded from the header.

## Requested positions

Each requisition can include one or more positions. Each position records:

| Field                    | Description                                                                          |
| ------------------------ | ------------------------------------------------------------------------------------ |
| Requisition number       | Reference to the requisition it belongs to.                                      |
| Position number          | Identifier of the position within the requisition.                               |
| Position                 | Type of job requested (see [[Posiciones|Positions]]: Housekeeper, Houseman, etc.).         |
| Modality                 | Hiring modality (see [[Employment Types|Hiring Modalities]]).                     |
| Number of people         | How many collaborators are needed for this position.                               |
| Start date               | Date on which the staff is required.                                                |
| Schedule                 | Schedule of the position.                                                              |
| Language preference      | Preferred English level. See [[English Levels|English Levels]].                                |
| Notes                    | Additional clarifications from the hotel.                                                  |

> [!note] About the end date
> The position has a **start date** but **no defined end date**. The position ends when the [[Hotel/Area Manager|Area Manager]] or the [[Hotel/Supervisor|Supervisor]] sends the collaborator to rest (**Pink - Stand-by** state in the [[Collaborator Status Light|Collaborator Status Light]]).

## Urgency levels

The urgency level is classified according to the [[Requisition Urgency Status Light|Requisition Urgency Status Light]], based on the time until the start date.

## States

A requisition has several visual states that apply to different dimensions:

- **[[Requisition Status Light|Requisition Status Light]]** — general state of the life cycle (in preparation, authorized, in process, covered).
- **[[Requisition Urgency Status Light|Requisition Urgency Status Light]]** — urgency level based on time.
- **[[Requisition Positions Status Light|Requisition Positions Status Light]]** — coverage percentage for each requested position.

## Requisition History

Each requisition maintains an **immutable chronological timeline** of all the actions that occur on it, with the **actor** (role and name) and **timestamp** of each event. The history records, among others:

- Who **took** the requisition (first recruiter) and who **joined** afterwards as a participating recruiter.
- Who **left** the requisition.
- Who **assigned** or **unassigned** which [[Collaborator Pool\|collaborator]] to which position/slot.
- Status (status-light) changes with their actor.
- Who **closed** the requisition.

The history is **immutable** (not edited or deleted) and is **visible to all participating recruiters, the [[Recruitment/Recruiters Group Leader|Group Leader]] and the [[Recruitment Manager|Recruitment Manager]]**. It is the source of traceability for collaborative work. See RF-41 and RR-16.

## Flow

See [[Requisition Flow|Requisition Flow]].

## Related

- [[Requisition Flow|Requisition Flow]]
- [[Requisition Status Light|Requisition Status Light]]
- [[Requisition Urgency Status Light|Requisition Urgency Status Light]]
- [[Requisition Positions Status Light|Requisition Positions Status Light]]
- [[Recruitment Flow|Recruitment Flow]]
- [[Posiciones|Positions]]
- [[Employment Types|Hiring Modalities]]
- [[English Levels|English Levels]]
- [[Zones|Zones]]
- [[Inspector]]
- [[Hotel/Area Manager|Area Manager]]
- [[Hotel/Supervisor|Supervisor]]
- [[Recruiter|Recruiter]]
- [[Recruitment/Recruiters Group Leader|Recruiters Group Leader]]
- [[Recruitment Manager|Recruitment Manager]]
- [[Recruitment/Requisition Self-Pick|Requisition Self-Pick]]
- [[Collaborator Pool|Collaborator Pool]]
