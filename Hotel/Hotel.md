---
tags:
  - modulo/hotel
aliases:
  - Hotel
  - Módulo de Hotel
---

# Hotel

Módulo que representa al hotel como cliente de Oranje. El hotel solicita personal a través de [[Requisición|requisiciones]] y gestiona su operación semanal desde el [[Core/Módulos/Schedule|Schedule]], que es el eje donde convergen la demanda de posiciones, la cobertura de colaboradores asignados y el registro de tiempo trabajado ([[Timesheet]]). Opera como contraparte del equipo de [[Reclutamiento/Reclutamiento|Reclutamiento]].

## Contenido del módulo

### Roles

- [[Hotel/Manager del Hotel|Manager del Hotel]] — Aprueba o rechaza requisiciones; gestiona el personal asignado.
- [[Hotel/Colaborador del Gerente del Hotel|Colaborador del Gerente del Hotel]] — Crea las requisiciones de personal.

### Procesos

- Creación y autorización de [[Requisición|requisiciones]].
- Gestión del [[Core/Módulos/Schedule|Schedule]] semanal.
- Registro de tiempo trabajado vía [[Timesheet]].

## Conceptos Core relacionados

- [[Requisición]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Timesheet]]
- [[Semáforo de Requisición]]
- [[Semáforo de Urgencia de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
- [[Semáforo del Colaborador]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Posiciones]]
- [[Modalidades de Contratación]]
- [[Niveles de Inglés]]
- [[Zonas]]
- [[Inspector]]

## Relación con otros módulos

- [[Reclutamiento/Reclutamiento|Reclutamiento]] — Recibe las requisiciones aprobadas y asigna personal.
- [[Ventas/Ventas|Ventas]] — Responsable del onboarding de nuevos hoteles.
