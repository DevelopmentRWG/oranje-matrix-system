---
tags:
  - module/hotel
aliases:
  - Area Manager
  - Department Manager
  - GH
---

# Area Manager

Operational role in the [[Hotel/Hotel|Hotel]] module. Responsible for approving or rejecting [[Requisición|requisitions]], managing assigned associates, and administering the [[Core/Módulos/Schedule|Schedule]] for their department.

> [!note] Simple Hierarchy
> In hotels with a simple hierarchy, the [[Hotel/Manager General|Manager General]] also operates as Area Manager (same person, two roles). In hotels with an extended hierarchy, there is one Area Manager per [[Departamentos del Hotel|department]] (Housekeeping, Food & Beverage, Maintenance, Front Desk), subordinate to the [[Hotel/Manager General|Manager General]].

## Responsibilities

### Requisitions

- Creates staff [[Requisición|requisitions]].
- **Approves** the requisition (status **Authorized**), making it available in the [[Reclutamiento/Reclutamiento|Reclutamiento]] shared inbox to be taken by a [[Reclutadora]] or [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo]] ([[Self-Pick de Requisiciones|Self-Pick]] model).
- **Rejects** the requisition, returning it to the creator with comments (status **In Progress**).

> [!important] Security Layer
> This approval is a security layer to prevent false or incorrect requisitions from reaching the [[Reclutamiento/Reclutamiento|Reclutamiento]] team. Oranje only receives requisitions that an Area Manager or the [[Hotel/Manager General|Manager General]] has validated.

### Assigned Staff Management

- Generates the **QR** code for associates to punch in the [[Timesheet]].
- Places associates on rest (status **Pink — Stand-by** in the [[Semáforo del Colaborador]]).
- Reports associates (status **Red — Reported** in the [[Semáforo del Colaborador]]).
- Reports [[Core/Módulos/Accidente Laboral/Accidente Laboral|workplace accidents]] detected on the property.
- Manages the weekly [[Core/Módulos/Schedule|Schedule]] for their department.

## Related

- [[Hotel/Manager General|Manager General]]
- [[Hotel/Supervisor|Supervisor]]
- [[Hotel/Hotel|Hotel]]
- [[Departamentos del Hotel]]
- [[Requisición]]
- [[Timesheet]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Semáforo de Requisición]]
- [[Semáforo del Colaborador]]
- [[Inspector]]
