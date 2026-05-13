---
tags:
  - arquitectura
  - rol/bdc
aliases:
  - Acciones BDC
---

# 6. ACCIONES DEL USUARIO — BUSINESS DEVELOPER COORDINATOR

---

| Acción                         | Resultado                                                                                                                                   |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| Validar Documento de T&C       | T&C aprobado · Notifica al BD · Permite avanzar a Rosa · Queda en log                                                                       |
| Rechazar T&C con observaciones | T&C vuelve a editable · Notifica al BD con observaciones                                                                                    |
| Iniciar negociación (Rosa)     | Status pasa a Rosa · Trazabilidad                                                                                                           |
| Crear Documento de T&C         | Documento creado con campos obligatorios                                                                                                    |
| Crear Usuario del Hotel        | Usuario creado · Habilita botón "Aprobar conversión"                                                                                        |
| Aprobar conversión a cliente   | Status pasa a Naranja · **Trigger Automático** ejecuta 3 acciones en paralelo: email + notif al BD + sale del Pipeline · Hotel queda activo |
| Marcar prospecto Café          | Status pasa a Café · Notifica al BD                                                                                                         |
| Investigar caso Café           | Acceso a histórico, contactos, notas del BD                                                                                                 |
| Desbloquear Café               | Decisión tomada · Permite reactivar                                                                                                         |
| Reactivar desde Café           | Status regresa a Azul Claro · Notifica al BD original                                                                                       |
| Marcar cliente Negro           | Cliente activo pasa a Negro · Notifica al BD asignado · Queda en log                                                                        |
| Reactivar desde Negro          | Cliente Negro regresa a Azul Claro como prospecto · Notifica al BD                                                                          |
| Reasignar prospecto a otro BD  | Cambio de BD asignado · Notifica a ambos BDs · Queda en log                                                                                 |
| Comentar al expediente         | Comentario aparece en línea de tiempo · Notifica al BD asignado                                                                             |
| Solicitar reporte a un BD      | Notifica al BD con la solicitud                                                                                                             |
| Generar reporte de Ventas      | Vista previa con datos consolidados · Botones de exportar / enviar / guardar                                                                |
| Exportar reporte               | Descarga CSV / PDF / Excel                                                                                                                  |
| Enviar reporte a dirección     | Email / link enviado · Histórico con destinatario y estado                                                                                  |
| Programar envío recurrente     | Configuración guardada · Sistema enviará automáticamente                                                                                    |
| Comunicar con BD               | Mensaje / nota interna · Notificación al BD                                                                                                 |
| Cancelar acción                | Cambios no se guardan                                                                                                                       |
