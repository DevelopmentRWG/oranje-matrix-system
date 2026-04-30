---
tags:
  - arquitectura
  - rol/manager-reclutamiento
aliases:
  - Validaciones Manager
---

# 4. VALIDACIONES — MANAGER DE RECLUTAMIENTO

---

| Caso                                    | Comportamiento del Sistema                                                |
| --------------------------------------- | ------------------------------------------------------------------------- |
| Tomar requisición sin justificación     | Solicita comentario obligatorio (es excepcional)                          |
| Asignar manual sin comentario           | Bloquea acción; muestra "La asignación manual requiere justificación"     |
| Forzar cambio de semáforo sin motivo    | Bloquea cambio; solicita comentario obligatorio                           |
| Aprobar Blacklist sin evidencia adjunta | Bloquea creación; muestra "Debe adjuntar al menos una evidencia"          |
| Aprobar Blacklist sin descripción       | Bloquea creación; muestra "Debe describir el motivo (mín. 30 caracteres)" |
| Remover de Blacklist sin justificación  | Bloquea acción; solicita comentario                                       |
| Resolver disputa sin comentario         | Bloquea cierre; solicita justificación                                    |
| Crear Líder con email duplicado         | Bloquea alta; muestra "Email ya existe en el sistema"                     |
| Crear Reclutadora sin Líder asignado    | Bloquea alta; muestra "Debe asignar un Líder"                             |
| Editar propio rol                       | Bloquea acción; muestra "No puedes editar tu propio rol"                  |
| Eliminar Líder con Reclutadoras activas | Bloquea baja; muestra "Reasigne primero las Reclutadoras del grupo"       |
| Generar reporte sin rango de fechas     | Bloquea generación                                                        |
| Generar reporte con periodo vacío       | Muestra "El reporte no contiene datos para el periodo"                    |
| Escalar a Dirección sin contexto        | Bloquea escalamiento; solicita resumen                                    |
