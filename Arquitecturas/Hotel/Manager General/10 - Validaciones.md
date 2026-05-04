---
tags:
  - arquitectura
  - rol/manager-general
aliases:
  - Validaciones Manager General
---

# 4. VALIDACIONES — MANAGER GENERAL

---

| Caso                                                       | Comportamiento del Sistema                                                                                                |
| ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Comentar expediente con <20 caracteres                     | Bloquea envío; muestra: *"El comentario debe tener al menos 20 caracteres"*                                                |
| Escalar requisición sin motivo                             | Bloquea envío; muestra: *"Seleccione el motivo del escalamiento"*                                                          |
| Escalar requisición con mensaje <30 caracteres             | Bloquea envío; muestra: *"El mensaje al Manager de Reclutamiento debe tener al menos 30 caracteres"*                        |
| Solicitar reporte sin tipo                                 | Bloquea envío; muestra: *"Seleccione el tipo de reporte"*                                                                  |
| Solicitar reporte sin rango de fechas                      | Bloquea envío; muestra: *"Indique el rango de fechas a reportar"*                                                          |
| Solicitar reporte con fecha límite pasada                  | Bloquea envío; muestra: *"La fecha límite debe ser futura"*                                                                |
| Generar reporte sin tipo                                   | Bloquea envío; muestra: *"Seleccione el tipo de reporte"*                                                                  |
| Enviar reporte sin destinatarios                           | Bloquea envío; muestra: *"Seleccione al menos un destinatario"*                                                            |
| Enviar reporte sin asunto                                  | Bloquea envío; muestra: *"El asunto es obligatorio"*                                                                       |
| Enviar reporte recurrente sin frecuencia                   | Bloquea envío; muestra: *"Seleccione la frecuencia del envío recurrente"*                                                  |
| Adjunto >5 MB                                               | Rechaza archivo; muestra: *"Tamaño máximo: 5 MB"*                                                                          |
| Intentar autorizar requisición                             | Acción no disponible; el botón no aparece (RR-H-14)                                                                        |
| Intentar generar QR / corregir ponche                      | Acción no disponible; los módulos correspondientes son solo lectura                                                         |
| Intentar editar Schedule                                    | Acción no disponible; vista solo lectura                                                                                    |
| Intentar dar de alta usuario                                | Acción no disponible (eso es del Administrador)                                                                             |
| Acceder a Indicador de Lunch Extendido                     | Sin acceso; el indicador no aparece en la interfaz (RR-H-15)                                                               |
| Sesión expirada                                             | Redirige a login                                                                                                            |
| Acceder a hotel con jerarquía simple                       | Sin acceso al rol Manager General; mensaje: *"Este rol solo aplica en hoteles con jerarquía extendida"*                    |
