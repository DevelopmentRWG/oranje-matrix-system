---
tags:
  - arquitectura
  - rol/colaborador
aliases:
  - PRD Colaborador
---

# DOCUMENTO DE REQUISITOS DE PRODUCTO
## PRD — COLABORADOR

**Sistema de Gestión de Personal · Rol Colaborador (COL)**

---

| Campo                   | Contenido                                                                                      |
| ----------------------- | ---------------------------------------------------------------------------------------------- |
| **ID del PRD**          | PRD-COLAB-01                                                                                   |
| **Historia de Usuario** | HU-COLAB-01                                                                                    |
| **Departamento**        | Colaborador / Operación                                                                        |
| **Funcionalidad**       | App de autoservicio personal: alta, ponche, disponibilidad, reporte de accidente y consultas  |
| **Actor Principal**     | Colaborador (COL)                                                                              |
| **Dispositivo**         | Mobile + Web (responsive)                                                                      |
| **Estado**              | En definición                                                                                  |
| **Versión**             | 1.0                                                                                            |

---

## Objetivo

Dar al Colaborador una **app móvil de autoservicio personal** que le permita: completar su alta en el sistema (Fase 2 y Fase 3), registrar su asistencia diaria mediante ponche QR, declarar su disponibilidad voluntaria (Amarillo), reportar accidentes laborales, y consultar sus propios datos operativos (schedule, timesheet, pago, notificaciones y perfil). El colaborador no gestiona a nadie; solo opera sobre sus propios datos.

---

## Historia de Usuario

> Como **Colaborador**, quiero poder completar mi alta, ponchar mis entradas y salidas, ver mis turnos y mi pago semanal, y declarar mi disponibilidad, todo desde mi teléfono, para no depender de intermediarios para gestionar mi información operativa básica.

---

## Flujo General

**Descarga app → Completa Fase 2 (alta) → Completa Fase 3 (emergencia) → Espera validación de Reclutadora → Queda en Verde fuerte → Es asignado → Poncha diariamente vía QR → Consulta su schedule y timesheet → Al quedar libre, activa Amarillo si desea disponibilidad voluntaria → Si sufre accidente, reporta desde la app**

---

## Casos de Uso

| ID | Caso de Uso | Prioridad |
|---|---|---|
| RF-C-01 | Completar alta en la app (Fase 2) | 🔴 Alta |
| RF-C-02 | Completar datos de emergencia (Fase 3) | 🔴 Alta |
| RF-C-03 | Ponchar vía QR | 🔴 Alta |
| RF-C-04 | Activar disponibilidad voluntaria (Amarillo) | 🔴 Alta |
| RF-C-05 | Reportar accidente laboral desde la app | 🔴 Alta |
| RF-C-06 | Consultar Mi Schedule | 🟡 Media |
| RF-C-07 | Consultar Mi Timesheet | 🟡 Media |
| RF-C-08 | Consultar Mi Pago semanal | 🟡 Media |
| RF-C-09 | Consultar notificaciones | 🟡 Media |
| RF-C-10 | Consultar Mi perfil y estado | 🟡 Media |

> [!note]
> Los archivos de detalle de cada caso de uso (RF-C-01 a RF-C-10) están disponibles en `Casos de Uso/`.

---

## Reglas de Negocio Aplicables

### Reglas nuevas — específicas de la app de autoservicio

| ID | Regla |
|---|---|
| RR-C-01 | El Colaborador solo puede ver y editar SUS PROPIOS datos. Sin acceso a datos de otros colaboradores. |
| RR-C-02 | Amarillo (disponibilidad voluntaria) es la única transición de estado que el Colaborador activa por sí mismo, sin aprobación de nadie. |
| RR-C-03 | El Colaborador no puede ponchar sin un Timesheet activo, lo cual requiere estar inscrito en el Schedule con una asignación activa (fija o temporal). |
| RR-C-04 | El Colaborador accede a la plataforma desde **móvil y web (responsive)**. El onboarding (Fase 2 y 3) y las vistas de consulta (Mi Schedule, Mi Timesheet, Mi Pago, Notificaciones, Mi Perfil) y la activación de disponibilidad (Amarillo) están disponibles en ambos canales. El ponche por QR (RF-C-03) es una acción nativa de móvil (escaneo del QR físico en el hotel con la cámara del teléfono). |
| RR-C-05 | El Colaborador puede consultar el **historial de sus pagos ya recibidos** (semana, hotel(es), horas, monto pagado y fecha de pago). **No puede ver el monto de su pago en curso o próximo**: el cálculo del pago es exclusivo de Contabilidad y solo se revela al Colaborador una vez que el pago ha sido liberado. El [[Contabilidad/Consolidado Semanal del Colaborador\|Consolidado Semanal del Colaborador]] completo (rate interno, deducciones, facturación) permanece de uso exclusivo de Contabilidad. Ver [[RF-C-08 Consultar Mi Pago semanal]]. |

### Reglas existentes referenciadas

Para las reglas de negocio detalladas sobre ponchado, deducción de lunch, 3 inasistencias → Blacklist, protección Gris por accidente, y pago semanal, ver: [[Reglas del Colaborador]]

---

## Restricciones / Permisos

- NO puede aceptar ni rechazar asignaciones.
- NO puede solicitar reasignación directamente.
- NO puede autorizar ninguna acción del sistema.
- NO puede asignar a nadie ni gestionar a otros colaboradores.
- NO puede editar el Schedule (solo lectura).
- NO puede corregir ponches (exclusivo del Manager de Área).
- NO puede ver datos de otros colaboradores (RR-C-01).
- NO puede acceder a módulos de gestión (requisiciones, pool, contabilidad, QA).
- El ponche por QR (RF-C-03) es exclusivo de móvil; en web el colaborador puede consultar toda la información pero no puede ejecutar el ponche (RR-C-04).
