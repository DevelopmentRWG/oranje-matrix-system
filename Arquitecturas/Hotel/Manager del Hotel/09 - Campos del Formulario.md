---
tags:
  - arquitectura
  - rol/manager-del-hotel
aliases:
  - Campos Formulario Manager del Hotel
---

# 3. CAMPOS DEL FORMULARIO — MANAGER DEL HOTEL

> [!info]
> El Manager del Hotel **no llena formularios de creación**, pero sí completa varios formularios de acciones (rechazo, eliminación con posiciones, corrección de ponche, reporte de colaborador, etc.). A continuación los campos requeridos por acción.

---

## A) Formulario de Rechazo de Requisición (RF-H-06)

| Campo            | Tipo de Input | Obligatorio | Validación                              | Descripción                                                |
| ---------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Motivo           | Select        | SÍ          | Catálogo: Posiciones erróneas / Modalidad incorrecta / Datos incompletos / Falta justificación / Otro | Categoría del rechazo                                      |
| Observaciones    | Textarea      | SÍ          | Mín. 20 caracteres                      | Detalle de lo que el Supervisor debe corregir              |
| Adjuntos         | File          | NO          | PDF/JPG/PNG, máx. 5 MB                  | Evidencia o documento de soporte (opcional)                |

---

## B) Formulario de Eliminación de Requisición con Posiciones (RF-H-07)

| Campo            | Tipo de Input | Obligatorio | Validación                              | Descripción                                                |
| ---------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Justificación    | Textarea      | SÍ          | Mín. 20 caracteres                      | Por qué se elimina la requisición con posiciones           |
| Confirmación     | Checkbox      | SÍ          | Debe estar marcado                      | "Confirmo que las posiciones serán eliminadas físicamente" |

---

## C) Formulario de Corrección de Ponche (RF-H-14)

| Campo                  | Tipo de Input | Obligatorio | Validación                              | Descripción                                                |
| ---------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Colaborador            | Select        | SÍ          | Lista de colaboradores asignados        | Colaborador a corregir                                     |
| Día                    | Date          | SÍ          | Día dentro de la semana en curso        | Fecha del ponche a corregir                                |
| Tipo de ponche         | Select        | SÍ          | Catálogo: Entrada / Salida Lunch / Entrada Lunch / Salida Break / Entrada Break / Salida | Cuál de los 6 ponches                                      |
| Hora corregida         | Time          | SÍ          | Formato HH:MM (24h)                     | Nueva hora del ponche                                      |
| Motivo de corrección   | Textarea      | SÍ          | Mín. 20 caracteres                      | Justificación obligatoria — queda en log auditable        |
| Adjuntos               | File          | NO          | PDF/JPG/PNG, máx. 5 MB                  | Evidencia (opcional)                                       |

---

## D) Formulario de Stand-by (Rosa) — RF-H-17

| Campo            | Tipo de Input | Obligatorio | Validación                              | Descripción                                                |
| ---------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Colaborador      | Select        | SÍ          | Lista de colaboradores asignados        | Colaborador a poner en Stand-by                            |
| Motivo           | Select        | SÍ          | Catálogo: Vacaciones del colaborador / Temporada baja / Decisión del hotel / Otro | Razón del Stand-by                                         |
| Notas            | Textarea      | NO          | Máx. 500 caracteres                     | Contexto adicional                                          |

---

## E) Formulario de Reporte de Colaborador (Rojo) — RF-H-18

| Campo            | Tipo de Input | Obligatorio | Validación                              | Descripción                                                |
| ---------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Colaborador      | Select        | SÍ          | Lista de colaboradores asignados        | Colaborador a reportar                                     |
| Motivo           | Select        | SÍ          | Catálogo: Falta grave / Mala conducta / Robo / Conflicto / Otro | Razón del reporte                                          |
| Descripción      | Textarea      | SÍ          | Mín. 50 caracteres                      | Detalle del incidente para la investigación del Inspector |
| Evidencia        | File          | NO          | PDF/JPG/PNG, máx. 10 MB                 | Fotos, videos o documentos                                 |
| Testigos         | Text          | NO          | Mín. 3 caracteres si se llena           | Nombres de testigos                                        |

---

## F) Filtros del Schedule / Timesheet

| Campo                    | Tipo de Input | Obligatorio | Descripción                                                |
| ------------------------ | ------------- | ----------- | ---------------------------------------------------------- |
| Departamento             | Select        | NO          | Solo en jerarquía extendida (alcance del Gerente)          |
| Posición                 | Select        | NO          | Catálogo de Posiciones                                     |
| Estado de cobertura       | Select        | NO          | Cubierta / Parcial / Vacante                               |
| Semana                   | Date Range    | SÍ          | Selector de semana                                         |
| Buscar (nombre/posición) | Text          | NO          | Búsqueda libre                                             |
