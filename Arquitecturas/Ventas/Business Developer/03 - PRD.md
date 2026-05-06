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

| Campo                   | Contenido                                                                |
| ----------------------- | ------------------------------------------------------------------------ |
| **ID del PRD**          | PRD-VENTAS-02                                                            |
| **Historia de Usuario** | HU-VENTAS-02                                                             |
| **Departamento**        | Ventas                                                                   |
| **Funcionalidad**       | Ejecutar el ciclo comercial con hoteles prospecto en el territorio asignado |
| **Actor Principal**     | Business Developer (BD)                                                  |
| **Dispositivo**         | Mobile (prioritario) / Tablet / Desktop                                  |
| **Estado**              | En definición                                                            |
| **Versión**             | 1.0                                                                      |

---

## Objetivo

Permitir al Business Developer **identificar, contactar, proponer y dar seguimiento** a hoteles prospecto en su territorio asignado, llevándolos a través del Semáforo Onboarding hasta el status Rosa, donde el BDC toma la conversión final.

---

## Flujo General

**Identifico prospecto (Gris) → Recopilo datos + visita en frío (Azul Claro) → Elaboro y envío Propuesta (Verde) → Seguimiento (Amarillo) → Creo T&C → Negocio con BDC (Rosa) → BDC aprueba → Naranja (cliente activo) → Quedo como referente comercial**

---

## Casos de Uso

| ID | Caso de Uso | Prioridad |
|---|---|---|
| RF-V-01 | Identificar prospecto (Gris) | 🔴 Alta |
| RF-V-02 | Crear perfil del hotel (Azul Claro) | 🔴 Alta |
| RF-V-03 | Registrar visita en frío | 🟡 Media |
| RF-V-04 | Elaborar Propuesta Personalizada | 🔴 Alta |
| RF-V-05 | Enviar propuesta al hotel | 🔴 Alta |
| RF-V-06 | Registrar intentos de contacto | 🟡 Media |
| RF-V-07 | Avanzar a Amarillo (interés) | 🔴 Alta |
| RF-V-08 | Crear Documento de T&C | 🔴 Alta |
| RF-V-09 | Iniciar negociación (Rosa) | 🔴 Alta |
| RF-V-15 | Gestionar rechazo (Rojo) | 🟡 Media |
| RF-V-16 | Reactivar prospecto desde Rojo | 🟡 Media |
| RF-V-17 | Marcar estancamiento (Café) | 🟡 Media |
| RF-V-22 | Ver Pipeline | 🔴 Alta |
| RF-V-23 | Ver Mi Territorio | 🔴 Alta |
| RF-V-29 | Ver Clientes Activos (referente) | 🟡 Media |

---

## Reglas de Negocio Aplicables

- **RR-V-01:** El BD NO aprueba conversión (eso es del BDC).
- **RR-V-04:** El BD puede marcar Café, pero NO desbloquearlo.
- **RR-V-06:** El BD gestiona los rechazos (Rojo).
- **RR-V-07:** Reactivaciones desde Rojo regresan a Azul Claro.
- **RR-V-09:** Propuesta Personalizada solo en Verde.
- **RR-V-12:** Post-Naranja, BD es referente comercial sin operación.

---

## Restricciones / Permisos

- NO valida T&C (eso es del BDC).
- NO crea Usuario del Hotel.
- NO aprueba conversión.
- NO desbloquea Café.
- NO gestiona Negro.
- Solo ve prospectos de SU territorio.
- NO accede a métricas de otros BDs.
- NO genera reportes ejecutivos.
