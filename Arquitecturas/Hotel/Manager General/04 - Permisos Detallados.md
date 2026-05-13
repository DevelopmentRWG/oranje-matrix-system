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
> El Manager General **siempre existe** (jerarquía simple y extendida). En simple opera también como Manager de Área (mismo usuario, dos roles). En extendida supervisa a los Managers de Área y mantiene visibilidad global, pero también puede ejecutar acciones operativas cuando aplica.

---

| Módulo                | Funcionalidad                                       | Permiso        | Descripción                                                                                                                                          |
| --------------------- | --------------------------------------------------- | -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Requisiciones**     | Ver vista global del hotel                          | 👁️ Ver         | Todas las requisiciones, todos los deptos                                                                                                            |
| Requisiciones         | Filtrar por Manager de Área / depto / estado / urgencia | 👁️ Ver     | Filtros amplios para análisis                                                                                                                        |
| Requisiciones         | **Crear requisición**                                | ➕ Crear        | Compartido con Manager de Área y Supervisor                                                                                                          |
| Requisiciones         | Editar borrador de requisición                       | 📝 C · E       | Antes de enviar a autorización                                                                                                                       |
| Requisiciones         | **Autorizar requisición**                            | ✓ Aprobar      | Compartido con Manager de Área — RR-H-02                                                                                                              |
| Requisiciones         | **Rechazar con observaciones**                       | ✗ Rechazar     | Compartido con Manager de Área                                                                                                                       |
| Requisiciones         | Eliminar requisición con posiciones                  | 📝 C · E       | Con journal individual por posición                                                                                                                  |
| Requisiciones         | Comentar al expediente                               | 📝 C · E       | Visible para el Manager de Área                                                                                                                      |
| Requisiciones         | Escalar requisición demorada                         | 🔍 Supervisar  | Notifica al Manager de Reclutamiento                                                                                                                 |
| **Schedule**          | Ver Schedule global del hotel                        | 👁️ Ver         | Consolidado de todos los deptos (exclusivo del GM)                                                                                                   |
| Schedule              | Ver Schedule de cualquier depto                      | 👁️ Ver         | Drill-down por departamento                                                                                                                          |
| Schedule              | **Editar Schedule**                                  | 📝 C · E       | Cuando opera como Manager de Área o interviene puntualmente                                                                                          |
| Schedule              | Exportar Schedule consolidado                        | 👁️ Ver         | PDF / CSV / Excel                                                                                                                                     |
| **Timesheet**         | Ver Timesheet global del hotel                       | 👁️ Ver         | Consolidado de todos los deptos                                                                                                                      |
| Timesheet             | **Generar / Renovar QR**                             | ➕ Crear        | Compartido con Manager de Área — RR-H-09                                                                                                              |
| Timesheet             | **Corregir ponche**                                  | 📝 C · E       | Con justificación obligatoria — log auditable                                                                                                        |
| Timesheet             | Ver Indicador de Cumplimiento (consolidado)         | 👁️ Ver         | Por depto y por colaborador                                                                                                                          |
| Timesheet             | Ver Indicador de Lunch Extendido                    | —              | Sin acceso (RR-H-15)                                                                                                                                 |
| Timesheet             | Exportar Timesheet consolidado                       | 👁️ Ver         | PDF / CSV / Excel                                                                                                                                     |
| **Mi Personal**       | Ver colaboradores del hotel                          | 👁️ Ver         | Vista global de todos los deptos                                                                                                                     |
| Mi Personal           | **Poner colaborador en Stand-by (Rosa)**             | 📝 C · E       | Compartido con Supervisor y Manager de Área — RR-H-11                                                                                                |
| Mi Personal           | **Reportar colaborador (Rojo)**                      | 🚨 Reportar    | Compartido con Supervisor y Manager de Área — RR-H-10                                                                                                |
| **Accidentes**        | Ver accidentes del hotel                             | 👁️ Ver         | Global, todos los deptos                                                                                                                              |
| Accidentes            | **Reportar accidente — Escenarios A y B**            | ➕ Crear        | Compartido con Supervisor y Manager de Área — RR-H-19                                                                                                |
| **Mi Equipo del Hotel** | Ver Managers de Área                               | 👁️ Ver         | Lista con métricas (cobertura, tiempo de autorización, casos)                                                                                        |
| Mi Equipo del Hotel   | Ver Supervisores                                     | 👁️ Ver         | Lista con métricas                                                                                                                                   |
| Mi Equipo del Hotel   | Comunicar con M.Área / Supervisor                    | 📝 C · E       | Chat / nota interna                                                                                                                                  |
| Mi Equipo del Hotel   | Solicitar reporte específico                         | ➕ Crear        | Notifica al destinatario con la solicitud                                                                                                            |
| Mi Equipo del Hotel   | Dar de alta / baja                                   | —              | Sin acceso (eso es del Administrador)                                                                                                                |
| **Reportes**          | Generar reporte ejecutivo                            | ➕ Crear        | Plantillas (cobertura, desempeño, accidentes, calidad, indicadores) — exclusivo del GM                                                              |
| Reportes              | Exportar (CSV / PDF / Excel)                         | 👁️ Ver         | —                                                                                                                                                     |
| Reportes              | Enviar a dirección                                   | ➕ Crear        | Email / link interno                                                                                                                                 |
| Reportes              | Programar envío recurrente                           | 📝 C · E       | Semanal / mensual / trimestral                                                                                                                       |
| Reportes              | Ver histórico de reportes                            | 👁️ Ver         | Lista con destinatario y estado                                                                                                                      |
| **Dashboard**         | Ver KPIs globales del hotel                          | 👁️ Ver         | Cobertura, cumplimiento, calidad, accidentes — vista ejecutiva exclusiva                                                                            |
| Dashboard             | Heatmap por depto y día                              | 👁️ Ver         | Visualización ejecutiva                                                                                                                              |
| Dashboard             | Ranking de Managers de Área                          | 👁️ Ver         | Por velocidad de autorización y cobertura                                                                                                            |
| **Blacklist**         | Consultar Blacklist                                  | 👁️ Ver         | Solo lectura                                                                                                                                          |
| **Sistema** (transv.) | Recibir notificación                                 | 👁️ Ver         | Alertas críticas globales                                                                                                                            |
