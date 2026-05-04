---
tags:
  - arquitectura
  - rol/manager-del-hotel
aliases:
  - PRD Manager del Hotel
---

# DOCUMENTO DE REQUISITOS DE PRODUCTO
## PRD – MANAGER DEL HOTEL

**Sistema de Gestión de Personal · Rol Manager del Hotel / Gerente de Departamento**

---

| Campo                   | Contenido                                                                            |
| ----------------------- | ------------------------------------------------------------------------------------ |
| **ID del PRD**          | PRD-HOTEL-03                                                                         |
| **Historia de Usuario** | HU-HOTEL-03                                                                          |
| **Departamento**        | Hotel                                                                                |
| **Funcionalidad**       | Autorizar requisiciones, gestionar Schedule y Timesheet, administrar personal asignado |
| **Actor Principal**     | Manager del Hotel / Gerente de Departamento                                          |
| **Dispositivo**         | Web – Desktop / Tablet                                                               |
| **Estado**              | En definición                                                                        |
| **Versión**             | 1.0                                                                                  |

---

## Objetivo

Permitir al Manager del Hotel **revisar y autorizar** las requisiciones que crea el Supervisor (capa de seguridad antes de Reclutamiento), **gestionar el Schedule y Timesheet** del depto, **generar el QR de ponchado**, y **administrar a los colaboradores asignados** (Stand-by, Reportar).

---

## Flujo General

**Recibe requisición del Supervisor → Revisa → Autoriza/Rechaza → Reclutamiento toma → Colaboradores asignados → Genera QR → Gestión semanal de Schedule + Timesheet → Stand-by / Reportar cuando aplica**

---

## Casos de Uso

| ID | Caso de Uso | Prioridad |
|---|---|---|
| RF-H-05 | Autorizar requisición | 🔴 Alta |
| RF-H-06 | Rechazar requisición con observaciones | 🔴 Alta |
| RF-H-07 | Eliminar requisición con posiciones | 🟡 Media |
| RF-H-11 | Generar / Renovar QR del Timesheet | 🔴 Alta |
| RF-H-12 | Editar Schedule semanal | 🔴 Alta |
| RF-H-14 | Corregir ponche del Timesheet | 🟡 Media |
| RF-H-15 | Consultar Timesheet | 🔴 Alta |
| RF-H-17 | Poner colaborador en Stand-by (Rosa) | 🔴 Alta |
| RF-H-18 | Reportar colaborador (Rojo) | 🔴 Alta |
| RF-H-29 | Consultar Blacklist | 🟡 Media |

---

## Reglas de Negocio Aplicables

- **RR-H-02:** Solo el Manager del Hotel puede autorizar requisiciones (capa de seguridad).
- **RR-H-03:** La requisición debe tener ≥1 posición para autorizar.
- **RR-H-09:** Generación de QR exclusiva del Manager del Hotel.
- **RR-H-10:** Reporte de colaborador (Rojo) exclusivo del Manager del Hotel.
- **RR-H-11:** Stand-by (Rosa) compartido con el Supervisor.
- **RR-H-15:** Sin acceso al Indicador de Lunch Extendido.

---

## Restricciones / Permisos

- NO puede crear requisiciones (eso es del Supervisor).
- NO accede al Indicador de Lunch Extendido.
- NO puede agregar / remover de Blacklist (eso es del depto Reclutamiento).
- NO puede dar de alta usuarios (eso es del Administrador).
