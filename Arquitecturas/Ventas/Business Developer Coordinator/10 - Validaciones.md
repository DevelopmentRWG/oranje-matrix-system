---
tags:
  - arquitectura
  - rol/bdc
aliases:
  - Validaciones BDC
---

# 4. VALIDACIONES — BUSINESS DEVELOPER COORDINATOR

---

| Caso                                                       | Comportamiento del Sistema                                                                                                |
| ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Rechazar T&C sin observaciones                              | Bloquea envío; muestra: *"Las observaciones son obligatorias al rechazar"*                                                 |
| Rechazar T&C con observaciones <30 caracteres              | Bloquea envío; muestra: *"Las observaciones deben tener al menos 30 caracteres"*                                            |
| Crear Usuario del Hotel con email duplicado                | Bloquea envío; muestra: *"Este email ya está registrado en el sistema"*                                                    |
| Crear Usuario del Hotel sin rol asignado                    | Bloquea envío; muestra: *"Seleccione el rol asignado"*                                                                       |
| Aprobar conversión sin Usuario del Hotel previamente creado | Bloquea botón; muestra: *"Debe crear el Usuario del Hotel antes de aprobar la conversión"* (RR-V-02)                       |
| Aprobar conversión sin T&C validado                         | Bloquea botón; muestra: *"El Documento de T&C debe estar validado antes de aprobar la conversión"*                          |
| Aprobar conversión sin marcar confirmación final            | Bloquea botón; muestra: *"Confirme que el hotel cumple los requisitos para activarse"*                                      |
| Desbloquear Café sin diagnóstico o solución                 | Bloquea envío; muestra: *"Diagnóstico y solución son obligatorios"*                                                         |
| Desbloquear Café con campos <50 caracteres                  | Bloquea envío; muestra: *"Cada campo debe tener al menos 50 caracteres"*                                                    |
| Marcar Negro sin motivo                                     | Bloquea envío; muestra: *"Seleccione el motivo del Negro"*                                                                  |
| Marcar Negro con comentario <30 caracteres                  | Bloquea envío; muestra: *"El comentario debe tener al menos 30 caracteres"*                                                  |
| Reactivar Negro fuera de mi territorio                      | Bloquea acción; muestra: *"No tienes permiso para gestionar este cliente"*                                                  |
| Reasignar prospecto a un BD que no es de mi territorio      | Bloquea selección; muestra: *"Solo puedes reasignar a BDs de tu territorio"*                                                |
| Generar reporte sin tipo                                    | Bloquea envío; muestra: *"Seleccione el tipo de reporte"*                                                                    |
| Enviar reporte sin destinatarios                            | Bloquea envío; muestra: *"Seleccione al menos un destinatario"*                                                              |
| Enviar reporte recurrente sin frecuencia                    | Bloquea envío; muestra: *"Seleccione la frecuencia del envío recurrente"*                                                  |
| Adjunto >10 MB                                               | Rechaza archivo; muestra: *"Tamaño máximo: 10 MB"*                                                                          |
| Intentar marcar Rojo                                        | Acción no disponible (RR-V-06 — exclusivo BD)                                                                               |
| Intentar acceder a operación post-Naranja                   | Acción no disponible (RR-V-12 — referente comercial sin operación)                                                         |
| Sesión expirada                                             | Redirige a login                                                                                                            |
