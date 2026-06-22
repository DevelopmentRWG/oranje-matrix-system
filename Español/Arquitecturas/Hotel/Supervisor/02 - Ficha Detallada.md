---
tags:
  - arquitectura
  - rol/supervisor-hotel
aliases:
  - Ficha Detallada Supervisor
---

# FICHA DETALLADA — SUPERVISOR

---

| Campo                          | Contenido                                                                                                                                                                                                                              |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **ID Rol**                     | ROL-H-01                                                                                                                                                                                                                               |
| **Nombre del Rol**             | 🦺 Supervisor (SUP)                                                                                                                                                                                                                    |
| **Descripción**                | Rol operativo del módulo Hotel. Crea las requisiciones de personal y reporta accidentes laborales. Subordinado del Manager de Área / Gerente de Departamento.                                                                       |
| **Objetivo en el Sistema**     | Formalizar la necesidad de personal del hotel mediante requisiciones; reportar accidentes con detalle presencial.                                                                                                                      |
| **Módulos que Usa**            | Dashboard · Requisiciones · Schedule (consulta) · Timesheet (consulta) · Mi Personal · Accidentes · Notificaciones                                                                                                                     |
| **Permisos (CRUD)**            | Crear · Ver · Editar (sin eliminar excepto borradores) · Reportar accidentes                                                                                                                                                            |
| **Acciones Principales**       | Crear requisición · Editar borrador · Enviar a autorización · Sugerir refuerzo · Reportar accidente Escenario A · Reportar accidente Escenario B · Poner Stand-by                                                                      |
| **Nivel de Acceso**            | 🟡 Medio (operativo)                                                                                                                                                                                                                   |
| **Dispositivo**                | Mobile (app del Supervisor) / Tablet / Desktop                                                                                                                                                                                          |
| **Frecuencia de Uso**          | Alta — diaria                                                                                                                                                                                                                          |
| **Dolor / Necesidad Actual**   | Crear requisiciones tarda mucho desde Desktop si no está cerca de la oficina; al detectar un accidente debe acudir físicamente y registrar en papel; falta de visibilidad sobre las requisiciones rechazadas hasta que entra al sistema. |
| **Notas UX / Recomendaciones** | App mobile prioritaria con creación rápida (3-4 pasos), notificaciones push de accidentes y rechazos, formulario de accidente con captura de foto y geolocalización opcional, dashboard con bandeja de "necesita acción" priorizada. |
