---
tags:
  - arquitectura
  - departamento/ventas
aliases:
  - PRD del Depto Ventas
---

# DOCUMENTO DE REQUISITOS DE PRODUCTO
## PRD – VENTAS

**Sistema de Gestión de Personal · Departamento de Ventas**

---

| Campo | Contenido |
|---|---|
| **ID del PRD** | PRD-VENTAS-01 |
| **Historia de Usuario** | HU-VENTAS-01 |
| **Departamento** | Ventas |
| **Funcionalidad** | Gestionar el ciclo comercial de captación de hoteles desde su identificación hasta la conversión en cliente activo |
| **Actor Principal** | Business Developer · Business Developer Coordinator |
| **Dispositivo** | Web – Desktop / Mobile (BD en campo) |
| **Estado** | En definición |
| **Versión** | 1.0 |

---

## Objetivo

Permitir al equipo comercial **identificar, contactar, proponer y convertir hoteles prospectos en clientes activos** de Oranje, siguiendo el [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]]. El depto Ventas es la **puerta de entrada** del cliente al sistema: nada opera (Reclutamiento, Schedule, Timesheet) sin que Ventas haya cerrado el onboarding (status Naranja).

---

## Alcance

**Incluye:**
- Identificación de prospectos por territorio.
- Recopilación de datos y visita en frío.
- Elaboración y envío de Propuesta Personalizada.
- Creación y validación del Documento de Términos y Condiciones.
- Negociación de términos.
- Aprobación final y conversión a cliente (BDC exclusivo).
- Trigger Automático de Conversión (3 acciones paralelas).
- Gestión de rechazos (Rojo), estancamientos (Café) y clientes pausados (Negro).
- Reactivaciones (siempre a Azul Claro).
- Supervisión de territorio y desempeño de BDs (BDC).
- Reportes ejecutivos.
- Trazabilidad de cambios de status.

**Fuera del alcance:**
- Operación post-Naranja (Reclutamiento, Schedule, Timesheet) — pasa al depto Hotel y Reclutamiento.
- Inspección operativa (módulo Inspección).
- Auditoría de calidad (módulo QA — observa, no opera).
- Configuración del sistema (Administrador — en pausa).

---

## Flujo General

**Identificar prospecto (Gris) → Recopilar datos y visita (Azul Claro) → Enviar Propuesta (Verde) → Seguimiento (Amarillo) → Negociar (Rosa) → BDC aprueba conversión + crea Usuario del Hotel + Trigger Automático → Cliente activo (Naranja) → Hotel pasa a operaciones**

```
GRIS (BD)
  ↓
AZUL CLARO (BD)
  ↓
VERDE (BD) — Propuesta Personalizada
  ↓
AMARILLO (BD + BDC apoyo) — Documento T&C
  ↓
ROSA (BD + BDC) — Negociación
  ↓ (BDC aprueba)
NARANJA — Trigger Automático → Hotel cliente activo

Ramas alternas:
  • ROJO (BD) — Rechazo → reactivar a Azul Claro
  • CAFÉ (BDC) — Estancamiento → desbloquear a Azul Claro
  • NEGRO (BDC) — Cliente pausado → reactivar a Azul Claro
```

---

## Actores

| Actor                          | Tipo           | Responsabilidad principal                                   |
| ------------------------------ | -------------- | ----------------------------------------------------------- |
| Business Developer (BD)        | Operativo      | Identifica, propone, da seguimiento, gestiona rechazos      |
| Business Developer Coordinator | Supervisor     | Valida T&C, aprueba conversión, gestiona Café y Negro       |
| Sistema                        | Automatización | Trigger automático, trazabilidad, notificaciones, semáforos |
| Administrador *(en pausa)*     | Configuración  | Usuarios, catálogos, permisos                               |

---

## Restricciones / Reglas de negocio aplicables

Ver [[07 - Reglas de Negocio]] para el detalle. Las más importantes:

- **RR-V-01:** Solo el BDC aprueba la conversión.
- **RR-V-02:** Precondición — Usuario del Hotel creado antes del Trigger.
- **RR-V-03:** Trigger Automático ejecuta 3 acciones en paralelo.
- **RR-V-04:** Solo el BDC desbloquea estancamiento (Café).
- **RR-V-08:** Naranja es el único status que habilita generar requisiciones.

---

## Integraciones (RI)

| ID      | Integración               | Descripción                                                                          |
| ------- | ------------------------- | ------------------------------------------------------------------------------------ |
| RI-V-01 | Ventas ↔ Hotel            | Al alcanzar Naranja, el hotel se habilita en el módulo Hotel (genera requisiciones). |
| RI-V-02 | Ventas ↔ Reclutamiento    | El hotel cliente activo recibe Reclutadoras y Líderes para cubrir requisiciones.     |
| RI-V-03 | Ventas ↔ Inspección       | Al activarse, el hotel queda asignado a un Inspector por zona.                       |
| RI-V-04 | Ventas ↔ Contrato         | El cierre en Rosa genera el Contrato con T&C validado.                               |
| RI-V-05 | Ventas ↔ Sistema de Email | Trigger automático envía email de bienvenida al hotel.                               |
| RI-V-06 | Ventas ↔ QA               | Operador de QA fijo asignado al depto. Métricas e Indicador de Calidad.              |

---

## Dependencias

Ver [[09 - Dependencias]] para el detalle.

- Depende del [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]] como columna vertebral del proceso.
- Depende del [[Core/Módulos/Contrato|Contrato]] como artefacto generado al cierre.
- Depende de [[Hotel/Hotel|Hotel]] como destino final del onboarding.
- Depende de [[Reclutamiento/Reclutamiento|Reclutamiento]] e [[Inspección/Inspección|Inspección]] como receptores post-Naranja.
- Depende de [[QA/QA|QA]] como observador del depto.
