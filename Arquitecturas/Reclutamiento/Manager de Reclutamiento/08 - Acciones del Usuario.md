---
tags:
  - arquitectura
  - rol/manager-reclutamiento
aliases:
  - Acciones Manager
---

# 6. ACCIONES DEL USUARIO — MANAGER DE RECLUTAMIENTO

---

| Acción | Resultado |
|---|---|
| Tomar requisición personal (caso especial) | Sistema registra intervención con motivo en log; semáforo a Amarillo |
| Asignar manual a Reclutadora | Sistema notifica a la Reclutadora; queda en log con justificación |
| Reasignar requisición | Reclutadora original pierde acceso; nueva la recibe con notificación |
| Forzar cambio de semáforo | Cambio aplicado con log auditable; notifica a involucrados |
| Aprobar inclusión en Blacklist | Colaborador queda vetado; notifica al colaborador y a Reclutadora |
| Resolver disputa de Blacklist | Decisión final aplicada; cierra caso con comentario |
| Remover de Blacklist | Colaborador reactivado en Pool; queda registro de la remoción |
| Dar de alta Líder de Grupo | Sistema crea cuenta con rol asignado; envía credenciales |
| Dar de alta Reclutadora | Sistema crea cuenta y asigna al Líder seleccionado |
| Editar usuario | Sistema aplica cambios; queda registro |
| Mover Reclutadora a otro Líder | Reclutadora cambia de grupo; notifica a ambos Líderes |
| Marcar usuario como inactivo / vacaciones / baja | Sistema desactiva acceso; queda registro |
| Investigar caso de incidencia | Acceso a evidencia, comentarios y recomendaciones |
| Resolver incidencia | Cierre con decisión final y comentario obligatorio |
| Escalar a Dirección | Notifica a Director con todo el contexto |
| Generar reporte global | Sistema compila datos del periodo |
| Exportar reporte | Descarga archivo (CSV/PDF/Excel) |
| Programar envío de reporte | Configura recurrencia (semanal/mensual) |
| Cancelar acción | Cambios no se guardan |
