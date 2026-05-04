---
tags:
  - arquitectura
  - rol/manager-del-hotel
aliases:
  - Ficha Detallada Manager del Hotel
---

# FICHA DETALLADA — MANAGER DEL HOTEL

---

| Campo                          | Contenido                                                                                                                                                                                                                                              |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **ID Rol**                     | ROL-H-02                                                                                                                                                                                                                                               |
| **Nombre del Rol**             | 🧑‍💼 Manager del Hotel / Gerente de Departamento                                                                                                                                                                                                       |
| **Descripción**                | Rol de supervisión del lado del hotel. Autoriza/rechaza requisiciones del Supervisor (capa de seguridad), gestiona Schedule y Timesheet, genera QR de ponchado y administra a los colaboradores asignados.                                            |
| **Objetivo en el Sistema**     | Validar las solicitudes de personal, gestionar el Schedule y Timesheet del depto, y mantener la operación diaria.                                                                                                                                      |
| **Módulos que Usa**            | Dashboard · Requisiciones · Schedule · Timesheet · Mi Personal · Blacklist (consulta) · Notificaciones                                                                                                                                                  |
| **Permisos (CRUD)**            | Crear · Ver · Editar · Aprobar · Rechazar · Reportar                                                                                                                                                                                                   |
| **Acciones Principales**       | Autorizar requisición · Rechazar con observaciones · Generar QR · Editar Schedule · Corregir ponche · Poner Stand-by (Rosa) · Reportar (Rojo) · Eliminar requisición con posiciones                                                                    |
| **Nivel de Acceso**            | 🟠 Alto (en su depto)                                                                                                                                                                                                                                  |
| **Dispositivo**                | Desktop / Tablet                                                                                                                                                                                                                                       |
| **Frecuencia de Uso**          | Alta — diaria                                                                                                                                                                                                                                          |
| **Dolor / Necesidad Actual**   | Falta de visibilidad sobre las requisiciones pendientes de revisión, errores frecuentes en el Schedule (turnos cruzados), corrección manual de ponches sin trazabilidad, ausencia de alertas tempranas sobre cumplimiento de Timesheet.                |
| **Notas UX / Recomendaciones** | Bandeja de pendientes con badge rojo si lleva >24h sin revisar; vista consolidada Schedule + Timesheet; QR renovable con 1 click; corrección de ponche con justificación obligatoria visible en log; alertas push en mobile cuando sale notificación crítica. |
