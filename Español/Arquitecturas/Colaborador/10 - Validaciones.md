---
tags:
  - arquitectura
  - rol/colaborador
aliases:
  - Validaciones Colaborador
---

# 4. VALIDACIONES — COLABORADOR

---

## Validaciones de Onboarding

| Caso                                                        | Comportamiento del Sistema                                                                                                  |
| ----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Fase 2 enviada sin SSN ni ITIN                              | NO bloquea el envío; muestra aviso informativo: *"Sin SSN ni ITIN se aplicará una retención del 16% sobre tu pago (reembolsable)"* — ver [[Deducciones]]                                                                    |
| SSN con formato incorrecto (no XXX-XX-XXXX)                 | Bloquea campo; muestra: *"Formato de SSN inválido. Ingresa en formato XXX-XX-XXXX"* (aplica solo si el colaborador ingresa un SSN)                                                                                          |
| ITIN con formato incorrecto (no 9XX-XX-XXXX)                | Bloquea campo; muestra: *"Formato de ITIN inválido. El ITIN comienza con 9"* (aplica solo si el colaborador ingresa un ITIN)                                                                                                |
| Posición sin seleccionar                                    | Bloquea envío; muestra: *"Selecciona tu posición"*                                                                          |
| Nivel de inglés sin seleccionar                             | Bloquea envío; muestra: *"Selecciona tu nivel de inglés"*                                                                   |
| Nivel de experiencia sin seleccionar                        | Bloquea envío; muestra: *"Selecciona tu nivel de experiencia"*                                                              |
| Tipo de transporte sin seleccionar                          | Bloquea envío; muestra: *"Selecciona tu tipo de transporte"*                                                                |
| Modalidad sin seleccionar                                   | Bloquea envío; muestra: *"Selecciona la modalidad de contratación"*                                                         |
| Documento de SSN/ITIN con formato no permitido (no JPG/PNG/PDF) | Rechaza archivo; muestra: *"Solo se aceptan archivos JPG, PNG o PDF"* (aplica solo si el colaborador adjunta un documento) |
| Documento de SSN/ITIN con tamaño superior a 10 MB           | Rechaza archivo; muestra: *"El archivo no debe superar 10 MB"* (aplica solo si el colaborador adjunta un documento)        |
| Fase 3 enviada sin contacto de emergencia completo          | Bloquea envío; muestra: *"El contacto de emergencia es obligatorio. Completa nombre, teléfono y parentesco"*                |
| Teléfono de contacto de emergencia con formato inválido     | Bloquea campo; muestra: *"Ingresa un número de teléfono válido"*                                                            |
| Tipo de sangre sin seleccionar                              | Bloquea envío; muestra: *"Selecciona tu tipo de sangre. Si no lo sabes, selecciona 'No sé'"*                               |

---

## Validaciones de Ponche QR (RF-C-03)

Ver reglas de negocio completas en [[Reglas del Colaborador#Ponchado y Timesheet]]

| Caso                                                        | Comportamiento del Sistema                                                                                                  |
| ----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Intentar ponchar sin Timesheet activo                       | Bloquea acción; muestra: *"No tienes un turno activo. Comunícate con tu supervisor"* (RR-C-03)                             |
| Intentar ponchar con QR inválido o expirado                 | Bloquea acción; muestra: *"Código QR no válido. Solicita un QR actualizado a tu supervisor"*                               |
| Intentar ponchar en orden incorrecto (ej. Salida Lunch sin Entrada) | Sistema alerta; muestra: *"Registra tu Entrada antes de ponchar la Salida a Lunch"*                               |
| Ponche duplicado en la misma jornada                        | Sistema bloquea; muestra: *"Ya registraste este ponche hoy. Si hay un error, contacta a tu supervisor"*                    |
| Sin conexión al ponchar (offline)                           | Sistema encola el registro localmente; muestra: *"Sin conexión. Tu ponche se registrará cuando recuperes señal"* (RNF-C-02) |
| Lunch < 30 minutos                                          | Sistema aplica deducción mínima de 30 min automáticamente · No bloquea al colaborador · Ver [[Reglas del Colaborador#Deducción de Lunch]] |
| Jornada sin ningún ponche de Lunch                          | Sistema aplica auto-deducción de 30 min al cerrar la jornada · Ver [[Reglas del Colaborador#Deducción de Lunch]]           |

---

## Validaciones de Disponibilidad — Amarillo (RF-C-04)

| Caso                                                        | Comportamiento del Sistema                                                                                                  |
| ----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Intentar activar Amarillo estando en estado Café (asignación activa) | Bloquea acción; muestra: *"No puedes declararte disponible mientras tienes una asignación activa"*              |
| Intentar activar Amarillo estando en estado Morado, Rojo, Gris o Negro | Bloquea acción; muestra: *"No puedes modificar tu disponibilidad en tu estado actual. Contacta a Reclutamiento"* |
| Activar Amarillo sin confirmación explícita                 | Sistema requiere confirmación modal antes de ejecutar el cambio de estado (RR-C-02)                                         |

---

## Validaciones de Reporte de Accidente (RF-C-05)

| Caso                                                        | Comportamiento del Sistema                                                                                                  |
| ----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Reporte sin fecha del accidente                             | Bloquea envío; muestra: *"Indica cuándo ocurrió el accidente"*                                                              |
| Reporte con fecha futura                                    | Bloquea envío; muestra: *"La fecha del accidente no puede ser futura"*                                                      |
| Reporte sin descripción                                     | Bloquea envío; muestra: *"Describe brevemente qué ocurrió (mínimo 50 caracteres)"*                                          |
| Descripción con menos de 50 caracteres                      | Bloquea envío; muestra: *"La descripción debe tener al menos 50 caracteres"*                                                |
| Evidencia fotográfica >10 MB                                | Rechaza archivo; muestra: *"Tamaño máximo de foto: 10 MB"*                                                                  |

---

## Validaciones de Edición de Perfil (RF-C-10)

| Caso                                                        | Comportamiento del Sistema                                                                                                  |
| ----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Intentar editar SSN/ITIN tras validación de Fase 2          | Campo bloqueado; muestra: *"Para modificar este dato, comunícate con tu Reclutadora"*                                       |
| Teléfono propio con formato inválido                        | Bloquea guardado; muestra: *"Ingresa un número de teléfono válido"*                                                         |
| Guardar datos de emergencia sin nombre del contacto         | Bloquea guardado; muestra: *"El nombre del contacto de emergencia es obligatorio"*                                           |

---

## Validaciones Generales

| Caso                                                        | Comportamiento del Sistema                                                                                                  |
| ----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Sesión expirada                                             | Redirige a login; muestra: *"Tu sesión ha expirado, por favor inicia sesión nuevamente"*                                    |
| Intentar acceder a datos de otro colaborador                | Sin acceso; el sistema nunca expone datos de otros colaboradores en la interfaz (RR-C-01)                                   |
| Intentar ponchar por QR desde web                           | Acción no disponible en web; muestra: *"El ponche por QR requiere la cámara de tu teléfono. Usa la app móvil para ponchar."* (RR-C-04) |
