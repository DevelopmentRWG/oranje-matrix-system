---
tags:
  - arquitectura
  - rol/supervisor-hotel
aliases:
  - Respuestas Sistema Supervisor
---

# 7. RESPUESTAS DEL SISTEMA — SUPERVISOR

---

| Evento                                                | Respuesta del Sistema                                                                                                |
| ----------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Supervisor crea requisición                            | Asigna número auto (AAAAMMDDHHMM + Homoclave) · Estado borrador (Verde manzana) · Permite editar libremente            |
| Supervisor envía requisición a autorización            | Estado pasa a Verde manzana — pendiente de autorización · Notifica al Manager del Hotel · Visible en su bandeja      |
| Manager del Hotel autoriza                            | Notifica al Supervisor: *"Tu requisición fue autorizada y enviada a Reclutamiento"* · Estado cambia a Autorizada     |
| Manager del Hotel rechaza con observaciones           | Notifica al Supervisor: *"Tu requisición fue rechazada"* · Observaciones visibles en el detalle · Estado vuelve a En elaboración |
| Supervisor edita borrador o rechazada                 | Cambios persisten · Estado se mantiene                                                                                |
| Supervisor elimina borrador                            | Eliminación física automática sin journal · Sin confirmación necesaria                                                |
| Sistema elimina físicamente requisición vacía          | Sin journal · Automático al salir del editor                                                                          |
| Reclutamiento toma una requisición                    | Notifica al Supervisor: *"Tu requisición fue tomada por [Reclutadora]"* · Estado pasa a En proceso                    |
| Reclutamiento asigna colaborador                      | Notifica al Supervisor · Colaborador aparece en el Schedule · Actualiza % cobertura                                  |
| Requisición queda cubierta al 100%                    | Notifica al Supervisor: *"Tu requisición fue cubierta al 100%"* · Estado a Cubierta                                  |
| Supervisor reporta accidente — Escenario A            | Tarjeta creada con captura presencial · Notifica al Inspector de zona · Estado del colaborador a Gris (RR-H-20)      |
| Supervisor reporta accidente — Escenario B            | Tarjeta creada · Notifica al Inspector · Estado del colaborador a Gris                                                |
| Inspector inicia investigación del accidente          | Notifica al Supervisor del avance del caso                                                                            |
| Caso de accidente cerrado                              | Notifica al Supervisor con resolución                                                                                  |
| Supervisor pone colaborador en Stand-by (Rosa)        | Estado a Rosa · Sin Schedule ni Timesheet · Notifica al colaborador y al Manager del Hotel                            |
| Supervisor sugiere refuerzo de personal               | Modal de nueva requisición pre-llenado con datos de la posición vacante                                              |
| Supervisor consulta Schedule                          | Vista calendario semanal con asignaciones del depto                                                                    |
| Supervisor consulta Timesheet                         | Tabla semanal con ponches del depto                                                                                    |
| Sesión iniciada                                        | Redirige a Dashboard con bandeja de "necesita acción" priorizada                                                       |
| Sesión expirada                                        | Redirige a login                                                                                                       |
| Error en validación de formulario                     | Muestra mensajes de error claros junto a cada campo inválido                                                          |
