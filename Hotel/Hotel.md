---
tags:
  - module/hotel
aliases:
  - Hotel
  - Hotel Module
---

# Hotel

Module that represents the hotel as an Oranje client. The hotel requests staff through [[Requisición|requisitions]] and manages its weekly operations from the [[Core/Módulos/Schedule|Schedule]], which is the hub where demand for positions, coverage of assigned associates, and worked-time records ([[Timesheet]]) converge. It operates as the counterpart to the [[Reclutamiento/Reclutamiento|Reclutamiento]] team.

## Module Contents

### Roles

- [[Hotel/Manager General|Manager General]] — Highest authority at the hotel. Always exists in both hierarchies.
- [[Hotel/Manager de Área|Manager de Área]] — Operational role by department. Approves or rejects requisitions; manages assigned staff.
- [[Hotel/Supervisor|Supervisor]] — Creates staff requisitions.

### Organizational Structure

Depending on the hotel's size and complexity, the platform supports two hierarchical configurations:

#### Simple Hierarchy

For small hotels or those with a flat structure. The General Manager also operates as Area Manager (same person, two roles).

```
General Manager (GM) → SUP → Oranje Associates
```

#### Extended Hierarchy

For large hotels with multiple operational [[Departamentos del Hotel|departments]].

```
General Manager (GM)
  └── Area Manager (one per department)
       └── Supervisor(s)
            └── Oranje Associates
```

#### Role Equivalence

| Simple Hierarchy | Extended Hierarchy | Platform Responsibilities |
|---|---|---|
| [[Hotel/Manager General\|Manager General]] | [[Hotel/Manager General\|Manager General]] | General oversight, global visibility, all operational actions |
| [[Hotel/Manager General\|Manager General]] (same role) | [[Hotel/Manager de Área\|Manager de Área]] | Approves requisitions, manages schedule, generates QR, reports associates |
| [[Hotel/Supervisor\|SUP]] | [[Hotel/Supervisor\|Supervisor]] | Creates requisitions, reports associates, reports workplace accidents |

#### Hotel Departments

- **Housekeeping** — Housekeeper, Houseman, Laundry
- **Food & Beverage** — Chef
- **Maintenance**
- **Front Desk**

See full catalog at [[Departamentos del Hotel]].

### Processes

- Creation and authorization of [[Requisición|requisitions]].
- Management of the weekly [[Core/Módulos/Schedule|Schedule]].
- Recording of worked time via [[Timesheet]].

## Related Core Concepts

- [[Requisición]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Timesheet]]
- [[Semáforo de Requisición]]
- [[Semáforo de Urgencia de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
- [[Semáforo del Colaborador]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Posiciones]]
- [[Departamentos del Hotel]]
- [[Modalidades de Contratación]]
- [[Niveles de Inglés]]
- [[Zonas]]
- [[Inspector]]

## Relationship with Other Modules

- [[Reclutamiento/Reclutamiento|Reclutamiento]] — Receives approved requisitions and assigns staff.
- [[Ventas/Ventas|Ventas]] — Responsible for onboarding new hotels.
- [[Customer Service/Customer Service|Customer Service]] — Post-onboarding service channel for inquiries, complaints, and incident follow-up.
