---
tags:
  - arquitectura
  - rol/manager-general
aliases:
  - Respuestas Sistema Manager General
---

# 7. RESPUESTAS DEL SISTEMA — MANAGER GENERAL

---

| Evento                                                | Respuesta del Sistema                                                                                                |
| ----------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| GM consulta Schedule global                           | Vista calendario consolidada con drill-down por depto · Heatmap de cobertura                                         |
| GM consulta Timesheet global                          | Tabla consolidada con Indicador de Cumplimiento · Resumen por depto                                                  |
| GM aplica filtros                                     | Vista actualizada en menos de 2s                                                                                      |
| GM exporta Schedule / Timesheet consolidado           | Genera archivo PDF / CSV / Excel descargable                                                                          |
| GM comenta al expediente de requisición               | Comentario aparece en el journal con autor y fecha · Notifica al Gerente de Departamento                             |
| GM escala requisición demorada                        | Notifica al Manager de Reclutamiento · Cambia indicador a "Escalado" · Queda en log auditable                       |
| GM solicita reporte a Gerente                         | Notifica al Gerente con los datos de la solicitud · Aparece en su bandeja de pendientes                              |
| GM comunica con Gerente / Supervisor                  | Mensaje enviado · Notificación push / email al destinatario                                                          |
| GM genera reporte ejecutivo                           | Vista previa con datos consolidados según plantilla seleccionada · Botones de exportar / enviar / guardar           |
| GM exporta reporte                                    | Archivo descargable (CSV / PDF / Excel)                                                                               |
| GM envía reporte a dirección                          | Email / link enviado · Queda en histórico con destinatario, asunto y estado · Notifica al GM cuando se lee          |
| GM programa envío recurrente                          | Configuración guardada · Sistema enviará automáticamente según frecuencia                                            |
| Indicador de Calidad cae a Rojo                       | Notifica al GM y al Manager de QA · Alerta visible en Dashboard                                                     |
| Indicador de Cumplimiento del Timesheet cae a Rojo (consolidado) | Notifica al GM y al Gerente de Departamento afectado                                                       |
| Cobertura del hotel cae <70%                          | Alerta visible en Dashboard · Notifica al GM                                                                         |
| Accidente laboral grave                               | Notifica al GM con detalle del caso e Inspector asignado                                                             |
| Sesión iniciada                                        | Redirige a Dashboard global con KPIs cargados                                                                         |
| Sesión expirada                                        | Redirige a login                                                                                                       |
| GM intenta acción sin permiso                         | Muestra mensaje: *"No tienes permiso para esta acción"* · El botón normalmente no aparece                            |
