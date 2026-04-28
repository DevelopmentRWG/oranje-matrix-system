---
tags:
  - arquitectura
  - rol/lider-de-grupo
aliases:
  - Validaciones Líder de Grupo
---

# 4. VALIDACIONES — LÍDER DE GRUPO DE RECLUTADORAS

---

## Validaciones operativas (heredadas de Reclutadora)

| Caso | Comportamiento del Sistema |
|---|---|
| Campos obligatorios vacíos en formulario de colaborador | Bloquea envío y muestra mensaje junto a cada campo inválido |
| Documento de identidad ya existe | Bloquea creación |
| Candidato en Blacklist | Bloquea asignación con alerta visible |
| Asignar colaborador no validado | Bloquea asignación |
| Asignar colaborador ya activo en otro hotel | Bloquea (regla RR-05 de exclusividad) |
| Marcar requisición cubierta sin 100% | Bloquea acción |
| Tomar requisición ya tomada | Muestra "Esta requisición ya fue tomada por [usuario]" |

---

## Validaciones exclusivas del Líder

| Caso | Comportamiento del Sistema |
|---|---|
| Generar reporte sin rango de fechas | Bloquea generación; muestra "Debe seleccionar rango de fechas" |
| Enviar reporte sin métricas válidas | Muestra "El reporte no contiene datos para el periodo seleccionado" |
| Comunicar con Reclutadora fuera del grupo | Bloquea acción; muestra "Solo puedes comunicar con Reclutadoras de tu grupo" |
| Atender incidencia sin justificación | Bloquea cierre; solicita comentario obligatorio |
| Acceso a métricas de otro grupo | Bloquea acceso; muestra "Solo puedes ver métricas de tu grupo" |
| Exportar reporte vacío | Bloquea exportación |
