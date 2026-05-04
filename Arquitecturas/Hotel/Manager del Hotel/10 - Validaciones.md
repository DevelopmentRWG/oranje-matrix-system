---
tags:
  - arquitectura
  - rol/manager-del-hotel
aliases:
  - Validaciones Manager del Hotel
---

# 4. VALIDACIONES — MANAGER DEL HOTEL

---

| Caso                                                       | Comportamiento del Sistema                                                                                                |
| ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Intentar autorizar requisición sin posiciones              | Bloquea acción; muestra: *"No tiene posiciones registradas, registre al menos una posición e intente nuevamente"*         |
| Otro rol intenta autorizar (Supervisor)                    | Bloquea acción; muestra: *"Solo el gerente del hotel puede autorizar la requisición"*                                     |
| Rechazar sin observaciones                                  | Bloquea acción; muestra: *"Las observaciones son obligatorias al rechazar"*                                                |
| Eliminar requisición con posiciones sin justificación      | Bloquea acción; muestra: *"La justificación es obligatoria al eliminar una requisición con posiciones"*                    |
| Confirmación de eliminación física no marcada              | Bloquea botón; muestra: *"Debe confirmar que las posiciones serán eliminadas físicamente"*                                  |
| Generar QR sin permisos del rol                            | Bloquea acción; muestra: *"Solo el gerente del hotel puede generar el código QR del Timesheet"*                            |
| Corregir ponche sin justificación                          | Bloquea acción; muestra: *"La justificación es obligatoria para corregir ponches"*                                          |
| Corregir ponche con hora fuera del rango de la jornada     | Muestra advertencia; permite continuar con confirmación adicional                                                          |
| Reportar colaborador con descripción <50 caracteres        | Bloquea envío; muestra: *"La descripción debe tener al menos 50 caracteres para iniciar la investigación"*                  |
| Reportar colaborador no asignado al depto                  | Bloquea acción; muestra: *"Solo puede reportar colaboradores asignados a su departamento"*                                  |
| Poner Stand-by a colaborador ya en Stand-by                | Bloquea acción; muestra: *"El colaborador ya se encuentra en Stand-by"*                                                    |
| Stand-by sin motivo seleccionado                           | Bloquea envío; muestra: *"Seleccione el motivo del Stand-by"*                                                              |
| Editar Schedule con posiciones cruzadas (mismo colaborador en 2 turnos) | Bloquea guardado; muestra: *"El colaborador ya está asignado en este horario en otra posición"*                  |
| Acceder a Indicador de Lunch Extendido                     | Sin acceso visible; el módulo no aparece en la interfaz                                                                    |
| Adjunto >5 MB en formularios                               | Rechaza archivo; muestra: *"Tamaño máximo: 5 MB"*                                                                          |
| Evidencia de reporte >10 MB                                | Rechaza archivo; muestra: *"Tamaño máximo de evidencia: 10 MB"*                                                            |
| Sesión expirada                                             | Redirige a login; muestra: *"Tu sesión ha expirado, por favor inicia sesión nuevamente"*                                    |
