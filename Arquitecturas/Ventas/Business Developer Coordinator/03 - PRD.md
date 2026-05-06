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

| Campo                   | Contenido                                                                |
| ----------------------- | ------------------------------------------------------------------------ |
| **ID del PRD**          | PRD-VENTAS-03                                                            |
| **Historia de Usuario** | HU-VENTAS-03                                                             |
| **Departamento**        | Ventas                                                                   |
| **Funcionalidad**       | Validar T&C, aprobar conversiones, supervisar BDs, gestionar casos especiales |
| **Actor Principal**     | Business Developer Coordinator (BDC)                                     |
| **Dispositivo**         | Web – Desktop / Tablet                                                   |
| **Estado**              | En definición                                                            |
| **Versión**             | 1.0                                                                      |

---

## Objetivo

Permitir al BDC **validar la calidad** de cada T&C antes del cierre, **aprobar la conversión final** del prospecto a cliente, **supervisar al equipo de BDs** y **gestionar los casos especiales** (Café, Negro). Es el rol que custodia la calidad de la entrada de clientes al sistema.

---

## Flujo General

**Reviso T&C pendiente → Valido o rechazo → Negocio (Rosa) junto al BD → Creo Usuario del Hotel → Apruebo conversión → Trigger Automático → Cliente activo (Naranja) | Paralelo: gestiono casos Café y Negro, supervisó al equipo, genero reportes**

---

## Casos de Uso

| ID | Caso de Uso | Prioridad |
|---|---|---|
| RF-V-08 | Crear Documento de T&C (apoyo) | 🔴 Alta |
| RF-V-09 | Iniciar negociación (Rosa) | 🔴 Alta |
| RF-V-10 | Validar T&C | 🔴 Alta |
| RF-V-11 | Crear Usuario del Hotel | 🔴 Alta |
| RF-V-12 | Aprobar conversión a cliente | 🔴 Alta |
| RF-V-17 | Marcar estancamiento (Café) | 🟡 Media |
| RF-V-18 | Desbloquear estancamiento | 🟡 Media |
| RF-V-19 | Reactivar desde Café | 🟡 Media |
| RF-V-20 | Marcar cliente Negro | 🟡 Media |
| RF-V-21 | Reactivar desde Negro | 🟢 Baja |
| RF-V-22 | Ver Pipeline (global) | 🔴 Alta |
| RF-V-24 | Ver Mi Equipo | 🔴 Alta |
| RF-V-25 | Métricas individuales por BD | 🟡 Media |
| RF-V-26 | Generar reporte de Ventas | 🟡 Media |
| RF-V-27 | Enviar reporte a dirección | 🟡 Media |
| RF-V-29 | Ver Clientes Activos | 🟡 Media |

---

## Reglas de Negocio Aplicables

- **RR-V-01:** Conversión exclusiva del BDC.
- **RR-V-02:** Precondición de conversión — Usuario del Hotel.
- **RR-V-03:** Trigger Automático ejecuta 3 acciones en paralelo.
- **RR-V-04:** Desbloqueo de Café exclusivo del BDC.
- **RR-V-05:** Gestión de Negro exclusiva del BDC.
- **RR-V-07:** Reactivaciones siempre a Azul Claro.
- **RR-V-15:** Contrato resulta del cierre exitoso en Rosa.

---

## Restricciones / Permisos

- NO identifica prospectos (eso es del BD).
- NO elabora Propuesta Personalizada (BD exclusivo).
- NO gestiona Rojo (BD exclusivo).
- NO accede a la operación post-Naranja.
