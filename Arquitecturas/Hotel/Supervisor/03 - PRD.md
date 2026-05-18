---
tags:
  - arquitectura
  - rol/supervisor-hotel
aliases:
  - PRD Supervisor
---

# DOCUMENTO DE REQUISITOS DE PRODUCTO
## PRD – SUPERVISOR

**Sistema de Gestión de Personal · Rol Supervisor (SUP) del Hotel**

---

| Campo                   | Contenido                                                                  |
| ----------------------- | -------------------------------------------------------------------------- |
| **ID del PRD**          | PRD-HOTEL-02                                                               |
| **Historia de Usuario** | HU-HOTEL-02                                                                |
| **Departamento**        | Hotel                                                                      |
| **Funcionalidad**       | Crear requisiciones de personal y reportar accidentes laborales en sitio  |
| **Actor Principal**     | Supervisor (SUP)                                                           |
| **Dispositivo**         | Mobile (prioritario) / Tablet / Desktop                                    |
| **Estado**              | En definición                                                              |
| **Versión**             | 1.0                                                                        |

---

## Objetivo

Permitir al Supervisor **formalizar la necesidad de personal del hotel** mediante requisiciones que el Manager de Área autorizará para que Reclutamiento las cubra. Además, dar al Supervisor las herramientas para **reportar accidentes laborales en escenarios A y B** con captura presencial.

---

## Flujo General

**Detecta necesidad de personal → Crea requisición (mobile) → Envía a Manager de Área → Espera autorización → Si rechazo, corrige y reenvía → Una vez autorizada, queda en manos de Reclutamiento → Operación diaria: consulta Schedule, Timesheet, reporta accidentes**

---

## Casos de Uso

| ID | Caso de Uso | Prioridad |
|---|---|---|
| RF-H-01 | Crear requisición | 🔴 Alta |
| RF-H-02 | Editar borrador de requisición | 🔴 Alta |
| RF-H-03 | Enviar requisición a autorización | 🔴 Alta |
| RF-H-04 | Eliminar borrador / requisición vacía | 🟡 Media |
| RF-H-13 | Consultar Schedule | 🔴 Alta |
| RF-H-15 | Consultar Timesheet | 🔴 Alta |
| RF-H-17 | Poner colaborador en Stand-by (Rosa) | 🔴 Alta |
| RF-H-19 | Sugerir refuerzo de personal | 🟢 Baja |
| RF-H-20 | Reportar accidente — Escenario A | 🔴 Alta |
| RF-H-21 | Reportar accidente — Escenario B | 🔴 Alta |

---

## Reglas de Negocio Aplicables

- **RR-H-02:** El Supervisor NO puede autorizar requisiciones (capa de seguridad).
- **RR-H-03:** La requisición debe tener ≥1 posición para enviar a autorización.
- **RR-H-11:** Stand-by (Rosa) compartido con Manager de Área.
- **RR-H-12:** Acceso al módulo de requisiciones restringido al Supervisor y Manager de Área.
- **RR-H-15:** Sin acceso al Indicador de Lunch Extendido.
- **RR-H-19:** Reporte de accidentes en escenarios A y B.
- **RR-H-20:** Colaborador en accidente pasa a Gris (protección 3 inasistencias).

---

## Restricciones / Permisos

- NO puede autorizar requisiciones.
- NO puede generar QR del Timesheet.
- NO puede corregir ponches.
- NO puede reportar colaborador (Rojo).
- NO puede editar Schedule (solo consulta).
