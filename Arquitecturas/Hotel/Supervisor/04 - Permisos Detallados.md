---
tags:
  - arquitectura
  - rol/supervisor-hotel
aliases:
  - Permisos Detallados Supervisor
---

# PERMISOS DETALLADOS POR ROL

## ROL-H-01 · 🦺 Supervisor (SUP)

---

| Módulo                | Funcionalidad                                       | Permiso     | Descripción                                                       |
| --------------------- | --------------------------------------------------- | ----------- | ----------------------------------------------------------------- |
| **Requisiciones**     | Ver mis requisiciones                                | 👁️ Ver     | Filtrado por las que yo creé                                      |
| Requisiciones         | Ver vista global del hotel                           | —           | Sin acceso (solo Manager de Área y Manager General)             |
| Requisiciones         | Crear requisición                                    | ➕ Crear     | Acción principal del rol                                          |
| Requisiciones         | Editar borrador                                      | 📝 C · E    | Edición libre antes de enviar                                     |
| Requisiciones         | Enviar a autorización                                | ➕ Crear     | Envía al Manager de Área                                        |
| Requisiciones         | Eliminar borrador                                    | ➕ Crear     | Auto si requisición vacía (RR-H-07)                               |
| Requisiciones         | Autorizar                                            | —           | Sin acceso (RR-H-02)                                              |
| Requisiciones         | Rechazar                                             | —           | Sin acceso                                                        |
| **Schedule**          | Ver Schedule del depto                              | 👁️ Ver     | Vista calendario semanal del depto                                |
| Schedule              | Editar Schedule                                      | —           | Sin acceso (solo Manager de Área)                               |
| Schedule              | Sugerir refuerzo de personal                         | ➕ Crear     | Genera prefill de nueva requisición desde posición vacante         |
| Schedule              | Exportar Schedule                                    | 👁️ Ver     | PDF / CSV                                                          |
| **Timesheet**         | Ver Timesheet del depto                              | 👁️ Ver     | Tabla semanal × colaborador con 6 ponches                         |
| Timesheet             | Generar QR                                           | —           | Sin acceso (RR-H-09)                                              |
| Timesheet             | Corregir ponche                                      | —           | Sin acceso (solo Manager de Área)                               |
| Timesheet             | Ver Indicador de Cumplimiento                       | 👁️ Ver     | Semaforizado por colaborador                                       |
| Timesheet             | Ver Indicador de Lunch Extendido                    | —           | Sin acceso (RR-H-15)                                              |
| Timesheet             | Exportar Timesheet                                   | 👁️ Ver     | PDF / CSV                                                          |
| **Mi Personal**       | Ver colaboradores asignados                          | 👁️ Ver     | Lista del depto                                                   |
| Mi Personal           | Poner colaborador en Stand-by (Rosa)                 | 📝 C · E    | Compartido con Manager de Área y Manager General (RR-H-11)        |
| Mi Personal           | **Reportar colaborador (Rojo)**                      | 🚨 Reportar | **NUEVO** — Compartido con Manager de Área y Manager General (RR-H-10)|
| Mi Personal           | Ver historial del colaborador                       | 👁️ Ver     | Asignaciones e incidencias                                        |
| **Accidentes**        | Ver accidentes del depto                             | 👁️ Ver     | Lista de casos abiertos y cerrados                                |
| Accidentes            | Reportar accidente — Escenario A                    | ➕ Crear     | Captura presencial tras notificación simultánea con Inspector     |
| Accidentes            | Reportar accidente — Escenario B                    | ➕ Crear     | Crea tarjeta cuando detecta primero                               |
| Accidentes            | Capturar evidencia presencial                       | 📝 C · E    | Foto / video / notas                                              |
| **Dashboard**         | Ver KPIs personales                                  | 👁️ Ver     | Mis requisiciones, accidentes reportados                          |
| **Sistema** (transv.) | Recibir notificación                                 | 👁️ Ver     | Alertas y notificaciones                                          |
