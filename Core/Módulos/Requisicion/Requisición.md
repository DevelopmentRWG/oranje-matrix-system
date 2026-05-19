---
tags:
  - module/core
aliases:
  - Requisition
  - Requisitions
---

# Requisition

Request that the [[Hotel/Supervisor|Supervisor]] sends to the [[Reclutamiento/Reclutamiento|Recruitment]] team to fill one or more [[Posiciones]]. A requisition consists of **a header** and **one or more requested positions**.

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
| GH (Area Manager)    | [[Hotel/Manager de Área\|Area Manager]] responsible.                                        |
| Recruiter            | [[Reclutadora]] assigned to handle the requisition.                                          |
| Inspector            | [[Inspector]] corresponding to the hotel's [[Zonas\|zone]].                                 |
| Status (color)       | Current status per the [[Semáforo de Requisición]].                                          |

> [!note] About the Inspector in the header
> Each hotel belongs to a [[Zonas|zone]] and each zone has a corresponding [[Inspector]]. For any dispute that occurs, the inspector for the hotel's zone must be aware and follow up — that is why they are recorded in the header.

## Requested Positions

Each requisition can include one or more positions. Each position records:

| Field                    | Description                                                                          |
| ------------------------ | ------------------------------------------------------------------------------------ |
| Requisition number       | Reference to the parent requisition.                                                 |
| Position number          | Identifier for the position within the requisition.                                  |
| Position                 | Type of role requested (see [[Posiciones]]: Housekeeper, Houseman, etc.).            |
| Employment type          | Employment modality (see [[Modalidades de Contratación]]).                           |
| Headcount                | How many associates are needed for this position.                                    |
| Start date               | Date when personnel is required.                                                     |
| Schedule                 | Position schedule.                                                                   |
| Language preference      | Preferred English level. See [[Niveles de Inglés]].                                  |
| Notes                    | Additional hotel clarifications.                                                     |

> [!note] About the end date
> The position has a **start date** but **no defined end date**. The position ends when the [[Hotel/Manager de Área|Area Manager]] or the [[Hotel/Supervisor|Supervisor]] puts the associate on stand-by (**Pink - Stand-by** status in the [[Semáforo del Colaborador]]).

## Urgency Levels

The urgency level is classified according to the [[Semáforo de Urgencia de Requisición]], based on time until the start date.

## Statuses

A requisition has several visual statuses that apply to different dimensions:

- **[[Semáforo de Requisición]]** — general lifecycle status (drafting, authorized, in process, covered).
- **[[Semáforo de Urgencia de Requisición]]** — urgency level based on time.
- **[[Semáforo de Posiciones de la Requisición]]** — coverage percentage for each requested position.

## Flow

See [[Flujo de Requisición]].

## Related

- [[Flujo de Requisición]]
- [[Semáforo de Requisición]]
- [[Semáforo de Urgencia de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
- [[Flujo de Reclutamiento]]
- [[Posiciones]]
- [[Modalidades de Contratación]]
- [[Niveles de Inglés]]
- [[Zonas]]
- [[Inspector]]
- [[Hotel/Manager de Área|Area Manager]]
- [[Hotel/Supervisor|Supervisor]]
- [[Reclutadora]]
- [[Manager de Reclutamiento]]
