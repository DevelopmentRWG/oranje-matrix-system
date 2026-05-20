---
tags:
  - module/core
aliases:
  - Requisition
  - Requisitions
---

# Requisition

Request that the [[Hotel/Supervisor|Supervisor]] sends to the [[Recruitment/Recruitment|Recruitment]] team to fill one or more [[Positions]]. A requisition consists of **a header** and **one or more requested positions**.

## Structure

A requisition consists of:

- **Header**: general requisition data (hotel, assigned roles, status).
- **Requested positions**: one or more positions, each with its own detail (headcount, date, schedule, etc.).

## Header

General data that identifies the requisition:

| Field                | Description                                                                                  |
| -------------------- | -------------------------------------------------------------------------------------------- |
| Requisition number   | Unique identifier for the requisition.                                                       |
| Hotel                | Hotel requesting personnel.                                                                  |
| SUP                  | [[Hotel/Supervisor\|Supervisor]] who created the requisition.                                |
| GH (Area Manager)    | [[Hotel/Area Manager\|Area Manager]] responsible.                                        |
| Recruiter            | [[Recruiter]] assigned to handle the requisition.                                          |
| Inspector            | [[Inspector]] corresponding to the hotel's [[Zones\|zone]].                                 |
| Status (color)       | Current status per the [[Requisition Status Indicator]].                                          |

> [!note] About the Inspector in the header
> Each hotel belongs to a [[Zones|zone]] and each zone has a corresponding [[Inspector]]. For any dispute that occurs, the inspector for the hotel's zone must be aware and follow up — that is why they are recorded in the header.

## Requested Positions

Each requisition can include one or more positions. Each position records:

| Field                    | Description                                                                          |
| ------------------------ | ------------------------------------------------------------------------------------ |
| Requisition number       | Reference to the parent requisition.                                                 |
| Position number          | Identifier for the position within the requisition.                                  |
| Position                 | Type of role requested (see [[Positions]]: Housekeeper, Houseman, etc.).            |
| Employment type          | Employment modality (see [[Employment Types]]).                           |
| Headcount                | How many associates are needed for this position.                                    |
| Start date               | Date when personnel is required.                                                     |
| Schedule                 | Position schedule.                                                                   |
| Language preference      | Preferred English level. See [[English Levels]].                                  |
| Notes                    | Additional hotel clarifications.                                                     |

> [!note] About the end date
> The position has a **start date** but **no defined end date**. The position ends when the [[Hotel/Area Manager|Area Manager]] or the [[Hotel/Supervisor|Supervisor]] puts the associate on stand-by (**Pink - Stand-by** status in the [[Associate Status Indicator]]).

## Urgency Levels

The urgency level is classified according to the [[Requisition Urgency Indicator]], based on time until the start date.

## Statuses

A requisition has several visual statuses that apply to different dimensions:

- **[[Requisition Status Indicator]]** — general lifecycle status (drafting, authorized, in process, covered).
- **[[Requisition Urgency Indicator]]** — urgency level based on time.
- **[[Requisition Position Indicator]]** — coverage percentage for each requested position.

## Flow

See [[Requisition Flow]].

## Related

- [[Requisition Flow]]
- [[Requisition Status Indicator]]
- [[Requisition Urgency Indicator]]
- [[Requisition Position Indicator]]
- [[Recruitment Flow]]
- [[Positions]]
- [[Employment Types]]
- [[English Levels]]
- [[Zones]]
- [[Inspector]]
- [[Hotel/Area Manager|Area Manager]]
- [[Hotel/Supervisor|Supervisor]]
- [[Recruiter]]
- [[Recruitment Manager]]
