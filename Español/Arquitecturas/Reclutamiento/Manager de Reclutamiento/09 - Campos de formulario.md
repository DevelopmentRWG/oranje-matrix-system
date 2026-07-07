---
tags:
  - arquitectura
  - rol/manager-reclutamiento
aliases:
  - Campos Formulario Manager
---

# 3. CAMPOS DEL FORMULARIO — MANAGER

---

## Formulario de alta de Líder de Grupo

| Campo            | Tipo de Input | Obligatorio | Validación             | Descripción              |
| ---------------- | ------------- | ----------- | ---------------------- | ------------------------ |
| Nombre completo  | Text          | SÍ          | Mín. 3 caracteres      | Nombre legal             |
| Documento        | Text          | SÍ          | Único en el sistema    | Identificación oficial   |
| Correo           | Email         | SÍ          | Formato válido y único | Acceso al sistema        |
| Teléfono         | Text          | SÍ          | 10 dígitos             | Contacto                 |
| Zona asignada    | Select        | SÍ          | Catálogo de zonas      | Zona principal del grupo |
| Nombre del grupo | Text          | SÍ          | Mín. 5 caracteres      | Identificador del grupo  |
| Foto             | File          | NO          | JPG/PNG, máx. 2 MB     | Foto de perfil           |

---

## Formulario de alta de Reclutadora

| Campo           | Tipo de Input | Obligatorio | Validación             | Descripción            |
| --------------- | ------------- | ----------- | ---------------------- | ---------------------- |
| Nombre completo | Text          | SÍ          | Mín. 3 caracteres      | Nombre legal           |
| Documento       | Text          | SÍ          | Único en el sistema    | Identificación oficial |
| Correo          | Email         | SÍ          | Formato válido y único | Acceso al sistema      |
| Teléfono        | Text          | SÍ          | 10 dígitos             | Contacto               |
| Zona asignada   | Select        | SÍ          | Catálogo de zonas      | Zona de operación      |
| Líder de Grupo  | Select        | SÍ          | Líderes activos        | Líder al que pertenece |
| Foto            | File          | NO          | JPG/PNG, máx. 2 MB     | Foto de perfil         |

---

## Formulario de inclusión en Blacklist

| Campo                 | Tipo de Input | Obligatorio | Validación                                         | Descripción         |
| --------------------- | ------------- | ----------- | -------------------------------------------------- | ------------------- |
| Colaborador           | Search        | SÍ          | Debe existir en Pool                               | Colaborador a vetar |
| Motivo del veto       | Select        | SÍ          | Catálogo (3 inasistencias / Disputa / Falta grave) | Categoría           |
| Descripción detallada | Textarea      | SÍ          | Mín. 30 caracteres                                 | Detalle del caso    |
| Evidencia             | File          | SÍ          | Mín. 1 archivo, máx. 10 MB c/u                     | Documentos / fotos  |
| Fecha del incidente   | DatePicker    | SÍ          | Fecha pasada                                       | Cuándo ocurrió      |

---

## Formulario de generación de reporte global

| Campo | Tipo de Input | Obligatorio | Validación | Descripción |
|---|---|---|---|---|
| Tipo de reporte | Select | SÍ | Cobertura global / Comparativa Líderes / Comparativa zonas / Tiempos / Casos escalados | Tipo de métrica |
| Rango de fechas | DatePicker | SÍ | Inicio < fin | Periodo |
| Filtro por zona | Select multi | NO | Catálogo | Zonas a incluir |
| Filtro por Líder | Select multi | NO | Líderes activos | Líderes a incluir |
| Formato de exportación | Select | NO | CSV / PDF / Excel | Formato del export |
| Destinatario | Select | NO | Mi supervisión / Comercial / Solo yo | A quién enviar |

---

## Caso de incidencia (datos del caso)

| Campo | Tipo de Input | Obligatorio | Validación | Descripción |
|---|---|---|---|---|
| ID del caso | Auto | — | — | Identificador generado por el sistema (INC-XX) |
| Tipo de incidencia | Select | SÍ | Catálogo | Sobrecarga de Reclutadora / Conflicto candidato-hotel / Disputa de cobertura comercial / Incumplimiento de SLA, etc. |
| Origen | Auto | SÍ | Líder / Inspector / Sistema | Quién escaló el caso |
| Zona | Auto | SÍ | Catálogo de zonas | Zona del caso |
| Hotel afectado | Search | NO (si aplica) | Catálogo de hoteles | Hotel implicado en el caso |
| Descripción | Textarea | SÍ | Mín. 30 caracteres | Detalle del problema |
| Evidencia | File | NO | Archivos del que escaló | Adjuntos (investigación del Inspector, reportes, etc.) |
| Involucrados | Auto | — | — | Líder, Reclutadora, Inspector, hotel (RF-30) |
| Prioridad | Select | NO | Crítica / Alta / Media / Baja | **Recurso de UI del mockup; pendiente de confirmar si es campo oficial** |
| Fecha | Auto | — | — | Fecha de escalamiento |
| Estado | Auto | — | Ver [[13 - Estados de Incidencia]] | Estado actual del caso |

---

## Formulario de resolución de incidencia (RF-30)

| Campo | Tipo de Input | Obligatorio | Validación | Descripción |
|---|---|---|---|---|
| Caso | Auto | SÍ | Caso en investigación | Caso a resolver |
| Decisión | Select | SÍ | Resolver / Escalar a comercial / Solicitar más información | Decisión final (RF-30) |
| Comentario | Textarea | SÍ | Obligatorio (mín. 30 caracteres) | Justificación de la decisión |
| (al confirmar) Notifica a involucrados | Auto | SÍ | — | Líder, Reclutadora, Inspector, hotel (RF-30) |

---

## Formulario de escalamiento a comercial (RF-31)

| Campo | Tipo de Input | Obligatorio | Validación | Descripción |
|---|---|---|---|---|
| Destinatario | Select | SÍ | BD / BDC del hotel afectado | A quién se escala |
| Contexto | Textarea | SÍ | Obligatorio | Contexto del escalamiento |
| Evidencia | File | NO | Archivos | Adjuntos para comercial |
