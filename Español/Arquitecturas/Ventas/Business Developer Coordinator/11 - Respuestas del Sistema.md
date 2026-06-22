---
tags:
  - arquitectura
  - rol/bdc
aliases:
  - Respuestas Sistema BDC
---

# 7. RESPUESTAS DEL SISTEMA — BUSINESS DEVELOPER COORDINATOR

---

| Evento                                    | Respuesta del Sistema                                                                                                                                                                                  |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BDC valida T&C                            | T&C aprobado · Notifica al BD: *"Tu T&C fue validado"* · Permite avanzar a Rosa · Log auditable                                                                                                        |
| BDC rechaza T&C con observaciones         | T&C vuelve a editable por el BD · Notifica al BD con observaciones                                                                                                                                     |
| BDC crea Usuario del Hotel                | Usuario creado · Habilita botón "Aprobar conversión" · Email NO se envía aún (espera la aprobación)                                                                                                    |
| BDC aprueba conversión                    | Status pasa a Naranja · **Trigger Automático ejecuta en paralelo:** (1) email de bienvenida al hotel, (2) notificación al BD asignado, (3) hotel desaparece del Pipeline · Aparece en Clientes Activos |
| Trigger ejecuta exitosamente              | Las 3 acciones quedan en log · Notifica al BDC del éxito                                                                                                                                               |
| BDC marca Café                            | Status pasa a Café · Notifica al BD                                                                                                                                                                    |
| BDC desbloquea Café                       | Decisión tomada · Notifica al BD: *"Tu prospecto fue desbloqueado"* · Permite reactivar                                                                                                                |
| BDC reactiva desde Café                   | Status regresa a Azul Claro · BD recupera control · Línea de tiempo actualizada                                                                                                                        |
| BDC marca cliente Negro                   | Cliente activo pasa a Negro · Notifica al BD asignado · Sale de la vista de clientes activos                                                                                                           |
| BDC reactiva desde Negro                  | Cliente regresa a Azul Claro como prospecto · Notifica al BD                                                                                                                                           |
| BDC reasigna prospecto a otro BD          | Prospecto cambia de BD · Notifica a ambos BDs · Línea de tiempo actualizada                                                                                                                            |
| BDC comenta al expediente                 | Comentario aparece en línea de tiempo · Notifica al BD asignado                                                                                                                                        |
| BDC genera reporte                        | Vista previa con datos consolidados · Botones de exportar / enviar / guardar                                                                                                                           |
| BDC exporta reporte                       | Archivo descargable                                                                                                                                                                                    |
| BDC envía reporte a dirección             | Email / link enviado · Histórico actualizado · Notifica al BDC cuando se lee                                                                                                                           |
| BDC programa envío recurrente             | Configuración guardada · Sistema enviará automáticamente según frecuencia                                                                                                                              |
| BDC solicita reporte a un BD              | Notifica al BD con la solicitud                                                                                                                                                                        |
| Indicador de Calidad del depto cae a Rojo | Notifica al BDC y al Manager de QA                                                                                                                                                                     |
| Sesión iniciada                           | Redirige a Dashboard · Carga embudo, casos críticos, alertas                                                                                                                                           |
| Sesión expirada                           | Redirige a login                                                                                                                                                                                       |
| BDC intenta acción sin permiso            | Botón no aparece · Si fuerza vía URL: *"No tienes permiso para esta acción"*                                                                                                                           |
