---
tags:
  - arquitectura
  - rol/business-developer
aliases:
  - Campos Formulario Business Developer
---

# 3. CAMPOS DEL FORMULARIO — BUSINESS DEVELOPER

---

## A) Identificar Prospecto (Gris) — RF-V-01

| Campo                  | Tipo de Input | Obligatorio | Validación                              | Descripción                              |
| ---------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------- |
| Nombre del hotel       | Text          | SÍ          | Mín. 3 caracteres                       | Nombre del prospecto                     |
| Ciudad                 | Text          | SÍ          | Mín. 3 caracteres                       | Ciudad de ubicación                      |
| Zona / Ruta            | Select        | SÍ          | Catálogo de Zonas asignadas al BD       | Zona del prospecto                       |
| Geolocalización        | Auto / Manual | NO          | Coordenadas GPS                         | Auto desde mobile, manual en desktop    |
| Origen del lead        | Select        | NO          | Recomendación / Visita / Web / Otro     | De dónde salió el prospecto              |
| Notas iniciales        | Textarea      | NO          | Máx. 500 caracteres                     | Observaciones del BD                     |

---

## B) Crear Perfil del Hotel (Azul Claro) — RF-V-02

| Campo                  | Tipo de Input | Obligatorio | Validación                              | Descripción                              |
| ---------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------- |
| Email principal        | Email         | SÍ          | Formato email válido                    | Contacto del hotel                       |
| Teléfono               | Text          | SÍ          | Formato válido                          | Contacto principal                       |
| Nombre del contacto    | Text          | SÍ          | Mín. 3 caracteres                       | Persona con quien se trata               |
| Cargo del contacto     | Text          | SÍ          | Mín. 3 caracteres                       | Cargo en el hotel                        |
| Necesidad del negocio  | Textarea      | SÍ          | Mín. 30 caracteres                      | Qué necesita el hotel                    |
| Tamaño del hotel        | Select        | NO          | Pequeño / Mediano / Grande / Lujo       | Categoría comercial                      |
| Cantidad estimada de personal | Number  | NO          | Entero >0                               | Estimación inicial                       |

---

## C) Registrar Visita en Frío — RF-V-03

| Campo                  | Tipo de Input | Obligatorio | Validación                              | Descripción                              |
| ---------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------- |
| Fecha de visita         | Date          | SÍ          | Fecha actual o pasada                   | Cuándo se hizo la visita                 |
| Hora                   | Time          | SÍ          | —                                       | Hora aprox.                              |
| Persona contactada      | Text          | SÍ          | Mín. 3 caracteres                       | Quién atendió                            |
| Resultado              | Select        | SÍ          | Interesado / No disponible / Rechazo / Pendiente nuevo intento | Resultado de la visita                   |
| Observaciones          | Textarea      | NO          | Máx. 500 caracteres                     | Detalles                                 |
| Próximo seguimiento     | Date          | NO          | Fecha futura                             | Cuándo volver a contactar                |

---

## D) Registrar Intento de Contacto — RF-V-06

| Campo                  | Tipo de Input | Obligatorio | Validación                              | Descripción                              |
| ---------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------- |
| Tipo                   | Select        | SÍ          | Llamada / Email / Visita / WhatsApp     | Medio de contacto                        |
| Fecha y hora           | Datetime      | SÍ          | Actual o pasada                          | Cuándo se hizo                           |
| Resultado              | Select        | SÍ          | Sin respuesta / Respondió / Reagenda / Rechazo | —                                        |
| Notas                  | Textarea      | NO          | Máx. 500 caracteres                     | Detalles                                 |

---

## E) Elaborar Propuesta Personalizada — RF-V-04

| Campo                  | Tipo de Input | Obligatorio | Validación                              | Descripción                              |
| ---------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------- |
| Hotel destino          | Auto          | SÍ          | Pre-llenado desde el prospecto          | Hotel para el que se elabora             |
| Servicios propuestos    | Multi-select  | SÍ          | Catálogo de servicios                   | Qué se ofrece                            |
| Precios                | Number/Table  | SÍ          | Por servicio                             | Tarifas propuestas                       |
| Condiciones generales   | Textarea      | SÍ          | Mín. 100 caracteres                     | Términos comerciales                     |
| Vigencia de la propuesta | Date         | SÍ          | Fecha futura                             | Hasta cuándo es válida                   |
| Adjuntos               | File          | NO          | PDF / DOCX, máx. 10 MB                  | Documentos de soporte                    |

---

## F) Crear Documento de T&C — RF-V-08

> [!important]
> Campos obligatorios definidos por RR-V-10. Sin estos campos, no se puede iniciar la negociación (Rosa).

| Campo                  | Tipo de Input | Obligatorio | Validación                              | Descripción                              |
| ---------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------- |
| **Pay rate**           | Number        | SÍ          | >0                                       | Tarifa de pago al colaborador            |
| **Bill rate**          | Number        | SÍ          | >0                                       | Tarifa de facturación al hotel           |
| **Overtime**           | Number / %    | SÍ          | >0                                       | Reglas de tiempo extra                   |
| **Festivos**           | Multi-select  | SÍ          | Catálogo de festivos                    | Días festivos pagados                    |
| **Calendario**         | Date Range    | SÍ          | Rango válido                             | Inicio y fin de semana                   |
| Vigencia                | Date Range    | NO          | Rango futuro                             | Período de validez                       |
| Renovación              | Select        | NO          | Auto / Manual / Fija                    | Términos de renovación                   |
| Adjuntos                | File          | NO          | PDF, máx. 10 MB                          | Documentos de soporte                    |

---

## G) Marcar Rechazo (Rojo) — RF-V-15

| Campo                  | Tipo de Input | Obligatorio | Validación                              | Descripción                              |
| ---------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------- |
| Motivo                 | Select        | SÍ          | Catálogo: No le interesó / No tiene presupuesto / Otra empresa / Otro | Razón del rechazo                        |
| Comentario             | Textarea      | SÍ          | Mín. 30 caracteres                      | Detalles del rechazo                     |
| ¿Reactivar más adelante? | Checkbox    | NO          | —                                       | Si marca, queda como "candidato a reactivar" |

---

## H) Marcar Café (Estancamiento) — RF-V-17

| Campo                  | Tipo de Input | Obligatorio | Validación                              | Descripción                              |
| ---------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------- |
| Motivo del estancamiento | Select      | SÍ          | Catálogo: Sin respuesta / Cambio de contacto / Indefinido / Otro | Razón                                    |
| Notas para el BDC       | Textarea      | SÍ          | Mín. 30 caracteres                      | Contexto para que el BDC desbloquee      |

---

## I) Filtros del Pipeline / Mi Territorio

| Campo                | Tipo de Input | Obligatorio | Descripción                                                |
| -------------------- | ------------- | ----------- | ---------------------------------------------------------- |
| Status               | Multi-select  | NO          | Catálogo de status del Semáforo Onboarding                 |
| Ruta / Zona          | Select        | NO          | Catálogo de mis rutas asignadas                             |
| Días sin contacto     | Slider        | NO          | 1-3 / 4-7 / >7                                              |
| Buscar por nombre / ciudad | Text   | NO          | Búsqueda libre                                              |
