---
tags:
  - arquitectura
  - rol/colaborador
aliases:
  - Permisos Detallados Colaborador
---

# PERMISOS DETALLADOS POR ROL

## ROL-C-01 · 👷 Colaborador (COL)

---

| Módulo                | Funcionalidad                                        | Permiso      | Descripción                                                                   |
| --------------------- | ---------------------------------------------------- | ------------ | ----------------------------------------------------------------------------- |
| **Onboarding**        | Completar alta — Fase 2 (datos laborales)            | ➕ Crear      | Posición, inglés, experiencia, transporte, modalidad (obligatorios); SSN/ITIN opcionales; documento de SSN/ITIN opcional (JPG/PNG/PDF, máx. 10 MB); sin SSN/ITIN → aviso de retención 16% reembolsable (RF-C-01, ver [[Deducciones]])      |
| Onboarding            | Completar datos de emergencia — Fase 3               | ➕ Crear      | Contacto emergencia, tipo de sangre, alergias (RF-C-02)                       |
| Onboarding            | Ver estado de validación de su alta                  | 👁️ Ver      | Solo puede ver si fue aprobado o está pendiente; no ve observaciones internas |
| **Asistencia / QR**   | Escanear QR y ponchar (6 ponches)                    | ➕ Crear      | Entrada, Salida Lunch, Entrada Lunch, Salida Break, Entrada Break, Salida (RF-C-03) |
| Asistencia / QR       | Corregir ponche propio                               | —            | Sin acceso (exclusivo del Manager de Área)                                    |
| Asistencia / QR       | Generar QR                                           | —            | Sin acceso (exclusivo del Manager de Área / Manager General)                  |
| **Mi Schedule**       | Ver su schedule de la semana                         | 👁️ Ver      | Solo el suyo propio; lectura (RF-C-06)                                        |
| Mi Schedule           | Editar Schedule                                      | —            | Sin acceso (RR-C-01; exclusivo del Manager de Área)                           |
| **Mi Timesheet**      | Ver sus horas brutas, deducción de lunch, horas netas | 👁️ Ver     | Solo el suyo propio; lectura (RF-C-07)                                        |
| Mi Timesheet          | Ver Indicador de Lunch Extendido                     | —            | Sin acceso (exclusivo de Inspección y Reclutamiento)                          |
| Mi Timesheet          | Exportar Timesheet propio                            | 👁️ Ver      | PDF del timesheet personal de la semana                                       |
| **Mi Pago**           | Consultar historial de pagos recibidos               | 👁️ Ver      | Semana, hotel(es), horas, monto pagado y fecha de pago — solo para pagos ya liberados; sin acceso al monto del pago en curso (RR-C-05; RF-C-08) |
| Mi Pago               | Ver detalles financieros internos (pay rate, deducciones internas, facturación) | — | Sin acceso (exclusivo de Contabilidad; RR-C-05)                                 |
| Mi Pago               | Ver monto del pago en curso o próximo                | —            | Sin acceso hasta que Contabilidad libere el pago (RR-C-05)                    |
| **Disponibilidad**    | Activar disponibilidad voluntaria — Amarillo         | ➕ Crear      | Autoservicio sin aprobación (RR-C-02; RF-C-04)                                |
| Disponibilidad        | Desactivar Amarillo                                  | 📝 Editar    | Puede volver a Verde fuerte desactivando disponibilidad voluntaria            |
| **Accidente**         | Reportar accidente laboral (Escenario A — él reporta primero) | ➕ Crear | Crea la tarjeta inicial; notifica al Supervisor e Inspector (RF-C-05)         |
| Accidente             | Completar información presencial del accidente       | —            | Sin acceso (exclusivo del Supervisor)                                         |
| Accidente             | Cerrar tarjeta de accidente                          | —            | Sin acceso (exclusivo del Inspector)                                          |
| **Notificaciones**    | Ver notificaciones propias                           | 👁️ Ver      | Cambios de estado, asignaciones, validaciones (RF-C-09)                       |
| **Mi Perfil**         | Ver datos de su perfil (Fase 1 + 2 + 3)              | 👁️ Ver      | Solo el suyo (RR-C-01; RF-C-10)                                               |
| Mi Perfil             | Editar datos de contacto propios                     | 📝 Editar    | Teléfono, datos de emergencia con límites definidos                           |
| Mi Perfil             | Editar SSN/ITIN                                      | —            | Sin acceso tras aprobación de Fase 2 (dato sensible — requiere intervención de Reclutadora) |
| Mi Perfil             | Ver estado del semáforo propio                       | 👁️ Ver      | Color y nombre del estado actual (RF-C-10)                                    |
| **Sistema** (transv.) | Recibir notificaciones push                          | 👁️ Ver      | Alertas de cambio de estado, asignación, validaciones                         |

---

## Sección explícita — El Colaborador NO puede

- Ver datos de ningún otro colaborador (RR-C-01).
- Aceptar, rechazar o solicitar asignaciones.
- Modificar el Schedule (lectura exclusiva).
- Corregir ponches propios o ajenos (exclusivo del Manager de Área).
- Generar QR de ponchado (exclusivo del Manager de Área / Manager General).
- Ver el Indicador de Lunch Extendido (exclusivo de Inspección y Reclutamiento).
- Ver el Consolidado Semanal completo con deducciones internas y detalles financieros de Contabilidad.
- Acceder a módulos de gestión: requisiciones, pool, Blacklist, contabilidad, QA.
- Poner a otro colaborador en ningún estado del semáforo.
- Ponchar por web (RR-C-04) — el ponche por QR requiere la cámara del teléfono y es exclusivo de móvil.
