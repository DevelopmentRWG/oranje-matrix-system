---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - UC RF-29
---

# 🪪 ID: RF-29
🏷️ **Name:** Management of Leaders and Recruiters (CRUD)

**Story:**
The Manager is the only role that can create, edit, move between groups or deactivate Group Leaders and Recruiters in the department. The management lives in the "My Team" module and covers five subcases: Leader creation, Recruiter creation, editing, moving a Recruiter to another Leader and removal (inactive / vacation / termination).

**Acceptance criteria:**
Only the Manager can execute the action (rule RR-10). Every creation creates an account + sends credentials in under 1 min. Every edit / move / removal is recorded in an auditable log. The removal is logical (the history is not deleted). When a Recruiter is moved, both Leaders (origin and destination) receive a notification.

**Documentation:**
- PRD: PRD-RECL-03 Manager
- Flow: Team Management
- Prototype: (Figma link)

**Flow:**

### Subcase 1 — Create Group Leader
`Módulo Mi Equipo` → MANUAL → `Click "Nuevo usuario"` → `Selecciona rol: Líder de Grupo` → `Llena formulario (nombre, correo, zona, idioma)` → `Confirmar` → AUTOMATICO → `Sistema crea cuenta con rol asignado + Envía credenciales por correo + Registra en log`

### Subcase 2 — Create Recruiter
`Módulo Mi Equipo` → MANUAL → `Click "Nuevo usuario"` → `Selecciona rol: Reclutadora` → `Llena formulario + asigna Líder de Grupo + asigna zona` → `Confirmar` → AUTOMATICO → `Sistema crea cuenta + Asigna al Líder seleccionado + Envía credenciales + Notifica al Líder`

### Subcase 3 — Edit user
`Módulo Mi Equipo` → MANUAL → `Selecciona usuario` → `Click "Editar"` → `Modifica campos (rol / zona / grupo / estado)` → `Confirmar` → AUTOMATICO → `Sistema aplica cambios + Notifica al usuario y a Líder afectado + Registra en log`

### Subcase 4 — Move Recruiter to another Leader
`Módulo Mi Equipo → Detalle Reclutadora` → MANUAL → `Click "Mover de grupo"` → `Selecciona nuevo Líder + motivo` → `Confirmar` → AUTOMATICO → `Reclutadora cambia de grupo + Notifica a Líder origen y destino + Registra en log`

### Subcase 5 — Mark inactive / vacation / removal
`Módulo Mi Equipo → Detalle usuario` → MANUAL → `Click "Cambiar estado"` → `Selecciona estado (Inactivo / Vacaciones / Baja) + justificación` → `Confirmar` → AUTOMATICO → `Sistema desactiva accesos correspondientes + Reasigna requisiciones activas si aplica + Registra en log`
