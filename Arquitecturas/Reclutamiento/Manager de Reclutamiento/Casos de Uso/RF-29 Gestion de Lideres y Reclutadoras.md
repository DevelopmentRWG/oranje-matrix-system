---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - CU RF-29
---

# 🪪 ID: RF-29
🏷️ **Nombre:** Gestión de Líderes y Reclutadoras (CRUD)

**Historia:**
El Manager es el único rol que puede dar de alta, editar, mover entre grupos o desactivar a Líderes de Grupo y Reclutadoras del depto. La gestión vive en el módulo "Mi Equipo" y abarca cinco subcasos: alta de Líder, alta de Reclutadora, edición, mover Reclutadora a otro Líder y baja (inactivo / vacaciones / despido).

**Criterios de aceptación:**
Solo el Manager puede ejecutar la acción (regla RR-10). Toda alta crea cuenta + envía credenciales en menos de 1 min. Toda edición / movimiento / baja queda registrada en log auditable. La baja es lógica (no se borra el histórico). Al mover una Reclutadora, ambos Líderes (origen y destino) reciben notificación.

**Documentación:**
- PRD: PRD-RECL-03 Manager
- Flow: Gestión de Equipo
- Prototipo: (link de Figma)

**Flujo:**

### Subcaso 1 — Dar de alta Líder de Grupo
`Módulo Mi Equipo` → MANUAL → `Click "Nuevo usuario"` → `Selecciona rol: Líder de Grupo` → `Llena formulario (nombre, correo, zona, idioma)` → `Confirmar` → AUTOMATICO → `Sistema crea cuenta con rol asignado + Envía credenciales por correo + Registra en log`

### Subcaso 2 — Dar de alta Reclutadora
`Módulo Mi Equipo` → MANUAL → `Click "Nuevo usuario"` → `Selecciona rol: Reclutadora` → `Llena formulario + asigna Líder de Grupo + asigna zona` → `Confirmar` → AUTOMATICO → `Sistema crea cuenta + Asigna al Líder seleccionado + Envía credenciales + Notifica al Líder`

### Subcaso 3 — Editar usuario
`Módulo Mi Equipo` → MANUAL → `Selecciona usuario` → `Click "Editar"` → `Modifica campos (rol / zona / grupo / estado)` → `Confirmar` → AUTOMATICO → `Sistema aplica cambios + Notifica al usuario y a Líder afectado + Registra en log`

### Subcaso 4 — Mover Reclutadora a otro Líder
`Módulo Mi Equipo → Detalle Reclutadora` → MANUAL → `Click "Mover de grupo"` → `Selecciona nuevo Líder + motivo` → `Confirmar` → AUTOMATICO → `Reclutadora cambia de grupo + Notifica a Líder origen y destino + Registra en log`

### Subcaso 5 — Marcar inactivo / vacaciones / baja
`Módulo Mi Equipo → Detalle usuario` → MANUAL → `Click "Cambiar estado"` → `Selecciona estado (Inactivo / Vacaciones / Baja) + justificación` → `Confirmar` → AUTOMATICO → `Sistema desactiva accesos correspondientes + Reasigna requisiciones activas si aplica + Registra en log`
