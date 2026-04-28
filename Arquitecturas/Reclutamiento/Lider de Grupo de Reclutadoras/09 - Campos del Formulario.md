---
tags:
  - arquitectura
  - rol/lider-de-grupo
aliases:
  - Campos Formulario Líder de Grupo
---

# 3. CAMPOS DEL FORMULARIO — LÍDER DE GRUPO

> [!info]
> El Líder de Grupo opera con los mismos formularios que una Reclutadora (ver `Reclutadora/Campos del Formulario.md`) **más** los formularios exclusivos de supervisión y reportes que se detallan abajo.

---

## Formulario de generación de reportes (exclusivo del Líder)

| Campo | Tipo de Input | Obligatorio | Validación | Descripción |
|---|---|---|---|---|
| Tipo de reporte | Select | SÍ | Cobertura del grupo / Desempeño individual / Casos escalados / Distribución de carga | Tipo de métrica a generar |
| Rango de fechas | DatePicker | SÍ | Fecha inicio < fecha fin | Periodo del reporte |
| Filtro por zona | Select multi | NO | Debe seleccionar opción del catálogo | Zonas a incluir |
| Filtro por Reclutadora | Select multi | NO | Solo Reclutadoras del grupo | Reclutadoras a incluir |
| Filtro por posición | Select multi | NO | Posiciones del catálogo | Posiciones a incluir |
| Comentarios | Textarea | NO | Máx. 1000 caracteres | Notas adicionales |
| Destinatario | Select | SÍ | Manager de Reclutamiento (auto) | A quién enviar |

---

## Formulario de comunicación con Reclutadora (chat/nota)

| Campo | Tipo de Input | Obligatorio | Validación | Descripción |
|---|---|---|---|---|
| Reclutadora | Auto | SÍ | Solo Reclutadoras del grupo | Destinataria del mensaje |
| Asunto | Text | SÍ | Mín. 5 caracteres | Resumen del mensaje |
| Mensaje | Textarea | SÍ | Mín. 10 caracteres, máx. 2000 | Contenido del mensaje |
| Adjuntos | File | NO | PDF/JPG/PNG, máx. 10 MB c/u | Archivos relacionados |

---

## Formulario de atención de incidencia (1er nivel)

| Campo | Tipo de Input | Obligatorio | Validación | Descripción |
|---|---|---|---|---|
| Reclutadora origen | Auto | SÍ | Reclutadora del grupo | Quién reportó la incidencia |
| Tipo de caso | Select | SÍ | Opciones del catálogo | Categoría del caso |
| Descripción | Textarea | SÍ | Mín. 20 caracteres | Detalle del caso |
| Acción tomada | Select | SÍ | Resuelto / Escalado al Manager | Decisión del Líder |
| Comentario / Justificación | Textarea | SÍ | Mín. 10 caracteres | Razonamiento de la acción |
