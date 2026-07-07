---
tags:
  - arquitectura
  - rol/colaborador
aliases:
  - Respuestas Sistema Colaborador
---

# 7. RESPUESTAS DEL SISTEMA — COLABORADOR

---

| Evento                                                           | Respuesta del Sistema                                                                                                                                           |
| ---------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Colaborador completa Fase 2 y envía alta                         | Estado transita a → Blanco (pre-validación) · Sistema notifica a la Reclutadora que hay un alta pendiente de revisión · Colaborador ve confirmación: *"Tu alta fue enviada. Te avisaremos cuando sea revisada"* |
| Reclutadora aprueba validación de alta (RF-08)                   | Estado transita Blanco → Verde fuerte · Sistema notifica al colaborador: *"Tu alta fue aprobada. Ya eres parte del pool de colaboradores"* · Accesos habilitados  |
| Reclutadora rechaza o pide corrección de alta                    | Sistema notifica al colaborador: *"Tu alta necesita correcciones. Revisa y actualiza tu información"* · Estado se mantiene en Blanco                             |
| Colaborador completa Fase 3 (datos de emergencia)                | Sistema guarda los datos · Confirmación: *"Datos de emergencia guardados"* · No hay cambio de estado del semáforo (complementario al alta)                       |
| Colaborador escanea QR y poncha Entrada                          | Sistema registra ponche con hora y fecha · Confirmación visual: *"Entrada registrada a las HH:MM"* · Timesheet de la jornada actualizado                        |
| Colaborador poncha Salida Lunch                                  | Sistema registra ponche · Confirma: *"Salida a lunch registrada a las HH:MM"* · Inicia cómputo de tiempo de lunch                                               |
| Colaborador poncha Entrada Lunch                                 | Sistema registra ponche · Cierra cómputo de lunch · Si lunch < 30 min: aplica mínimo de 30 min automáticamente sin notificación adicional al colaborador · Confirma: *"Regreso de lunch registrado a las HH:MM"* |
| Colaborador poncha Salida Break                                  | Sistema registra ponche · Confirma: *"Salida a break registrada a las HH:MM"*                                                                                   |
| Colaborador poncha Entrada Break                                 | Sistema registra ponche · Confirma: *"Regreso de break registrado a las HH:MM"*                                                                                 |
| Colaborador poncha Salida (fin de jornada)                       | Sistema registra ponche · Calcula horas brutas (Salida − Entrada) · Aplica deducción de lunch · Calcula horas netas · Confirma: *"Salida registrada. Horas netas de hoy: X.X hrs"* |
| Jornada cerrada sin ponche de Lunch                              | Sistema aplica auto-deducción de 30 min · Timesheet muestra la deducción automática · Sin notificación especial al colaborador (conforme a [[Reglas del Colaborador#Deducción de Lunch]]) |
| Colaborador intenta ponchar sin Timesheet activo                 | Bloquea acción · Muestra: *"No tienes un turno activo. Comunícate con tu supervisor"* (RR-C-03)                                                                 |
| Colaborador activa Amarillo (disponibilidad voluntaria)          | Estado del semáforo transita a Amarillo · Confirmación: *"Quedaste registrado como disponible. Reclutamiento puede asignarte"* · Colaborador aparece en el Pool como disponible voluntario (RR-C-02) |
| Colaborador desactiva Amarillo                                   | Estado regresa a Verde fuerte · Confirmación: *"Ya no apareces como disponible voluntario"*                                                                     |
| Reclutadora asigna al colaborador (→ Café)                       | Sistema notifica al colaborador: *"Fuiste asignado a [Hotel] del [Fecha inicio] al [Fecha fin]. Revisa tu schedule"* · Estado transita a Café · Schedule y Timesheet habilitados |
| Fin de asignación temporal (Café → Verde fuerte / Amarillo)      | Sistema notifica al colaborador: *"Tu asignación temporal finalizó. Tu estado regresó a [Verde fuerte / Amarillo]"* · Schedule del hotel actualizado             |
| Colaborador reporta accidente laboral                            | Sistema crea tarjeta de accidente · Estado del colaborador transita a Gris (Accidentado) · Sistema notifica simultáneamente al Supervisor del hotel y al Inspector de zona · Colaborador ve confirmación: *"Tu reporte fue enviado. El Inspector de zona recibirá el caso"* · Protección contra regla de 3 inasistencias activada |
| Inspector cierra tarjeta de accidente y hay alta médica          | Estado del colaborador transita Gris → Verde fuerte · Sistema notifica al colaborador: *"Tu tarjeta de accidente fue cerrada. Ya puedes recibir asignaciones"*  |
| Colaborador puesto en Rosa (Stand-by) por el hotel               | Sistema notifica al colaborador: *"El hotel te ha puesto en descanso. Tu estado es Stand-by"* · Sin Schedule ni Timesheet activos · No puede ponchar             |
| Colaborador marcado Morado (no asistió)                          | Sistema notifica al colaborador: *"Se registró una inasistencia en tu expediente"* · Si es la tercera inasistencia: estado a Negro (Blacklist) automático       |
| Colaborador pasa a Negro (Blacklist)                             | Acceso bloqueado · Sistema muestra: *"Tu cuenta ha sido suspendida. Contacta a Oranje para más información"* · Caso visible para Manager de Reclutamiento       |
| Sistema consulta Mi Schedule (RF-C-06)                          | Muestra vista semanal de turnos asignados: hotel, posición, horario, fechas · Solo lectura                                                                       |
| Sistema consulta Mi Timesheet (RF-C-07)                         | Muestra tabla semanal: ponches registrados, horas brutas, deducción de lunch, horas netas · Solo lectura                                                         |
| Sistema consulta Mi Pago (RF-C-08)                              | Muestra el **historial de pagos liberados**; la semana en curso aparece "En cálculo" sin monto. El monto del próximo pago no se revela hasta que Contabilidad lo libere (RR-C-05). |
| Sesión iniciada                                                  | Redirige a Dashboard con estado del semáforo visible y próximo turno (si tiene asignación activa)                                                                |
| Sesión expirada                                                  | Redirige a login; muestra: *"Tu sesión ha expirado, por favor inicia sesión nuevamente"*                                                                         |
| Error en validación de formulario                                | Muestra mensajes de error claros junto a cada campo inválido · Sin interrumpir el progreso del formulario en campos ya completados                               |
