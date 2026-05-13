---
tags:
  - arquitectura
  - rol/lider-de-grupo
aliases:
  - Respuestas Sistema Líder de Grupo
---

# 7. RESPUESTAS DEL SISTEMA — LÍDER DE GRUPO

---

## Respuestas operativas (heredadas de Reclutadora)

| Evento                     | Respuesta del Sistema                                                   |
| -------------------------- | ----------------------------------------------------------------------- |
| Líder toma requisición     | Mueve a "Mis Requisiciones"; semáforo a Amarillo                        |
| Crea nuevo colaborador     | Mensaje de confirmación; redirige a lista                               |
| Valida alta en App         | Habilita accesos automáticamente; notifica al colaborador               |
| Asigna colaborador a hotel | Actualiza cobertura; refleja en Schedule; notifica al Manager de Área |
| Marca requisición cubierta | Sistema cierra (Azul claro); semáforo del hotel notifica el cierre      |
| Reclutadora del grupo marca cubierta | Llega solicitud al Líder para aprobar el cierre               |

---

## Respuestas exclusivas del Líder

| Evento                                           | Respuesta del Sistema                                                |
| ------------------------------------------------ | -------------------------------------------------------------------- |
| Reclutadora del grupo cubrió requisición al 100% | Notifica al Líder con felicitación y métrica actualizada             |
| Reclutadora del grupo reportó problema           | Notifica al Líder con contexto del caso para atención de 1er nivel   |
| Líder genera reporte                             | Compila datos del periodo y muestra vista previa                     |
| Líder envía reporte al Manager                   | Crea registro en histórico; notifica al Manager con link al reporte  |
| Líder exporta reporte                            | Descarga archivo (CSV/PDF)                                           |
| Líder atiende incidencia                         | Registra en log con resolución y comentario                          |
| Líder escala incidencia al Manager               | Notifica al Manager con todo el contexto y evidencia                 |
| Manager solicita reporte al Líder                | Notificación de solicitud aparece en bandeja de acción del Líder     |
| Reclutadora del grupo cambia disponibilidad      | Notifica al Líder (vacaciones, baja, vuelta)                         |
| Reclutadora del grupo entra en sobrecarga        | Alerta automática al Líder cuando supera N requisiciones simultáneas |
