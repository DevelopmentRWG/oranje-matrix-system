---
tags:
  - arquitectura
  - rol/reclutadora
aliases:
  - Respuestas Sistema Reclutadora
---

# 7. RESPUESTAS DEL SISTEMA — RECLUTADORA

---

| Evento                                        | Respuesta del Sistema                                                                                    |
| --------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Reclutadora toma requisición                  | Cambia estado a "En proceso"; mueve la requisición a "Mis Requisiciones"; semáforo a Amarillo            |
| Envío exitoso de nuevo colaborador            | Mostrar mensaje de confirmación y redirigir a lista de candidatos                                        |
| Error en validación de formulario             | Mostrar mensajes de error claros junto a cada campo inválido                                             |
| Reclutadora valida alta en app                | Notifica al sistema que el colaborador está habilitado; propaga accesos automáticamente                  |
| Habilitación de accesos                       | Crea registro en log; envía credenciales al colaborador por email/SMS                                    |
| Candidato en Blacklist                        | Bloquea envío y registra el intento en el histórico                                                      |
| Asignación exitosa de colaborador a hotel     | Actualiza % de cobertura de la requisición; refleja en Schedule del hotel; notifica al Manager de Área |
| Marcar requisición como cubierta              | Notifica al **Líder de Grupo** para validar cierre                                                       |
| Liberar requisición                           | Devuelve a la bandeja de Autorizadas; notifica disponibilidad                                            |
| Reclutadora reporta problema                  | Escala al Líder de Grupo con contexto del caso                                                           |
| Colaborador asignado pasa a Stand-by (Rosa)   | Notifica a la Reclutadora responsable                                                                    |
| Colaborador asignado entra a Rojo (reportado) | Notifica a la Reclutadora; escala al Inspector                                                           |
| Colaborador asignado tiene accidente laboral  | Notifica a la Reclutadora; estado pasa a Gris (Accidentado)                                              |
