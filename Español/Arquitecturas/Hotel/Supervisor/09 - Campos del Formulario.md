---
tags:
  - arquitectura
  - rol/supervisor-hotel
aliases:
  - Campos Formulario Supervisor
---

# 3. CAMPOS DEL FORMULARIO — SUPERVISOR

---

## A) Formulario "Nueva Requisición" (RF-H-01)

| Campo                  | Tipo de Input | Obligatorio | Validación                                                                | Descripción                                  |
| ---------------------- | ------------- | ----------- | ------------------------------------------------------------------------- | -------------------------------------------- |
| Posición               | Select        | SÍ          | Catálogo de [[Posiciones]] (Housekeeper, Hoseman, Chef, Laundry)          | Posición a cubrir                            |
| Cantidad               | Number        | SÍ          | Entero >0                                                                 | Personas a cubrir esta posición              |
| Fecha de inicio         | Date          | SÍ          | Fecha en el futuro                                                        | Cuándo se necesita el personal               |
| Horario entrada         | Time          | SÍ          | Formato HH:MM (24h)                                                       | Hora de inicio de jornada                    |
| Horario salida          | Time          | SÍ          | Formato HH:MM (24h) · Mayor que entrada                                   | Hora de fin de jornada                       |
| Modalidad              | Select        | SÍ          | Catálogo de [[Modalidades de Contratación]] (TC / MT / Temporal / SS)     | Tipo de contratación                         |
| Nivel de inglés         | Select        | SÍ          | Catálogo de [[Niveles de Inglés]] (Básico / Intermedio / Avanzado / Conv.) | Preferencia del nivel                        |
| Notas adicionales       | Textarea      | NO          | Máx. 500 caracteres                                                       | Contexto, requisitos especiales              |
| Adjuntos               | File          | NO          | PDF/JPG/PNG, máx. 5 MB                                                    | Documentos de soporte                        |

> [!note]
> Una requisición puede tener múltiples posiciones. El formulario permite agregar varias filas de "Posición + Cantidad" antes de enviar a autorización.

---

## B) Formulario de Reporte de Accidente — Escenario A y B (RF-H-20, RF-H-21)

| Campo                              | Tipo de Input | Obligatorio | Validación                              | Descripción                                                |
| ---------------------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Colaborador afectado               | Select        | SÍ          | Lista de colaboradores asignados        | Quién sufrió el accidente                                  |
| Fecha del accidente                | Date          | SÍ          | Fecha actual o pasada (no futura)        | Cuándo ocurrió                                              |
| Hora del accidente                 | Time          | SÍ          | Formato HH:MM                           | A qué hora ocurrió                                          |
| Ubicación exacta                    | Text          | SÍ          | Mín. 10 caracteres                       | Lugar específico de la propiedad                           |
| Circunstancias                     | Textarea      | SÍ          | Mín. 50 caracteres                       | Descripción detallada de cómo ocurrió                      |
| Atención inmediata brindada        | Textarea      | SÍ          | Mín. 20 caracteres                       | Qué se hizo en el momento (primeros auxilios, etc.)        |
| Testigos                           | Text          | NO          | Mín. 3 caracteres si se llena            | Nombres de testigos                                         |
| Evidencia (fotos/video)            | File          | NO          | JPG/PNG/MP4, máx. 10 MB                  | Captura presencial                                          |
| Geolocalización (mobile)           | Auto          | NO          | Auto desde el dispositivo                | Coordenadas del lugar (si aplica)                          |
| Escenario                          | Select        | SÍ          | A (colaborador reportó primero) / B (Supervisor detectó) | Tipo de flujo                                              |

---

## C) Formulario de Stand-by (Rosa) — RF-H-17

| Campo            | Tipo de Input | Obligatorio | Validación                              | Descripción                                                |
| ---------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Colaborador      | Select        | SÍ          | Lista de colaboradores asignados        | Colaborador a poner en Stand-by                            |
| Motivo           | Select        | SÍ          | Catálogo: Vacaciones / Temporada baja / Decisión del hotel / Otro | Razón                                                       |
| Notas            | Textarea      | NO          | Máx. 500 caracteres                     | Contexto adicional                                          |

---

## D) Formulario de Sugerir Refuerzo (RF-H-19)

| Campo                  | Tipo de Input | Obligatorio | Validación                              | Descripción                                                |
| ---------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Posición que falta     | Auto          | SÍ          | Pre-llenado desde el Schedule           | Posición vacante detectada                                 |
| Días vacantes           | Auto          | SÍ          | Pre-llenado desde el Schedule           | Días sin colaborador asignado                              |
| Justificación           | Textarea      | SÍ          | Mín. 20 caracteres                       | Por qué se necesita refuerzo                               |
| Continuar a Nueva Requisición | Action  | SÍ          | —                                       | Lleva al formulario A pre-llenado                          |

---

## E) Filtros de Mis Requisiciones

| Campo                | Tipo de Input | Obligatorio | Descripción                                                |
| -------------------- | ------------- | ----------- | ---------------------------------------------------------- |
| Estado               | Multi-select  | NO          | Borradores / Pendientes / Rechazadas / Autorizadas / etc.  |
| Posición             | Select        | NO          | Catálogo de Posiciones                                      |
| Fecha de creación    | Date Range    | NO          | Rango                                                       |
| Buscar por ID/número | Text          | NO          | Búsqueda libre                                              |
