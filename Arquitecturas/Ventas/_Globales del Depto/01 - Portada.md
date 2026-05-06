---
tags:
  - arquitectura
  - departamento/ventas
aliases:
  - Portada Ventas
  - Departamento de Ventas (Portada)
---

# GESTIÓN DE ROLES – DEPARTAMENTO DE VENTAS

**Plantilla de Roles y Perfiles de Usuario**

---

| Campo            | Contenido                          |
| ---------------- | ---------------------------------- |
| **Documento**    | Plantilla de Roles – Ventas        |
| **Departamento** | Ventas                             |
| **Relacionado**  | PRD-VENTAS-01 · HU-VENTAS-01       |
| **Versión**      | 1.0                                |
| **Estado**       | En definición                      |

---

## ROLES DEFINIDOS EN ESTE DOCUMENTO

| ID           | Rol · Descripción breve                                                                                                                                                |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **ROL-V-01** | 🤝 **Business Developer (BD)** — Ejecutor comercial en campo. Identifica prospectos, elabora propuestas, hace seguimiento, gestiona rechazos.                          |
| **ROL-V-02** | 🧑‍💼 **Business Developer Coordinator (BDC)** — Supervisa rutas y zonas. Valida términos, aprueba conversiones, gestiona estancamientos y clientes pausados. *Sí final.* |
| **ROL-V-03** | ⚙️ **Sistema** — Automatización: Trigger Automático de Conversión (3 acciones paralelas), trazabilidad de cambios de status, notificaciones, semáforos.                 |
| **ROL-V-04** | 🛠️ **Administrador** — Gestión total del sistema: usuarios, catálogos, permisos. *(En pausa hasta que se estabilicen reglas de negocio.)*                              |

---

## Estructura del depto

- El BD opera por **territorio asignado** (rutas y zonas).
- El BDC supervisa varias rutas/zonas y a sus BDs.
- Jerarquía: **BDC → BD**.

> [!info]
> El depto Ventas es responsable del **onboarding comercial del hotel** (pre-cliente). Una vez el hotel alcanza el status **Naranja** del Semáforo Onboarding, pasa a operación de [[Reclutamiento/Reclutamiento|Reclutamiento]] e [[Inspección/Inspección|Inspección]]. BD y BDC quedan como **referentes comerciales** post-conversión.
