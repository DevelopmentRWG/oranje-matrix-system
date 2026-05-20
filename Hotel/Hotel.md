---
tags:
  - module/hotel
aliases:
  - Hotel
  - Hotel Module
---

# Hotel

Module that represents the hotel as an Oranje client. The hotel requests staff through [[Requisition|requisitions]] and manages its weekly operations from the [[Core/Modules/Schedule|Schedule]], which is the hub where demand for positions, coverage of assigned associates, and worked-time records ([[Timesheet]]) converge. It operates as the counterpart to the [[Recruitment/Recruitment|Recruitment]] team.

## Module Contents

### Roles

- [[Hotel/General Manager|General Manager]] — Highest authority at the hotel. Always exists in both hierarchies.
- [[Hotel/Area Manager|Area Manager]] — Operational role by department. Approves or rejects requisitions; manages assigned staff.
- [[Hotel/Supervisor|Supervisor]] — Creates staff requisitions.

### Organizational Structure

Depending on the hotel's size and complexity, the platform supports two hierarchical configurations:

#### Simple Hierarchy

For small hotels or those with a flat structure. The General Manager also operates as Area Manager (same person, two roles).

```
General Manager (GM) → SUP → Oranje Associates
```

#### Extended Hierarchy

For large hotels with multiple operational [[Hotel Departments|departments]].

```
General Manager (GM)
  └── Area Manager (one per department)
       └── Supervisor(s)
            └── Oranje Associates
```

#### Role Equivalence

| Simple Hierarchy | Extended Hierarchy | Platform Responsibilities |
|---|---|---|
| [[Hotel/General Manager\|General Manager]] | [[Hotel/General Manager\|General Manager]] | General oversight, global visibility, all operational actions |
| [[Hotel/General Manager\|General Manager]] (same role) | [[Hotel/Area Manager\|Area Manager]] | Approves requisitions, manages schedule, generates QR, reports associates |
| [[Hotel/Supervisor\|SUP]] | [[Hotel/Supervisor\|Supervisor]] | Creates requisitions, reports associates, reports workplace accidents |

#### Hotel Departments

- **Housekeeping** — Housekeeper, Houseman, Laundry
- **Food & Beverage** — Chef
- **Maintenance**
- **Front Desk**

See full catalog at [[Hotel Departments]].

### Processes

- Creation and authorization of [[Requisition|requisitions]].
- Management of the weekly [[Core/Modules/Schedule|Schedule]].
- Recording of worked time via [[Timesheet]].

## Related Core Concepts

- [[Requisition]]
- [[Core/Modules/Schedule|Schedule]]
- [[Timesheet]]
- [[Requisition Status Indicator]]
- [[Requisition Urgency Indicator]]
- [[Requisition Position Indicator]]
- [[Associate Status Indicator]]
- [[Core/Modules/Blacklist|Blacklist]]
- [[Positions]]
- [[Hotel Departments]]
- [[Employment Types]]
- [[English Levels]]
- [[Zones]]
- [[Inspector]]

## Relationship with Other Modules

- [[Recruitment/Recruitment|Recruitment]] — Receives approved requisitions and assigns staff.
- [[Sales/Sales|Sales]] — Responsible for onboarding new hotels.
- [[Customer Service/Customer Service|Customer Service]] — Post-onboarding service channel for inquiries, complaints, and incident follow-up.
