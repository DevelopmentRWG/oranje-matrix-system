---
tags:
  - modulo/hotel
aliases:
  - Hotel
  - Hotel Module
---

# Hotel

Module that represents the hotel as a client of Oranje. The hotel requests staff through [[Requisition|requisitions]] and manages its weekly operation from the [[Core/Modules/Schedule|Schedule]], which is the axis where the demand for positions, the coverage of assigned collaborators and the record of worked time ([[Timesheet]]) converge. It operates as the counterpart of the [[Recruitment/Recruitment|Recruitment]] team.

## Module contents

### Roles

- [[Hotel/General Manager|General Manager]] — Highest authority of the hotel. Always exists in both hierarchies.
- [[Hotel/Area Manager|Area Manager]] — Operational role per department. Approves or rejects requisitions; manages assigned staff.
- [[Hotel/Supervisor|Supervisor]] — Creates the staffing requisitions.

### Organizational structure

Depending on the size and complexity of the hotel, the platform supports two hierarchical configurations:

#### Simple hierarchy

For small hotels or those with a flat structure. The General Manager also operates as Area Manager (same person, two roles).

```
General Manager (GM) → SUP → Oranje Collaborators
```

#### Extended hierarchy

For large hotels with multiple operational [[Hotel Departments|departments]].

```
General Manager (GM)
  └── Area Manager (one per department)
       └── Supervisor(s)
            └── Oranje Collaborators
```

#### Role equivalence

| Simple hierarchy | Extended hierarchy | Platform responsibilities |
|---|---|---|
| [[Hotel/General Manager\|General Manager]] | [[Hotel/General Manager\|General Manager]] | General supervision, global visibility, all operational actions |
| [[Hotel/General Manager\|General Manager]] (same role) | [[Hotel/Area Manager\|Area Manager]] | Approves requisitions, manages schedule, generates QR, reports collaborators |
| [[Hotel/Supervisor\|SUP]] | [[Hotel/Supervisor\|Supervisor]] | Creates requisitions, reports collaborators, reports workplace accidents |

#### Hotel departments

- **Housekeeping** — Housekeeper, Houseman, Laundry
- **Food** — Chef
- **Maintenance**
- **Front Desk**

See the full catalog in [[Hotel Departments|Hotel Departments]].

### Processes

- Creation and authorization of [[Requisition|requisitions]].
- Management of the weekly [[Core/Modules/Schedule|Schedule]].
- Record of worked time via [[Timesheet]].

## Related Core Concepts

- [[Requisition|Requisition]]
- [[Core/Modules/Schedule|Schedule]]
- [[Timesheet]]
- [[Requisition Status Light|Requisition Status Light]]
- [[Requisition Urgency Status Light|Requisition Urgency Status Light]]
- [[Requisition Positions Status Light|Requisition Positions Status Light]]
- [[Collaborator Status Light|Collaborator Status Light]]
- [[Core/Modules/Blacklist|Blacklist]]
- [[Posiciones|Positions]]
- [[Hotel Departments|Hotel Departments]]
- [[Employment Types|Hiring Modalities]]
- [[English Levels|English Levels]]
- [[Zones|Zones]]
- [[Inspector]]

## Relationship with other modules

- [[Recruitment/Recruitment|Recruitment]] — Receives the approved requisitions and assigns staff.
- [[Sales/Sales|Sales]] — Responsible for the onboarding of new hotels.
- [[Customer Service/Customer Service|Customer Service]] — Post-onboarding support channel for inquiries, complaints and follow-up of incidents.
