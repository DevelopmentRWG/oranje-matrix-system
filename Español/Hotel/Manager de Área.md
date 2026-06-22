---
tags:
  - modulo/hotel
aliases:
  - Manager de Área
  - Gerente de Departamento
  - GH
---

# Manager de Área

Rol operativo del módulo de [[Hotel/Hotel|Hotel]]. Responsable de aprobar o rechazar las [[Requisición|requisiciones]], gestionar a los colaboradores asignados y administrar el [[Core/Módulos/Schedule|Schedule]] de su departamento.

> [!note] Jerarquía simple
> En hoteles con jerarquía simple, el [[Hotel/Manager General|Manager General]] también opera como Manager de Área (misma persona, dos roles). En hoteles con jerarquía extendida, hay un Manager de Área por cada [[Departamentos del Hotel|departamento]] (Housekeeping, Alimentos, Mantenimiento, Front Desk), subordinados al [[Hotel/Manager General|Manager General]].

## Responsabilidades

### Requisiciones

- Crea [[Requisición|requisiciones]] de personal.
- **Aprueba** la requisición (estado **Autorizada**), que queda disponible en la bandeja compartida de [[Reclutamiento/Reclutamiento|Reclutamiento]] para ser tomada por una [[Reclutadora]] o [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo]] (modelo [[Self-Pick de Requisiciones|Self-Pick]]).
- **Rechaza** la requisición, regresándola al creador con observaciones (estado **En elaboración**).

> [!important] Capa de seguridad
> Esta aprobación es una capa de seguridad para evitar que lleguen requisiciones falsas o incorrectas al equipo de [[Reclutamiento/Reclutamiento|Reclutamiento]]. Oranje solo recibe requisiciones que un Manager de Área o el [[Hotel/Manager General|Manager General]] ha validado.

### Gestión de personal asignado

- Genera el código **QR** para que los colaboradores ponchen en el [[Timesheet]].
- Manda a colaboradores a descansar (estado **Rosa — Stand-by** en el [[Semáforo del Colaborador]]).
- Reporta colaboradores (estado **Rojo — Reportado** en el [[Semáforo del Colaborador]]).
- Reporta [[Core/Módulos/Accidente Laboral/Accidente Laboral|accidentes laborales]] detectados en la propiedad.
- Gestiona el [[Core/Módulos/Schedule|Schedule]] semanal de su departamento.

## Relacionado

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
