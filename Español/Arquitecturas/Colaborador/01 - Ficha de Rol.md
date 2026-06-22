---
tags:
  - arquitectura
  - rol/colaborador
aliases:
  - Ficha de Rol Colaborador
---

# FICHA DE ROL — COLABORADOR

---

| Campo              | Contenido                                                                   |
| ------------------ | --------------------------------------------------------------------------- |
| **ID Rol**         | ROL-C-01                                                                    |
| **Nombre del Rol** | 👷 Colaborador (COL)                                                        |
| **Tipo**           | Operativo (trabajador de campo)                                             |
| **Departamento**   | Colaborador / Operación                                                     |
| **Reporta a**      | Manager de Área / Supervisor en sitio; gestionado por Reclutamiento         |
| **Supervisa a**    | —                                                                           |

---

## Descripción

Entidad central del sistema Oranje. Persona reclutada, asignada y gestionada operativamente en los hoteles. Es el **sujeto pasivo** del sistema: su ciclo de vida es controlado por otros roles (Reclutadora, Inspector, Manager de Área). Su única acción autónoma de cambio de estado es activar su disponibilidad voluntaria (Amarillo).

---

## Objetivo en el Sistema

Completar su alta en la app, registrar su asistencia diaria vía QR, informar su disponibilidad voluntaria cuando corresponda, reportar accidentes laborales, y consultar sus propios datos operativos (schedule, timesheet, pago, perfil).

---

## Acciones Principales

- Completar datos de alta — Fase 2 (RF-C-01)
- Completar datos de emergencia — Fase 3 (RF-C-02)
- Escanear QR y ponchar (6 tipos de ponche) (RF-C-03)
- Activar disponibilidad voluntaria — Amarillo (RF-C-04)
- Reportar accidente laboral desde la app (RF-C-05)
- Consultar Mi Schedule — solo lectura (RF-C-06)
- Consultar Mi Timesheet — solo lectura (RF-C-07)
- Consultar Mi Pago semanal — solo lectura (RF-C-08)
- Consultar notificaciones (RF-C-09)
- Consultar Mi perfil y estado del semáforo (RF-C-10)

---

## Permisos Clave

Ver (solo datos propios) · Crear (alta, ponches, reporte de accidente, activar Amarillo) · Editar limitado (sus datos de perfil y emergencia)

---

## Nivel de Acceso

🟢 Bajo (solo datos propios)

---

## Dispositivo

Mobile + Web (responsive) — el ponche por QR es exclusivo de móvil; el resto de funcionalidades disponibles en ambos canales

---

## Frecuencia de Uso

Alta — diaria
