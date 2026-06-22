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
| Reclutadora toma requisición                  | Cambia estado a "En proceso"; la agrega a "Mis Requisiciones"; semáforo a Amarillo; la registra como reclutador participante en el Historial (no bloquea a las demás) |
| Reclutadora se une a requisición ya tomada    | La agrega como reclutador participante adicional sin desplazar a nadie ni retroceder el semáforo; registra el evento en el Historial con autor; notifica a los demás participantes |
| Envío exitoso de nuevo colaborador            | Mostrar mensaje de confirmación y redirigir a lista de candidatos                                        |
| Error en validación de formulario             | Mostrar mensajes de error claros junto a cada campo inválido                                             |
| Reclutadora valida alta en app                | Notifica al sistema que el colaborador está habilitado; propaga accesos automáticamente                  |
| Habilitación de accesos                       | Crea registro en log; envía credenciales al colaborador por email/SMS                                    |
| Candidato en Blacklist                        | Bloquea envío y registra el intento en el histórico                                                      |
| Asignación exitosa de colaborador a hotel     | Actualiza el % de cobertura compartido de la requisición; refleja en Schedule del hotel; notifica al Manager de Área; registra en el Historial qué colaborador se asignó a qué posición, con autor y fecha |
| Marcar requisición como cubierta              | Notifica al **Líder de Grupo** para validar cierre; registra el cierre en el Historial con autor          |
| Salir de la requisición                       | Retira solo a la reclutadora que sale; la requisición sigue En proceso si quedan otros reclutadores y no resetea lo asignado; vuelve a Autorizada solo cuando sale el último reclutador; registra el evento en el Historial con autor |
| Reclutadora reporta problema                  | Escala al Líder de Grupo con contexto del caso                                                           |
| Colaborador asignado pasa a Stand-by (Rosa)   | Notifica a la Reclutadora responsable                                                                    |
| Colaborador asignado entra a Rojo (reportado) | Notifica a la Reclutadora; escala al Inspector                                                           |
| Colaborador asignado tiene accidente laboral  | Notifica a la Reclutadora; estado pasa a Gris (Accidentado)                                              |
