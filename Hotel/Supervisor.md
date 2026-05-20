---
tags:
  - module/hotel
aliases:
  - SUP
  - Supervisor
---

# Supervisor

Operational role in the [[Hotel/Hotel|Hotel]] module, subordinate to the [[Hotel/Manager de Área|Manager de Área]]. Responsible for creating the staff [[Requisición|requisitions]] that the hotel needs to fill.

> [!note] Extended Hierarchy
> In hotels with an extended hierarchy, this role corresponds to the [[Departamentos del Hotel|department]] Supervisor, subordinate to the [[Hotel/Manager de Área|Manager de Área]] of their department. The platform responsibilities are the same.

## Responsibilities

### Requisitions

- Creates the [[Requisición]] from the app, specifying:
  - Required [[Posiciones|positions]].
  - Number of people per position.
  - Start date.
  - Schedule.
  - [[Modalidades de Contratación|Employment modality]].
  - [[Niveles de Inglés|English level]] preference.
  - Additional notes.
- Sends the requisition to the [[Hotel/Manager de Área|Manager de Área]] for approval.

> [!note] On Authorization
> The Supervisor **cannot authorize** a requisition. All requisitions must be reviewed and approved by the [[Hotel/Manager de Área|Manager de Área]] or the [[Hotel/Manager General|Manager General]] before reaching the [[Reclutamiento/Reclutamiento|Reclutamiento]] team.

### Assigned Staff Management

- Places associates on rest (status **Pink — Stand-by** in the [[Semáforo del Colaborador]]).
- Reports associates (status **Red — Reported** in the [[Semáforo del Colaborador]]).
- Reports [[Core/Módulos/Accidente Laboral/Accidente Laboral|workplace accidents]] detected on the property (see [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]]).
- Physically goes to the incident location and captures on-site information on the accident card: exact location, circumstances, witnesses, and immediate care provided.

## Related

- [[Hotel/Manager de Área|Manager de Área]]
- [[Hotel/Manager General|Manager General]]
- [[Hotel/Hotel|Hotel]]
- [[Departamentos del Hotel]]
- [[Requisición]]
- [[Semáforo de Requisición]]
- [[Semáforo del Colaborador]]
- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]]
- [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]]
