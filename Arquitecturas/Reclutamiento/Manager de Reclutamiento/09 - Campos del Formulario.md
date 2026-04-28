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

| Campo | Tipo de Input | Obligatorio | Validación | Descripción |
|---|---|---|---|---|
| Nombre completo | Text | SÍ | Mín. 3 caracteres | Nombre legal |
| Documento | Text | SÍ | Único en el sistema | Identificación oficial |
| Correo | Email | SÍ | Formato válido y único | Acceso al sistema |
| Teléfono | Text | SÍ | 10 dígitos | Contacto |
| Zona asignada | Select | SÍ | Catálogo de zonas | Zona principal del grupo |
| Nombre del grupo | Text | SÍ | Mín. 5 caracteres | Identificador del grupo |
| Foto | File | NO | JPG/PNG, máx. 2 MB | Foto de perfil |

---

## Formulario de alta de Reclutadora

| Campo | Tipo de Input | Obligatorio | Validación | Descripción |
|---|---|---|---|---|
| Nombre completo | Text | SÍ | Mín. 3 caracteres | Nombre legal |
| Documento | Text | SÍ | Único en el sistema | Identificación oficial |
| Correo | Email | SÍ | Formato válido y único | Acceso al sistema |
| Teléfono | Text | SÍ | 10 dígitos | Contacto |
| Zona asignada | Select | SÍ | Catálogo de zonas | Zona de operación |
| Líder de Grupo | Select | SÍ | Líderes activos | Líder al que pertenece |
| Foto | File | NO | JPG/PNG, máx. 2 MB | Foto de perfil |

---

## Formulario de inclusión en Blacklist

| Campo | Tipo de Input | Obligatorio | Validación | Descripción |
|---|---|---|---|---|
| Colaborador | Search | SÍ | Debe existir en Pool | Colaborador a vetar |
| Motivo del veto | Select | SÍ | Catálogo (3 inasistencias / Disputa / Falta grave) | Categoría |
| Descripción detallada | Textarea | SÍ | Mín. 30 caracteres | Detalle del caso |
| Evidencia | File | SÍ | Mín. 1 archivo, máx. 10 MB c/u | Documentos / fotos |
| Fecha del incidente | DatePicker | SÍ | Fecha pasada | Cuándo ocurrió |

---

## Formulario de resolución de disputa

| Campo | Tipo de Input | Obligatorio | Validación | Descripción |
|---|---|---|---|---|
| Caso | Auto | SÍ | Caso abierto | Disputa a resolver |
| Decisión | Select | SÍ | Mantener veto / Remover de Blacklist | Resolución final |
| Comentario | Textarea | SÍ | Mín. 30 caracteres | Justificación |
| Notificar a las partes | Checkbox | SÍ | Default: SÍ | Envío de notificación |

---

## Formulario de generación de reporte global

| Campo | Tipo de Input | Obligatorio | Validación | Descripción |
|---|---|---|---|---|
| Tipo de reporte | Select | SÍ | Cobertura global / Comparativa Líderes / Comparativa zonas / Tiempos / Casos escalados | Tipo de métrica |
| Rango de fechas | DatePicker | SÍ | Inicio < fin | Periodo |
| Filtro por zona | Select multi | NO | Catálogo | Zonas a incluir |
| Filtro por Líder | Select multi | NO | Líderes activos | Líderes a incluir |
| Formato de exportación | Select | NO | CSV / PDF / Excel | Formato del export |
| Destinatario | Select | NO | Email Dirección / Otros | A quién enviar |
