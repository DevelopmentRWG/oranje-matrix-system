---
tags:
  - arquitectura
  - rol/business-developer
aliases:
  - Acciones Business Developer
---

# 6. ACCIONES DEL USUARIO — BUSINESS DEVELOPER

---

| Acción                                        | Resultado                                                                               |
| --------------------------------------------- | --------------------------------------------------------------------------------------- |
| Identificar prospecto                         | Crea registro en status Gris con datos mínimos · Aparece en mi Pipeline                 |
| Crear perfil del hotel (Azul Claro)           | Completa datos: nombre, email, teléfono, contacto, necesidad · Status pasa a Azul Claro |
| Registrar visita en frío                      | Documenta visita (fecha, contacto, resultado) · Queda en histórico                      |
| Registrar intento de contacto                 | Documenta llamada / email / visita · Queda en línea de tiempo                           |
| Elaborar Propuesta Personalizada              | Crea propuesta (servicios, precios, condiciones) en estado borrador                     |
| Editar borrador de propuesta                  | Cambios persisten · Estado se mantiene                                                  |
| Enviar propuesta al hotel                     | Cambia a estado "Enviada" · Status del prospecto pasa a Verde · Notifica al BD          |
| Avanzar a Amarillo (interés del hotel)        | Cambio de status con motivo y comentario · Queda en línea de tiempo                     |
| Crear Documento de T&C                        | Inicia documento con campos obligatorios (Pay/Bill/Overtime/Festivos/Calendario)        |
| Editar borrador del T&C                       | Cambios persisten                                                                       |
| Enviar T&C al BDC para validación             | Notifica al BDC · Documento queda en pendientes de validación                           |
| Iniciar negociación (Rosa)                    | Status cambia a Rosa · Notifica al BDC                                                  |
| Marcar rechazo (Rojo)                         | Status pasa a Rojo · Motivo obligatorio · Notifica al BDC                               |
| Reactivar desde Rojo                          | Status regresa a Azul Claro · Histórico mantiene el registro del rechazo                |
| Marcar estancamiento (Café)                   | Status pasa a Café · Notifica al BDC para que desbloquee                                |
| Duplicar propuesta como plantilla             | Crea nueva propuesta con datos pre-cargados                                             |
| Exportar propuesta como PDF                   | Descarga PDF                                                                            |
| Planear ruta del día                          | Selecciona prospectos a visitar · Genera vista de ruta optimizada                       |
| Registrar contacto comercial (cliente activo) | Documenta visita de cortesía / follow-up · Queda en histórico del cliente               |
| Cancelar acción                               | Cambios no se guardan                                                                   |
