---
tags:
  - modulo/hotel
aliases:
  - Manager del Hotel
  - Gerente de Hotel
  - Gerente del Hotel
  - GH
  - HM
  - Hotel Manager
---

# Manager del Hotel

Rol de supervisión del módulo de [[Hotel/Hotel|Hotel]]. Responsable de aprobar o rechazar las [[Requisición|requisiciones]] creadas por el [[Hotel/Colaborador del Gerente del Hotel|Colaborador del Gerente del Hotel]], y de gestionar a los colaboradores asignados al hotel.

## Responsabilidades

### Aprobación de requisiciones

- Recibe las [[Requisición|requisiciones]] creadas por el [[Hotel/Colaborador del Gerente del Hotel|Colaborador del Gerente del Hotel]] (estado **Pendiente de aprobación** en el [[Semáforo de Requisición]]).
- Revisa que la requisición sea correcta y justificada.
- **Aprueba** la requisición (estado **Autorizada**), enviándola al [[Manager de Reclutamiento]].
- **Rechaza** la requisición, regresándola al [[Hotel/Colaborador del Gerente del Hotel|Colaborador del Gerente del Hotel]] con observaciones (estado **En elaboración**).

> [!important] Capa de seguridad
> Esta aprobación es una capa de seguridad para evitar que lleguen requisiciones falsas o incorrectas al equipo de [[Reclutamiento/Reclutamiento|Reclutamiento]]. Oranje solo recibe requisiciones que el Manager del Hotel ha validado.

### Gestión de personal asignado

- Genera el código **QR** para que los colaboradores ponchen en el [[Timesheet]].
- Manda a colaboradores a descansar (estado **Rosa - Stand-by** en el [[Semáforo del Colaborador]]).
- Reporta colaboradores (estado **Rojo - Reportado** en el [[Semáforo del Colaborador]]).
- Gestiona el [[Core/Módulos/Schedule|Schedule]] semanal del hotel.

## Relacionado

- [[Hotel/Colaborador del Gerente del Hotel|Colaborador del Gerente del Hotel]]
- [[Hotel/Hotel|Hotel]]
- [[Requisición]]
- [[Timesheet]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Semáforo de Requisición]]
- [[Semáforo del Colaborador]]
- [[Inspector]]
