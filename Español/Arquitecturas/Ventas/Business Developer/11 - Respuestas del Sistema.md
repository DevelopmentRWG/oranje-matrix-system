---
tags:
  - arquitectura
  - rol/business-developer
aliases:
  - Respuestas Sistema Business Developer
---

# 7. RESPUESTAS DEL SISTEMA — BUSINESS DEVELOPER

---

| Evento                             | Respuesta del Sistema                                                                              |
| ---------------------------------- | -------------------------------------------------------------------------------------------------- |
| BD identifica prospecto            | Crea registro en Gris · Aparece en mi Pipeline · Captura geolocalización si es desde mobile        |
| BD crea perfil del hotel           | Status pasa a Azul Claro · Notificación al BDC del avance                                          |
| BD registra visita en frío         | Visita queda en histórico · Si marca "próximo seguimiento", crea recordatorio                      |
| BD elabora Propuesta Personalizada | Se crea borrador · Permite editar libremente                                                       |
| BD envía propuesta al hotel        | Status pasa a Verde · Notifica al BDC · Email con propuesta enviado al hotel                       |
| Hotel responde con interés         | BD avanza a Amarillo · Notifica al BDC · Permite empezar T&C                                       |
| BD crea Documento de T&C           | Borrador con campos obligatorios listos para llenar                                                |
| BD envía T&C al BDC                | Notifica al BDC · Documento queda pendiente de validación                                          |
| BDC valida T&C                     | Notifica al BD: *"Tu T&C fue validado"* · Permite avanzar a Rosa                                   |
| BDC rechaza T&C                    | Notifica al BD con observaciones · BD corrige y reenvía                                            |
| BD inicia negociación (Rosa)       | Status pasa a Rosa · Notifica al BDC · Trazabilidad en la línea de tiempo                          |
| BDC aprueba conversión             | Notifica al BD: *"Tu prospecto se convirtió en cliente activo"* · Status pasa a Naranja            |
| Trigger Automático ejecuta         | Email de bienvenida al hotel · Notif al BD · Hotel sale del Pipeline · Aparece en Clientes Activos |
| BD marca Rojo (rechazo)            | Status pasa a Rojo · Notifica al BDC · Queda registrado con motivo                                 |
| BD reactiva desde Rojo             | Status regresa a Azul Claro · Histórico mantiene el rechazo                                        |
| BD marca Café                      | Status pasa a Café · Notifica al BDC para que desbloquee · BD ya no puede modificar este prospecto |
| BDC desbloquea Café                | Notifica al BD: *"Tu prospecto fue desbloqueado por [BDC]"* · Status regresa a Azul Claro          |
| BD intenta acción sin permiso      | Botón no aparece · Si intenta vía URL, mensaje: *"No tienes permiso para esta acción"*             |
| Sesión iniciada                    | Redirige a Dashboard · Carga KPIs personales · Lista próximos seguimientos                         |
| Sesión expirada                    | Redirige a login                                                                                   |
| Error en validación de formulario  | Muestra mensajes de error claros junto a cada campo inválido                                       |
