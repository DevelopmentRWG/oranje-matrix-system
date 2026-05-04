---
tags:
  - arquitectura
  - departamento/hotel
aliases:
  - Portada Hotel
  - Departamento de Hotel (Portada)
---

# GESTIÓN DE ROLES – DEPARTAMENTO DE HOTEL

**Plantilla de Roles y Perfiles de Usuario**

---

| Campo            | Contenido                  |
| ---------------- | -------------------------- |
| **Documento**    | Plantilla de Roles – Hotel |
| **Departamento** | Hotel                      |
| **Relacionado**  | PRD-HOTEL-01 · HU-HOTEL-01 |
| **Versión**      | 1.0                        |
| **Estado**       | En definición              |

---

## ROLES DEFINIDOS EN ESTE DOCUMENTO

| ID           | Rol · Descripción breve                                                                                                                                              |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **ROL-H-01** | 🦺 **Supervisor (SUP)** — Crea las requisiciones de personal y reporta accidentes laborales. Subordinado del Manager del Hotel / Gerente de Departamento.            |
| **ROL-H-02** | 🧑‍💼 **Manager del Hotel / Gerente de Departamento** — Autoriza o rechaza requisiciones, gestiona Schedule y Timesheet, genera QR, reporta colaboradores.            |
| **ROL-H-03** | 🧑‍✈️ **Manager General (GM)** — Máxima autoridad del lado del hotel en jerarquía extendida. Visibilidad global, supervisión y reportes ejecutivos. NO opera diariamente. |
| **ROL-H-04** | ⚙️ **Sistema** — Automatización interna: numeración de requisición, cálculo de urgencia, asignación de Inspector, semáforos, journals, notificaciones.              |
| **ROL-H-05** | 🛠️ **Administrador** — Gestión total del sistema: usuarios, catálogos, permisos. *(En pausa hasta que se estabilicen reglas de negocio.)*                            |

---

## Jerarquías soportadas

| Jerarquía | Estructura | Roles aplicables |
|---|---|---|
| **Simple** | Manager del Hotel → Supervisor → Colaboradores de Oranje | ROL-H-01, ROL-H-02 |
| **Extendida** | Manager General → Gerente de Departamento → Supervisor → Colaboradores | ROL-H-01, ROL-H-02, ROL-H-03 |

> [!info]
> En jerarquía extendida, **Manager del Hotel = Gerente de Departamento** (mismas responsabilidades en plataforma; cambia solo el alcance — todo el hotel vs. su departamento). Los departamentos operativos del hotel son: **Housekeeping, Alimentos, Mantenimiento, Front Desk** (ver [[Departamentos del Hotel]]).
