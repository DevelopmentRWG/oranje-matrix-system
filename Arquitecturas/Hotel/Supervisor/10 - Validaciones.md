---
tags:
  - arquitectura
  - rol/supervisor-hotel
aliases:
  - Validaciones Supervisor
---

# 4. VALIDACIONES — SUPERVISOR

---

| Caso                                                       | Comportamiento del Sistema                                                                                                |
| ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Crear requisición sin posiciones                           | Permite guardar como borrador, pero al intentar enviar a autorización: bloquea con *"No tiene posiciones registradas, registre al menos una posición e intente nuevamente"* (RR-H-03) |
| Cantidad de personas <1                                    | Bloquea envío; muestra: *"La cantidad debe ser al menos 1 persona"*                                                        |
| Fecha de inicio en el pasado                                | Bloquea envío; muestra: *"La fecha de inicio debe ser futura"*                                                              |
| Hora de salida menor o igual a entrada                      | Bloquea envío; muestra: *"La hora de salida debe ser mayor que la de entrada"*                                              |
| Posición no seleccionada                                    | Bloquea envío; muestra: *"Seleccione una posición"*                                                                         |
| Modalidad o nivel de inglés sin seleccionar                | Bloquea envío; muestra: *"Complete los campos obligatorios"*                                                                 |
| Adjunto >5 MB                                               | Rechaza archivo; muestra: *"Tamaño máximo: 5 MB"*                                                                            |
| Intentar autorizar requisición                             | Bloquea acción; muestra: *"Solo el gerente del hotel puede autorizar la requisición"* (RR-H-02)                            |
| Reportar accidente sin colaborador seleccionado            | Bloquea envío; muestra: *"Seleccione el colaborador afectado"*                                                              |
| Reportar accidente con descripción <50 caracteres          | Bloquea envío; muestra: *"Las circunstancias deben tener al menos 50 caracteres"*                                            |
| Reportar accidente sin atención inmediata                  | Bloquea envío; muestra: *"Indique qué atención inmediata se brindó"*                                                         |
| Reportar accidente con fecha futura                        | Bloquea envío; muestra: *"La fecha del accidente no puede ser futura"*                                                      |
| Evidencia >10 MB                                            | Rechaza archivo; muestra: *"Tamaño máximo de evidencia: 10 MB"*                                                              |
| Stand-by sin motivo seleccionado                           | Bloquea envío; muestra: *"Seleccione el motivo del Stand-by"*                                                                |
| Stand-by a colaborador ya en Stand-by                      | Bloquea acción; muestra: *"El colaborador ya se encuentra en Stand-by"*                                                     |
| Intentar reportar colaborador (Rojo)                       | Acción no disponible (solo Manager de Área); el botón no aparece                                                          |
| Intentar generar QR del Timesheet                          | Acción no disponible; el botón no aparece                                                                                    |
| Intentar editar Schedule                                    | Acceso solo lectura; los botones de edición no aparecen                                                                     |
| Acceder a Indicador de Lunch Extendido                     | Sin acceso; el módulo no aparece en la interfaz (RR-H-15)                                                                    |
| Sesión expirada                                             | Redirige a login; muestra: *"Tu sesión ha expirado, por favor inicia sesión nuevamente"*                                    |
