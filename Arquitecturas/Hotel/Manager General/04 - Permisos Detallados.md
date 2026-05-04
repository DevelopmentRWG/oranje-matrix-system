---
tags:
  - arquitectura
  - rol/manager-general
aliases:
  - Permisos Detallados Manager General
---

# PERMISOS DETALLADOS POR ROL

## ROL-H-03 · 🧑‍✈️ Manager General (GM)

> [!info]
> Rol activo **únicamente en jerarquía extendida**. En jerarquía simple este rol no existe.

---

| Módulo                | Funcionalidad                                       | Permiso        | Descripción                                                                  |
| --------------------- | --------------------------------------------------- | -------------- | ---------------------------------------------------------------------------- |
| **Requisiciones**     | Ver vista global del hotel                          | 👁️ Ver         | Todas las requisiciones, todos los deptos                                    |
| Requisiciones         | Filtrar por Gerente / depto / estado / urgencia     | 👁️ Ver         | Filtros amplios para análisis                                                |
| Requisiciones         | Comentar al expediente                               | 📝 C · E       | Visible para el Gerente de Departamento                                      |
| Requisiciones         | Escalar requisición demorada                         | 🔍 Supervisar  | Notifica al Manager de Reclutamiento                                         |
| Requisiciones         | Autorizar / Rechazar                                 | —              | Sin acceso (RR-H-14)                                                         |
| **Schedule**          | Ver Schedule global del hotel                        | 👁️ Ver         | Consolidado de todos los deptos                                              |
| Schedule              | Editar Schedule                                      | —              | Sin acceso                                                                    |
| Schedule              | Exportar Schedule consolidado                        | 👁️ Ver         | PDF / CSV / Excel                                                             |
| **Timesheet**         | Ver Timesheet global del hotel                       | 👁️ Ver         | Consolidado de todos los deptos                                              |
| Timesheet             | Generar QR / Corregir ponche                         | —              | Sin acceso                                                                    |
| Timesheet             | Ver Indicador de Cumplimiento (consolidado)         | 👁️ Ver         | Por depto y por colaborador                                                   |
| Timesheet             | Ver Indicador de Lunch Extendido                    | —              | Sin acceso (RR-H-15)                                                         |
| Timesheet             | Exportar Timesheet consolidado                       | 👁️ Ver         | PDF / CSV / Excel                                                             |
| **Mi Equipo del Hotel** | Ver Gerentes de Departamento                       | 👁️ Ver         | Lista con métricas (cobertura, tiempo de autorización, casos)                |
| Mi Equipo del Hotel   | Ver Supervisores                                     | 👁️ Ver         | Lista con métricas                                                           |
| Mi Equipo del Hotel   | Comunicar con Gerente / Supervisor                   | 📝 C · E       | Chat / nota interna                                                           |
| Mi Equipo del Hotel   | Solicitar reporte específico                         | ➕ Crear        | Notifica al Gerente con la solicitud                                         |
| Mi Equipo del Hotel   | Dar de alta / baja                                   | —              | Sin acceso (eso es del Administrador)                                         |
| **Reportes**          | Generar reporte ejecutivo                            | ➕ Crear        | Con plantillas (cobertura, desempeño, accidentes, calidad, indicadores)      |
| Reportes              | Exportar (CSV / PDF / Excel)                         | 👁️ Ver         | —                                                                             |
| Reportes              | Enviar a dirección                                   | ➕ Crear        | Email / link interno                                                          |
| Reportes              | Programar envío recurrente                           | 📝 C · E       | Semanal / mensual                                                             |
| Reportes              | Ver histórico de reportes                            | 👁️ Ver         | Lista con destinatario y estado                                               |
| **Dashboard**         | Ver KPIs globales del hotel                          | 👁️ Ver         | Cobertura, cumplimiento, calidad, accidentes                                 |
| Dashboard             | Heatmap por depto y día                              | 👁️ Ver         | Visualización ejecutiva                                                       |
| Dashboard             | Ranking de Gerentes                                  | 👁️ Ver         | Por velocidad de autorización y cobertura                                    |
| **Blacklist**         | Consultar Blacklist                                  | 👁️ Ver         | Solo lectura                                                                 |
| **Sistema** (transv.) | Recibir notificación                                 | 👁️ Ver         | Alertas críticas globales                                                    |
