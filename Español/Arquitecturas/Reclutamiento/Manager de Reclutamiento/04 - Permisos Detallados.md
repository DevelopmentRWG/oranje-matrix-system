---
tags:
  - arquitectura
  - rol/manager-reclutamiento
aliases:
  - Permisos Detallados Manager
---

# PERMISOS DETALLADOS POR ROL

## ROL-03 · 🧑‍💼 Manager de Reclutamiento

---

| Módulo        | Funcionalidad                     | Permiso       | Descripción                                      |
| ------------- | --------------------------------- | ------------- | ------------------------------------------------ |
| Requisición   | Ver vista global de requisiciones | 👁️ Ver       | Todas las del depto                              |
| Requisición   | Tomar requisición personal        | ➕ Crear       | Caso especial (excepcional)                      |
| Requisición   | Asignar manual a Reclutadora      | ✓ Aprobar     | Caso VIP, balanceo, ausencia (con justificación) |
| Requisición   | Reasignar requisición             | 📝 Editar     | Excepcional                                      |
| Requisición   | Forzar cambio de semáforo         | 📝 Editar     | Con log auditable                                |
| Reclutamiento | Ver Pool de Colaboradores         | 👁️ Ver       | Consulta completa                                |
| Reclutamiento | Crear colaborador (apoyo)         | ➕ Crear       | Backup operativo                                 |
| Reclutamiento | Editar colaborador                | 📝 Editar     | Captura/ajuste de datos                          |
| Reclutamiento | Asignar a hotel (apoyo)           | ➕ Crear       | Cuando interviene excepcionalmente               |
| **Blacklist** | Consultar Blacklist               | 👁️ Ver       | Vista completa                                   |
| **Blacklist** | Agregar a Blacklist               | ➕ Crear       | Igual que cualquier rol del depto                |
| **Blacklist** | Resolver disputa                  | 🔍 Investigar | Decisión final — Manager exclusivo               |
| **Blacklist** | Remover de Blacklist              | 📝 Editar     | Con justificación — Manager exclusivo            |
| **Mi Equipo** | Ver Líderes de Grupo              | 👁️ Ver       | Vista anidada                                    |
| **Mi Equipo** | Ver Reclutadoras                  | 👁️ Ver       | Filtro por Líder                                 |
| **Mi Equipo** | Dar de alta Líder                 | ➕ Crear       | Modal de alta                                    |
| **Mi Equipo** | Dar de alta Reclutadora           | ➕ Crear       | Asignar a Líder                                  |
| **Mi Equipo** | Editar usuario                    | 📝 Editar     | Cambiar rol/zona/grupo                           |
| **Mi Equipo** | Mover Reclutadora                 | 📝 Editar     | Reasignación organizacional                      |
| **Mi Equipo** | Marcar inactivo / baja            | 📝 Editar     | Eliminación lógica                               |
| Incidencias   | Ver caso abierto                  | 👁️ Ver       | Lista de escalamientos                           |
| Incidencias   | Investigar caso                   | 🔍 Investigar | Recopila evidencia                               |
| Incidencias   | Resolver caso                     | ✓ Aprobar     | Decisión final con comentario                    |
| Incidencias   | Escalar a Dirección               | 📝 Editar     | Casos críticos                                   |
| Reportes      | Ver reportes recibidos            | 👁️ Ver       | De Líderes                                       |
| Reportes      | Generar reporte global            | ➕ Crear       | Para Dirección                                   |
| Reportes      | Exportar                          | 👁️ Ver       | CSV/PDF/Excel                                    |
| Dashboard     | Ver KPIs globales                 | 👁️ Ver       | Cobertura del depto                              |
| Sistema       | Recibir notificación              | 👁️ Ver       | Alertas críticas                                 |
