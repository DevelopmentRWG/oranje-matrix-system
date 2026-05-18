---
tags:
  - arquitectura
  - departamento/hotel
aliases:
  - PRD del Depto Hotel
---

# DOCUMENTO DE REQUISITOS DE PRODUCTO
## PRD – HOTEL

**Sistema de Gestión de Personal · Departamento de Hotel**

---

| Campo | Contenido |
|---|---|
| **ID del PRD** | PRD-HOTEL-01 |
| **Historia de Usuario** | HU-HOTEL-01 |
| **Departamento** | Hotel |
| **Funcionalidad** | Gestionar el ciclo del hotel como cliente: solicitud de personal, aprobación, gestión del Schedule semanal, registro de Timesheet y reporte de incidencias |
| **Actor Principal** | Manager de Área · Supervisor · Manager General (jerarquía extendida) |
| **Dispositivo** | Web – Desktop / Tablet / Mobile (app del Supervisor) |
| **Estado** | En definición |
| **Versión** | 1.0 |

---

## Objetivo

Permitir al hotel **solicitar personal a Oranje** mediante requisiciones, **gestionar el Schedule semanal** y el **Timesheet** de los colaboradores asignados, y **reportar incidencias** (accidentes laborales, colaboradores con problemas). El depto Hotel actúa como contraparte del depto Reclutamiento bajo el modelo de capa de seguridad: **el Supervisor crea, el Manager de Área autoriza, Reclutamiento toma vía Self-Pick**.

---

## Alcance

**Incluye:**
- Habilitación del hotel post-onboarding (status Naranja en Semáforo Onboarding).
- Creación de requisiciones por el Supervisor.
- Autorización / rechazo por el Manager de Área (capa de seguridad).
- Gestión semanal del Schedule.
- Generación de QR del Timesheet (Manager de Área).
- Registro de ponches y cálculo de Indicador de Cumplimiento del Timesheet.
- Stand-by (Rosa) y reporte (Rojo) de colaboradores.
- Reporte de accidentes laborales por el Supervisor (escenarios A y B).
- Visibilidad global y reportes ejecutivos por el Manager General (jerarquía extendida).
- Soporte de jerarquía simple y extendida.

**Fuera del alcance:**
- Reclutamiento, validación y asignación de colaboradores (módulo Reclutamiento).
- Inspección operativa en sitio (módulo Inspección).
- Auditoría de calidad (módulo QA).
- Onboarding comercial pre-cliente (módulo Ventas / Onboarding-Hotel).
- Configuración del sistema (módulo Administrador — en pausa).

---

## Flujo General

**Supervisor crea requisición → Manager de Área autoriza → Reclutamiento la toma (Self-Pick) → Colaboradores asignados aparecen en el Schedule del hotel → Manager de Área genera QR → Colaboradores ponchan en Timesheet → Cálculo de Indicador de Cumplimiento → Pago semanal**

```
HOTEL                                          ORANJE                          
─────                                          ──────
Supervisor crea requisición
        │
        ▼
Manager de Área autoriza ─────────────────►  Bandeja de Autorizadas
                                                       │
                                                       ▼
                                               Reclutadora/Líder toma (Self-Pick)
                                                       │
                                                       ▼
                                               Asigna colaboradores
        ┌───────────────────────────────────────────────┘
        ▼
Schedule del hotel ←── colaboradores asignados
        │
        ▼
Manager de Área genera QR
        │
        ▼
Timesheet (ponches diarios) ─────────────────► Indicador de Cumplimiento
        │
        ▼
Stand-by (Rosa) / Reportar (Rojo) / Accidente (Gris) ──► Inspector / Investigación
```

---

## Actores

| Actor                      | Tipo           | Responsabilidad principal                                        |
| -------------------------- | -------------- | ---------------------------------------------------------------- |
| Supervisor (SUP)           | Operativo      | Crea requisiciones · Reporta accidentes laborales                |
| Manager de Área          | Supervisor     | Autoriza requisiciones · Gestiona Schedule y Timesheet · Genera QR |
| Manager General (GM)       | Ejecutivo      | Visibilidad global · Supervisión de Gerentes · Reportes ejecutivos |
| Sistema                    | Automatización | Numeración, semáforos, asignación de Inspector, journals, notificaciones |
| Administrador *(en pausa)* | Configuración  | Usuarios, catálogos, permisos                                    |

---

## Restricciones / Reglas de negocio aplicables

Ver [[07 - Reglas de Negocio]] para el detalle. Las más importantes:

- **RR-H-01:** El hotel solo opera tras alcanzar status Naranja en el Semáforo Onboarding.
- **RR-H-02:** Solo el Manager de Área autoriza requisiciones (capa de seguridad).
- **RR-H-09:** Solo el Manager de Área genera QR del Timesheet.
- **RR-H-10:** Solo el Manager de Área reporta colaborador (Rojo).
- **RR-H-11:** Stand-by (Rosa) compartido entre Manager de Área y Supervisor.
- **RR-H-13:** Sistema soporta jerarquía simple y extendida.

---

## Integraciones (RI)

| ID       | Integración                            | Descripción                                                                       |
| -------- | -------------------------------------- | --------------------------------------------------------------------------------- |
| RI-H-01  | Hotel ↔ Reclutamiento                  | Las requisiciones autorizadas pasan a la bandeja de Reclutamiento (Self-Pick).    |
| RI-H-02  | Hotel ↔ Schedule                       | Las posiciones autorizadas se reflejan automáticamente en el Schedule semanal.    |
| RI-H-03  | Hotel ↔ Timesheet                      | El Timesheet se construye sobre el Schedule. Los ponches se registran vía QR.     |
| RI-H-04  | Hotel ↔ Inspección                     | Asignación automática de Inspector por zona al autorizar. Investigación de Rojo y Gris. |
| RI-H-05  | Hotel ↔ QA                             | Operador de QA fijo asignado al depto Hotel. Métricas e Indicador de Calidad.     |
| RI-H-06  | Hotel ↔ Onboarding-Hotel               | Habilitación del hotel al alcanzar status Naranja en Semáforo Onboarding.         |
---

## Dependencias

Ver [[09 - Dependencias]] para el detalle.

- Depende de [[Reclutamiento/Reclutamiento|Reclutamiento]] para cubrir requisiciones.
- Depende de [[Inspección/Inspección|Inspección]] para investigar reportes y accidentes.
- Depende de [[Ventas/Onboarding-Hotel|Onboarding-Hotel]] para la habilitación del hotel.
- Depende de [[QA/QA|QA]] para auditoría de calidad.
- Depende del [[Core/Catálogos/Departamentos del Hotel|catálogo de Departamentos del Hotel]] y [[Posiciones]].
