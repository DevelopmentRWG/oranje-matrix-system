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

| Módulo | Funcionalidad | Permiso | Descripción |
|---|---|---|---|
| Bandeja | Ver vista global de requisiciones | 👁️ Ver | Todas las del depto |
| Bandeja | Tomar requisición personal | ➕ Crear | Caso especial (excepcional) |
| Bandeja | Asignar manual a Reclutadora | ✓ Aprobar | Caso VIP, balanceo, ausencia (con justificación) |
| Bandeja | Reasignar requisición | 📝 Editar | Excepcional |
| Bandeja | Forzar cambio de semáforo | 📝 Editar | Con log auditable |
| Pool | Ver Pool | 👁️ Ver | Consulta completa |
| Pool | Editar colaborador | ✅ CRUD | Por ser Manager |
| Pool | Crear colaborador (apoyo) | ➕ Crear | Backup operativo |
| **Blacklist** | Consultar Blacklist | 👁️ Ver | Vista completa |
| **Blacklist** | Aprobar inclusión | ➕ Crear | Único rol con permiso |
| **Blacklist** | Resolver disputa | 🔍 Investigar | Decisión final |
| **Blacklist** | Remover de Blacklist | 📝 Editar | Con justificación |
| **Mi Equipo** | Ver Líderes de Grupo | 👁️ Ver | Vista anidada |
| **Mi Equipo** | Ver Reclutadoras | 👁️ Ver | Filtro por Líder |
| **Mi Equipo** | Dar de alta Líder | ➕ Crear | Modal de alta |
| **Mi Equipo** | Dar de alta Reclutadora | ➕ Crear | Asignar a Líder |
| **Mi Equipo** | Editar usuario | 📝 Editar | Cambiar rol/zona/grupo |
| **Mi Equipo** | Mover Reclutadora | 📝 Editar | Reasignación organizacional |
| **Mi Equipo** | Marcar inactivo / baja | 📝 Editar | Eliminación lógica |
| Incidencias | Ver caso abierto | 👁️ Ver | Lista de escalamientos |
| Incidencias | Investigar caso | 🔍 Investigar | Recopila evidencia |
| Incidencias | Resolver caso | ✓ Aprobar | Decisión final con comentario |
| Incidencias | Escalar a Dirección | 📝 Editar | Casos críticos |
| Reportes | Ver reportes recibidos | 👁️ Ver | De Líderes |
| Reportes | Generar reporte global | ➕ Crear | Para Dirección |
| Reportes | Exportar | 👁️ Ver | CSV/PDF/Excel |
| Schedule | Ver Schedule global | 👁️ Ver | Cualquier hotel |
| Notificaciones | Recibir notificación | 👁️ Ver | Alertas críticas |
| Configuración | Ver catálogos | 👁️ Ver | Solo consulta |
| Configuración | Plantillas de reportes | 📝 Editar | Personalización |
