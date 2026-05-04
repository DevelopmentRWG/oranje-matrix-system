---
tags:
  - arquitectura
  - rol/manager-general
aliases:
  - PRD Manager General
---

# DOCUMENTO DE REQUISITOS DE PRODUCTO
## PRD – MANAGER GENERAL

**Sistema de Gestión de Personal · Rol Manager General (GM) del Hotel**

---

| Campo                   | Contenido                                                                |
| ----------------------- | ------------------------------------------------------------------------ |
| **ID del PRD**          | PRD-HOTEL-04                                                             |
| **Historia de Usuario** | HU-HOTEL-04                                                              |
| **Departamento**        | Hotel                                                                    |
| **Funcionalidad**       | Visibilidad global del hotel, supervisión de Gerentes, reportes ejecutivos |
| **Actor Principal**     | Manager General (GM) — solo jerarquía extendida                          |
| **Dispositivo**         | Web – Desktop / Tablet                                                   |
| **Estado**              | En definición                                                            |
| **Versión**             | 1.0                                                                      |

---

## Objetivo

Permitir al Manager General **supervisar el hotel completo** con visibilidad consolidada del Schedule, Timesheet y requisiciones de todos los departamentos. Detectar a tiempo problemas operativos, escalar casos críticos, generar reportes ejecutivos y mantener informada a la dirección.

---

## Flujo General

**Login → Dashboard global → Detectar desbalances → Supervisar Gerentes → Comentar/Escalar/Solicitar reporte → Generar reportes ejecutivos → Enviar a dirección**

---

## Casos de Uso

| ID | Caso de Uso | Prioridad |
|---|---|---|
| RF-H-22 | Ver Schedule global del hotel | 🟡 Media |
| RF-H-23 | Ver Timesheet global del hotel | 🟡 Media |
| RF-H-24 | Generar reporte ejecutivo | 🟡 Media |
| RF-H-25 | Enviar reporte a dirección | 🟡 Media |
| RF-H-26 | Comentar al expediente de requisición | 🟢 Baja |
| RF-H-27 | Escalar requisición demorada | 🟡 Media |
| RF-H-28 | Solicitar reporte a Gerente de Departamento | 🟢 Baja |
| RF-H-29 | Consultar Blacklist | 🟡 Media |

---

## Reglas de Negocio Aplicables

- **RR-H-13:** El sistema soporta jerarquía simple y extendida; este rol solo aplica en extendida.
- **RR-H-14:** El Manager General NO autoriza requisiciones (esa responsabilidad recae en cada Gerente de Departamento).
- **RR-H-15:** Sin acceso al Indicador de Lunch Extendido.

---

## Restricciones / Permisos

- NO crea requisiciones.
- NO autoriza requisiciones (RR-H-14).
- NO genera QR del Timesheet.
- NO edita Schedule (solo consulta).
- NO corrige ponches.
- NO pone Stand-by ni reporta colaborador (Rojo).
- NO puede dar de alta/baja a Gerentes ni Supervisores (eso es del Administrador).
- NO ve el Indicador de Lunch Extendido (RR-H-15).
