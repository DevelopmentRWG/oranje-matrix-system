---
tags:
  - arquitectura
  - rol/business-developer
aliases:
  - Validaciones Business Developer
---

# 4. VALIDACIONES — BUSINESS DEVELOPER

---

| Caso                                                       | Comportamiento del Sistema                                                                                                |
| ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Identificar prospecto sin nombre o ciudad                  | Bloquea envío; muestra: *"Complete los campos obligatorios (nombre, ciudad)"*                                              |
| Crear perfil sin email o teléfono                          | Bloquea envío; muestra: *"Email y teléfono son obligatorios"*                                                              |
| Email con formato inválido                                  | Bloquea envío; muestra: *"Formato de email inválido"*                                                                      |
| Necesidad del negocio <30 caracteres                       | Bloquea envío; muestra: *"Describa la necesidad del negocio (mín. 30 caracteres)"*                                          |
| Avanzar a Verde sin propuesta enviada                      | Bloquea acción; muestra: *"Debe enviar una Propuesta Personalizada antes de avanzar a Verde"*                              |
| Crear propuesta para prospecto en status no-Verde          | Permite crear borrador, pero al enviar muestra: *"La propuesta solo puede enviarse en status Verde"* (RR-V-09)              |
| Enviar propuesta sin servicios o precios                   | Bloquea envío; muestra: *"Complete servicios y precios antes de enviar"*                                                    |
| Crear T&C sin Pay/Bill/Overtime/Festivos/Calendario        | Bloquea envío; muestra: *"Complete los 5 campos obligatorios del T&C (RR-V-10)"*                                            |
| Iniciar negociación (Rosa) sin T&C completo                | Bloquea acción; muestra: *"Debe tener un Documento de T&C completo antes de iniciar negociación"*                          |
| Intentar aprobar conversión                                 | Acción no disponible; el botón no aparece (RR-V-01)                                                                         |
| Intentar crear Usuario del Hotel                            | Acción no disponible (BDC exclusivo)                                                                                         |
| Intentar desbloquear Café                                   | Acción no disponible; muestra: *"Solo el BDC puede desbloquear estancamientos"* (RR-V-04)                                   |
| Intentar marcar / reactivar Negro                           | Acción no disponible (BDC exclusivo — RR-V-05)                                                                              |
| Marcar Rojo sin motivo                                      | Bloquea envío; muestra: *"Seleccione el motivo del rechazo"*                                                                 |
| Marcar Rojo con comentario <30 caracteres                  | Bloquea envío; muestra: *"El comentario debe tener al menos 30 caracteres"*                                                  |
| Reactivar desde Rojo                                        | Status regresa automáticamente a Azul Claro (RR-V-07)                                                                       |
| Marcar Café sin notas para el BDC                          | Bloquea envío; muestra: *"Las notas para el BDC son obligatorias"*                                                          |
| Editar prospecto fuera de mi territorio                    | Sin acceso; muestra: *"No tienes permiso para gestionar este prospecto"*                                                    |
| Editar cliente activo (post-Naranja)                       | Sin acceso a campos operativos; vista solo lectura (RR-V-12)                                                                |
| Adjunto >10 MB                                              | Rechaza archivo; muestra: *"Tamaño máximo: 10 MB"*                                                                          |
| Sesión expirada                                             | Redirige a login                                                                                                            |
