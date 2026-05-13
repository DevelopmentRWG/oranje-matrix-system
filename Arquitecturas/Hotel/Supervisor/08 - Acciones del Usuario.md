---
tags:
  - arquitectura
  - rol/supervisor-hotel
aliases:
  - Acciones Supervisor
---

# 6. ACCIONES DEL USUARIO — SUPERVISOR

---

| Acción                                                  | Resultado                                                                                                |
| ------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Crear nueva requisición                                  | Sistema asigna número auto (AAAAMMDDHHMM + Homoclave) · Estado Verde manzana — En elaboración (borrador) |
| Editar borrador / requisición rechazada                  | Cambios persisten · Estado se mantiene                                                                    |
| Enviar requisición a autorización                        | Envío al Manager de Área · Estado pasa a Verde manzana — pendiente de autorización · Notificación      |
| Eliminar borrador                                        | Eliminación física automática sin journal (RR-H-07)                                                      |
| Sugerir refuerzo de personal                             | Modal de nueva requisición pre-llenado con datos de la posición vacante                                  |
| Reportar accidente — Escenario A                         | Captura presencial · Tarjeta con datos, testigos, atención · Notifica al Inspector                       |
| Reportar accidente — Escenario B                         | Crea tarjeta con datos del accidente · Estado del colaborador a Gris · Notifica al Inspector             |
| Adjuntar evidencia presencial al accidente               | Sube foto / video / nota · Queda asociada a la tarjeta                                                  |
| Poner colaborador en Stand-by (Rosa)                     | Estado en Semáforo del Colaborador a Rosa · Sin Schedule ni Timesheet · Notifica al colaborador         |
| Quitar Stand-by                                           | Reactiva al colaborador en Schedule y Timesheet                                                          |
| Consultar Schedule del depto                             | Vista calendario semanal con asignaciones                                                                |
| Consultar Timesheet del depto                            | Tabla semanal × colaborador con ponches y horas netas                                                    |
| Consultar Blacklist                                      | Vista lectura con motivo y fecha del veto                                                                |
| Cancelar acción                                          | Cambios no se guardan                                                                                     |
