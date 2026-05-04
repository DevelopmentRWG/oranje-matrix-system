---
tags:
  - arquitectura
  - rol/manager-del-hotel
aliases:
  - Permisos Detallados Manager del Hotel
---

# PERMISOS DETALLADOS POR ROL

## ROL-H-02 · 🧑‍💼 Manager del Hotel / Gerente de Departamento

---

| Módulo                | Funcionalidad                                       | Permiso       | Descripción                                                                  |
| --------------------- | --------------------------------------------------- | ------------- | ---------------------------------------------------------------------------- |
| **Requisiciones**     | Ver requisiciones del depto                         | 👁️ Ver        | Vista por estado (pendientes, autorizadas, en proceso, cubiertas, rechazadas) |
| Requisiciones         | Autorizar requisición                                | ✓ Aprobar     | Acción exclusiva — capa de seguridad (RR-H-02)                              |
| Requisiciones         | Rechazar con observaciones                          | ✗ Rechazar    | Devuelve al Supervisor con motivo                                            |
| Requisiciones         | Eliminar requisición con posiciones                 | 📝 C · E      | Cada posición pasa a Morado con journal individual (RR-H-08)                |
| **Schedule**          | Ver Schedule del depto                              | 👁️ Ver        | Calendario semanal completo del depto                                        |
| Schedule              | Editar Schedule semanal                             | 📝 C · E      | Reordena turnos, mueve colaboradores entre días, marca descansos            |
| Schedule              | Exportar Schedule                                    | 👁️ Ver        | PDF / CSV                                                                     |
| **Timesheet**         | Ver Timesheet del depto                             | 👁️ Ver        | Tabla semanal con 6 ponches por jornada                                       |
| Timesheet             | Generar / Renovar QR                                 | ➕ Crear       | Acción exclusiva (RR-H-09)                                                   |
| Timesheet             | Corregir ponche                                      | 📝 C · E      | Con justificación obligatoria — log auditable                                |
| Timesheet             | Ver Indicador de Cumplimiento                       | 👁️ Ver        | Semaforizado por colaborador y jornada                                       |
| Timesheet             | Ver Indicador de Lunch Extendido                    | —             | Sin acceso (RR-H-15)                                                         |
| Timesheet             | Exportar Timesheet                                   | 👁️ Ver        | PDF / CSV                                                                     |
| **Mi Personal**       | Ver colaboradores asignados                          | 👁️ Ver        | Lista con Semáforo del Colaborador                                           |
| Mi Personal           | Poner colaborador en Stand-by (Rosa)                 | 📝 C · E      | Compartido con Supervisor (RR-H-11)                                          |
| Mi Personal           | Reportar colaborador (Rojo)                          | 🚨 Reportar   | Acción exclusiva (RR-H-10)                                                  |
| Mi Personal           | Ver historial del colaborador                       | 👁️ Ver        | Asignaciones previas + incidencias                                           |
| **Dashboard**         | Ver KPIs del depto                                   | 👁️ Ver        | Cobertura, requisiciones, accidentes, cumplimiento                          |
| **Blacklist**         | Consultar Blacklist                                  | 👁️ Ver        | Solo consulta — sin acción                                                   |
| Blacklist             | Agregar / Remover                                    | —             | Sin acceso (exclusivo del depto Reclutamiento)                              |
| **Sistema** (transv.) | Recibir notificación                                 | 👁️ Ver        | Alertas críticas y notificaciones automáticas                               |
