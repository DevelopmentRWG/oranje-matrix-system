---
tags:
  - modulo/hotel
aliases:
  - Area Manager
  - Department Manager
  - GH
---

# Area Manager

Operational role of the [[Hotel/Hotel|Hotel]] module. Responsible for approving or rejecting [[Requisition|requisitions]], managing the assigned collaborators and administering the [[Core/Modules/Schedule|Schedule]] of its department.

> [!note] Simple hierarchy
> In hotels with a simple hierarchy, the [[Hotel/General Manager|General Manager]] also operates as Area Manager (same person, two roles). In hotels with an extended hierarchy, there is one Area Manager for each [[Hotel Departments|department]] (Housekeeping, Food, Maintenance, Front Desk), subordinate to the [[Hotel/General Manager|General Manager]].

## Responsibilities

### Requisitions

- Creates staffing [[Requisition|requisitions]].
- **Approves** the requisition (**Authorized** status), which becomes available in the shared inbox of [[Recruitment/Recruitment|Recruitment]] to be taken by a [[Recruiter|Recruiter]] or [[Recruitment/Recruiters Group Leader|Group Leader]] (the [[Requisition Self-Pick|Self-Pick]] model).
- **Rejects** the requisition, returning it to the creator with observations (**In progress** status).

> [!important] Security layer
> This approval is a security layer to prevent false or incorrect requisitions from reaching the [[Recruitment/Recruitment|Recruitment]] team. Oranje only receives requisitions that an Area Manager or the [[Hotel/General Manager|General Manager]] has validated.

### Management of assigned staff

- Generates the **QR** code so that collaborators can clock in on the [[Timesheet]].
- Sends collaborators to rest (**Pink — Stand-by** status in the [[Collaborator Status Light|Collaborator Status Light]]).
- Reports collaborators (**Red — Reported** status in the [[Collaborator Status Light|Collaborator Status Light]]).
- Reports [[Core/Modules/Workplace Accident/Workplace Accident|workplace accidents]] detected on the property.
- Manages the weekly [[Core/Modules/Schedule|Schedule]] of its department.

## Related

- [[Hotel/General Manager|General Manager]]
- [[Hotel/Supervisor|Supervisor]]
- [[Hotel/Hotel|Hotel]]
- [[Hotel Departments|Hotel Departments]]
- [[Requisition|Requisition]]
- [[Timesheet]]
- [[Core/Modules/Schedule|Schedule]]
- [[Requisition Status Light|Requisition Status Light]]
- [[Collaborator Status Light|Collaborator Status Light]]
- [[Inspector]]
