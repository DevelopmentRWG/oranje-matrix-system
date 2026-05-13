---
tags:
  - arquitectura
  - rol/business-developer
aliases:
  - PRD Business Developer
---

# DOCUMENTO DE REQUISITOS DE PRODUCTO
## PRD – BUSINESS DEVELOPER

**Sistema de Gestión de Personal · Rol Business Developer (BD) — Ventas**

---

| Campo                   | Contenido                                                                   |
| ----------------------- | --------------------------------------------------------------------------- |
| **ID del PRD**          | PRD-VENTAS-02                                                               |
| **Historia de Usuario** | HU-VENTAS-02                                                                |
| **Departamento**        | Ventas                                                                      |
| **Funcionalidad**       | Ejecutar el ciclo comercial con hoteles prospecto en el territorio asignado |
| **Actor Principal**     | Business Developer (BD)                                                     |
| **Dispositivo**         | Mobile (prioritario) / Tablet / Desktop                                     |
| **Estado**              | En definición                                                               |
| **Versión**             | 1.0                                                                         |

---

## Objetivo

Permitir al Business Developer **identificar, contactar, proponer y dar seguimiento** a hoteles prospecto en su territorio asignado, llevándolos a través del Semáforo Onboarding hasta el status Rosa, donde el BDC toma la conversión final.

---

## Flujo General

**Identifico prospecto (Gris) → Recopilo datos + visita en frío (Azul Claro) → Elaboro y envío Propuesta (Verde) → Seguimiento (Amarillo) → Creo T&C → Negocio con BDC (Rosa) → BDC aprueba → Naranja (cliente activo) → Quedo como referente comercial**

---

## Casos de Uso

| ID      | Caso de Uso                         | Prioridad |
| ------- | ----------------------------------- | --------- |
| RF-V-01 | Identificar prospecto (Gris)        | 🔴 Alta   |
| RF-V-02 | Crear perfil del hotel (Azul Claro) | 🔴 Alta   |
| RF-V-03 | Registrar visita en frío            | 🟡 Media  |
| RF-V-04 | Elaborar Propuesta Personalizada    | 🔴 Alta   |
| RF-V-05 | Enviar propuesta al hotel           | 🔴 Alta   |
| RF-V-06 | Registrar intentos de contacto      | 🟡 Media  |
| RF-V-07 | Avanzar a Amarillo (interés)        | 🔴 Alta   |
| RF-V-08 | Crear Documento de T&C              | 🔴 Alta   |
| RF-V-09 | Iniciar negociación (Rosa)          | 🔴 Alta   |
| RF-V-15 | Gestionar rechazo (Rojo)            | 🟡 Media  |
| RF-V-16 | Reactivar prospecto desde Rojo      | 🟡 Media  |
| RF-V-17 | Marcar estancamiento (Café)         | 🟡 Media  |
| RF-V-22 | Ver Pipeline                        | 🔴 Alta   |
| RF-V-23 | Ver Mi Territorio                   | 🔴 Alta   |
| RF-V-29 | Ver Clientes Activos (referente)    | 🟡 Media  |

---

## Reglas de Negocio Aplicables

| ID      | Regla                                 | Descripción / Cómo aplica al BD                                                                                               | Prioridad |
| ------- | ------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | --------- |
| RR-V-01 | Conversión exclusiva del BDC          | El BD NO aprueba conversión bajo ninguna circunstancia. Esa acción es exclusiva del BDC y dispara el Trigger Automático.      | 🔴 Alta   |
| RR-V-04 | Desbloqueo de Café exclusivo del BDC  | El BD puede MARCAR Café cuando detecta estancamiento, pero NO puede desbloquearlo — eso lo investiga y resuelve el BDC.       | 🔴 Alta   |
| RR-V-06 | Gestión de rechazo (Rojo) por el BD   | El BD es el responsable de marcar Rojo cuando el hotel rechaza la propuesta. Es acción exclusiva suya, no del BDC.            | 🔴 Alta   |
| RR-V-07 | Reactivaciones siempre a Azul Claro   | Cuando el BD reactiva un prospecto desde Rojo, el sistema lo regresa automáticamente a Azul Claro — nunca a Gris.             | 🔴 Alta   |
| RR-V-09 | Propuesta Personalizada solo en Verde | El BD solo puede elaborar y enviar la Propuesta Personalizada en status Verde. Fuera de ese status, la acción está bloqueada. | 🔴 Alta   |
| RR-V-11 | Trazabilidad de cambios de status     | Todo cambio de status que haga el BD queda registrado con fecha, autor y comentario obligatorio.                              | 🔴 Alta   |
| RR-V-12 | Post-Naranja: referentes comerciales  | Una vez el hotel pasa a Naranja, el BD queda como referente comercial — sin permisos operativos sobre el hotel.               | 🔴 Alta   |

---

## Restricciones / Permisos

| #   | Acción que NO puede hacer el BD        | Por qué (regla / decisión)                        | Quién SÍ puede                              |
| --- | -------------------------------------- | ------------------------------------------------- | ------------------------------------------- |
| 1   | Validar Documento de T&C               | RR-V-15 — sí final exclusivo del BDC              | BDC                                         |
| 2   | Crear Usuario del Hotel                | RR-V-02 — precondición exclusiva del BDC          | BDC                                         |
| 3   | Aprobar conversión de prospecto        | RR-V-01 — acción exclusiva del BDC                | BDC                                         |
| 4   | Desbloquear estancamiento (Café)       | RR-V-04 — investigación exclusiva del BDC         | BDC                                         |
| 5   | Marcar cliente Negro                   | RR-V-05 — gestión exclusiva del BDC               | BDC                                         |
| 6   | Reactivar cliente desde Negro          | RR-V-05 — exclusivo del BDC                       | BDC                                         |
| 7   | Ver prospectos fuera de su territorio  | Alcance limitado a rutas y zonas asignadas        | BDC (vista global) / otros BDs en sus zonas |
| 8   | Ver métricas individuales de otros BDs | Sin acceso a desempeño ajeno                      | BDC                                         |
| 9   | Generar reportes ejecutivos            | Sin acceso al módulo Reportes                     | BDC                                         |
| 10  | Editar el hotel post-Naranja           | RR-V-12 — referente comercial sin operación       | Manager del Hotel / Reclutamiento           |
| 11  | Crear requisiciones                    | Operación post-Naranja exclusiva del módulo Hotel | Supervisor / Manager del Hotel              |
