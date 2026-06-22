---
tags:
  - arquitectura
  - rol/bdc
aliases:
  - PRD BDC
---

# DOCUMENTO DE REQUISITOS DE PRODUCTO
## PRD – BUSINESS DEVELOPER COORDINATOR

**Sistema de Gestión de Personal · Rol BDC — Ventas**

---

| Campo                   | Contenido                                                                     |
| ----------------------- | ----------------------------------------------------------------------------- |
| **ID del PRD**          | PRD-VENTAS-03                                                                 |
| **Historia de Usuario** | HU-VENTAS-03                                                                  |
| **Departamento**        | Ventas                                                                        |
| **Funcionalidad**       | Validar T&C, aprobar conversiones, supervisar BDs, gestionar casos especiales |
| **Actor Principal**     | Business Developer Coordinator (BDC)                                          |
| **Dispositivo**         | Web – Desktop / Tablet                                                        |
| **Estado**              | En definición                                                                 |
| **Versión**             | 1.0                                                                           |

---

## Objetivo

Permitir al BDC **validar la calidad** de cada T&C antes del cierre, **aprobar la conversión final** del prospecto a cliente, **supervisar al equipo de BDs** y **gestionar los casos especiales** (Café, Negro). Es el rol que custodia la calidad de la entrada de clientes al sistema.

---

## Flujo General

**Reviso T&C pendiente → Valido o rechazo → Negocio (Rosa) junto al BD → Creo Usuario del Hotel → Apruebo conversión → Trigger Automático → Cliente activo (Naranja) | Paralelo: gestiono casos Café y Negro, supervisó al equipo, genero reportes**

---

## Casos de Uso

| ID      | Caso de Uso                    | Prioridad |
| ------- | ------------------------------ | --------- |
| RF-V-08 | Crear Documento de T&C (apoyo) | 🔴 Alta   |
| RF-V-09 | Iniciar negociación (Rosa)     | 🔴 Alta   |
| RF-V-10 | Validar T&C                    | 🔴 Alta   |
| RF-V-11 | Crear Usuario del Hotel        | 🔴 Alta   |
| RF-V-12 | Aprobar conversión a cliente   | 🔴 Alta   |
| RF-V-17 | Marcar estancamiento (Café)    | 🟡 Media  |
| RF-V-18 | Desbloquear estancamiento      | 🟡 Media  |
| RF-V-19 | Reactivar desde Café           | 🟡 Media  |
| RF-V-20 | Marcar cliente Negro           | 🟡 Media  |
| RF-V-21 | Reactivar desde Negro          | 🟢 Baja   |
| RF-V-22 | Ver Pipeline (global)          | 🔴 Alta   |
| RF-V-24 | Ver Mi Equipo                  | 🔴 Alta   |
| RF-V-25 | Métricas individuales por BD   | 🟡 Media  |
| RF-V-26 | Generar reporte de Ventas      | 🟡 Media  |
| RF-V-27 | Enviar reporte a dirección     | 🟡 Media  |
| RF-V-29 | Ver Clientes Activos           | 🟡 Media  |

---

## Reglas de Negocio Aplicables

| ID      | Regla                                 | Descripción / Cómo aplica al BDC                                                                                             | Prioridad |
| ------- | ------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | --------- |
| RR-V-01 | Conversión exclusiva del BDC          | El BDC es el ÚNICO que puede aprobar la conversión de prospecto a cliente activo. El BD jamás puede ejecutar esta acción.    | 🔴 Alta   |
| RR-V-02 | Precondición — Usuario del Hotel      | Antes de aprobar conversión, el BDC DEBE crear el Usuario del Hotel. Sin este paso, el botón "Aprobar" queda bloqueado.      | 🔴 Alta   |
| RR-V-03 | Trigger Automático ejecuta 3 acciones | Al aprobar conversión, el sistema dispara 3 acciones en paralelo: email de bienvenida + notif al BD + remoción del Pipeline. | 🔴 Alta   |
| RR-V-04 | Desbloqueo de Café exclusivo del BDC  | Cuando un BD marca Café, el caso pasa al BDC que investiga, diagnostica y reactiva (o reasigna / cierra como Rojo).          | 🔴 Alta   |
| RR-V-05 | Cliente Negro exclusivo del BDC       | Solo el BDC marca y reactiva clientes Negro (pausados / inactivos). El BD solo recibe notificación, no interviene.           | 🔴 Alta   |
| RR-V-07 | Reactivaciones siempre a Azul Claro   | Cuando el BDC reactiva desde Café o Negro, el status regresa a Azul Claro — nunca a Gris.                                    | 🔴 Alta   |
| RR-V-11 | Trazabilidad de cambios de status     | Toda decisión del BDC (validación T&C, conversión, Café, Negro) queda en log auditable con fecha, autor y motivo.            | 🔴 Alta   |
| RR-V-15 | Contrato resulta del cierre exitoso   | Al aprobar la conversión, el sistema genera el Contrato usando el T&C validado por el BDC como insumo obligatorio.           | 🔴 Alta   |

---

## Restricciones / Permisos

| #   | Acción que NO puede hacer el BDC                | Por qué (regla / decisión)                         | Quién SÍ puede                     |
| --- | ----------------------------------------------- | -------------------------------------------------- | ---------------------------------- |
| 1   | Identificar prospectos (Gris)                   | Es acción operativa de campo, exclusiva del BD     | BD                                 |
| 2   | Elaborar Propuesta Personalizada                | Acción exclusiva del BD (RR-V-09 — solo en Verde)  | BD                                 |
| 3   | Marcar prospecto como Rojo                      | RR-V-06 — gestión de rechazo exclusiva del BD      | BD                                 |
| 4   | Reactivar prospecto desde Rojo                  | Pertenece al ciclo del BD                          | BD                                 |
| 5   | Editar el hotel post-Naranja                    | RR-V-12 — referente comercial sin operación        | Manager de Área / Reclutamiento  |
| 6   | Crear requisiciones                             | Operación post-Naranja, exclusiva del módulo Hotel | Supervisor / Manager de Área     |
| 7   | Dar de alta / baja a BDs                        | Gestión de usuarios es exclusiva del Administrador | Administrador *(en pausa)*         |
| 8   | Operar el ciclo operativo (Schedule, Timesheet) | Fuera del alcance del depto Ventas                 | Hotel + Reclutamiento + Inspección |
