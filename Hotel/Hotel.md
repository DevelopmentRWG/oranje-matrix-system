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

- [[Hotel/Manager General|Manager General]] — Maxima autoridad en hoteles con jerarquia extendida. Supervisa a los Gerentes de Departamento.
- [[Hotel/Manager del Hotel|Manager del Hotel]] — Aprueba o rechaza requisiciones; gestiona el personal asignado.
- [[Hotel/Supervisor|Supervisor]] — Crea las requisiciones de personal.

### Estructura organizacional

Dependiendo del tamaño y complejidad del hotel, la plataforma soporta dos configuraciones jerárquicas:

#### Jerarquía simple

Para hoteles pequeños o con estructura plana.

```
Manager del Hotel → SUP → Colaboradores de Oranje
```

#### Jerarquía extendida

Para hoteles grandes con múltiples [[Departamentos del Hotel|departamentos]] operativos.

```
Manager General
  └── Gerente de Departamento (uno por departamento)
       └── Supervisor(es)
            └── Colaboradores de Oranje
```

#### Equivalencia de roles

| Jerarquía simple | Jerarquía extendida | Responsabilidades en plataforma |
|---|---|---|
| [[Hotel/Manager del Hotel\|Manager del Hotel]] | Gerente de Departamento | Aprueba requisiciones, gestiona schedule, genera QR, reporta colaboradores |
| [[Hotel/Supervisor\|SUP]] | Supervisor | Crea requisiciones, reporta accidentes laborales |
| *(no aplica)* | [[Hotel/Manager General\|Manager General]] | Supervisión general, visibilidad global |

#### Departamentos del hotel

- **Housekeeping** — Housekeeper, Hoseman, Laundry
- **Alimentos** — Chef
- **Mantenimiento**
- **Front Desk**

Ver catálogo completo en [[Departamentos del Hotel]].

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
- [[Departamentos del Hotel]]
- [[Modalidades de Contratación]]
- [[Niveles de Inglés]]
- [[Zonas]]
- [[Inspector]]

## Relación con otros módulos

- [[Reclutamiento/Reclutamiento|Reclutamiento]] — Recibe las requisiciones aprobadas y asigna personal.
- [[Ventas/Ventas|Ventas]] — Responsable del onboarding de nuevos hoteles.
