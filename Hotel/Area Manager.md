---
tags:
  - module/hotel
aliases:
  - Area Manager
  - Department Manager
  - GH
---

# Area Manager

Operational role in the [[Hotel/Hotel|Hotel]] module. Responsible for approving or rejecting [[Requisition|requisitions]], managing assigned associates, and administering the [[Core/Modules/Schedule|Schedule]] for their department.

> [!note] Simple Hierarchy
> In hotels with a simple hierarchy, the [[Hotel/General Manager|General Manager]] also operates as Area Manager (same person, two roles). In hotels with an extended hierarchy, there is one Area Manager per [[Hotel Departments|department]] (Housekeeping, Food & Beverage, Maintenance, Front Desk), subordinate to the [[Hotel/General Manager|General Manager]].

## Responsibilities

### Requisitions

- Creates staff [[Requisition|requisitions]].
- **Approves** the requisition (status **Authorized**), making it available in the [[Recruitment/Recruitment|Recruitment]] shared inbox to be taken by a [[Recruiter]] or [[Recruitment/Recruiter Team Lead|Team Lead]] ([[Requisition Self-Pick|Self-Pick]] model).
- **Rejects** the requisition, returning it to the creator with comments (status **In Progress**).

> [!important] Security Layer
> This approval is a security layer to prevent false or incorrect requisitions from reaching the [[Recruitment/Recruitment|Recruitment]] team. Oranje only receives requisitions that an Area Manager or the [[Hotel/General Manager|General Manager]] has validated.

### Assigned Staff Management

- Generates the **QR** code for associates to punch in the [[Timesheet]].
- Places associates on rest (status **Pink — Stand-by** in the [[Associate Status Indicator]]).
- Reports associates (status **Red — Reported** in the [[Associate Status Indicator]]).
- Reports [[Core/Modules/Work Accident/Work Accident|workplace accidents]] detected on the property.
- Manages the weekly [[Core/Modules/Schedule|Schedule]] for their department.

## Related

- [[Hotel/General Manager|General Manager]]
- [[Hotel/Supervisor|Supervisor]]
- [[Hotel/Hotel|Hotel]]
- [[Hotel Departments]]
- [[Requisition]]
- [[Timesheet]]
- [[Core/Modules/Schedule|Schedule]]
- [[Requisition Status Indicator]]
- [[Associate Status Indicator]]
- [[Inspector]]
