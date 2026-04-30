---
tags:
  - arquitectura
  - departamento/reclutamiento
aliases:
  - Matriz de Permisos Reclutamiento
---

# MATRIZ DE PERMISOS — DEPARTAMENTO DE RECLUTAMIENTO

**PRD-RECL-01 · Sistema de Gestión de Personal**

> [!info]
> El rol **Administrador (ROL-05)** se encuentra **en pausa** mientras se estabilizan las reglas de negocio. Los permisos del Admin se completarán al final.

---

| Módulo | Funcionalidad / Acción | ROL-01 Reclutadora | ROL-02 Líder de Grupo | ROL-03 Manager | ROL-04 Sistema | ROL-05 Admin |
|---|---|---|---|---|---|---|
| **REQUISICIÓN** | 👁️ Ver cola de Autorizadas | Ver | Ver | Ver | Auto | ⏸️ |
| | 🎯 Tomar requisición (Self-Pick) | Crear | Crear | Crear | Auto | ⏸️ |
| | 📝 Liberar requisición tomada | C · E | C · E | C · E | Auto | ⏸️ |
| | 📝 Marcar requisición en proceso | C · E | C · E | — | Auto | ⏸️ |
| | ✅ Marcar requisición como cubierta | C · E | C · E | C · E | Auto | ⏸️ |
| | 👁️ Ver vista global | — | Ver | Ver | Auto | ⏸️ |
| | ⚠️ Asignar manualmente (excepción) | — | — | C · E | — | ⏸️ |
| | 🚦 Calcular Semáforo de Urgencia | — | — | — | Auto | ⏸️ |
| | 🚦 Calcular Semáforo de Posiciones | — | — | — | Auto | ⏸️ |
| | 📝 Forzar cambio de semáforo | — | — | C · E | Auto | ⏸️ |
| **RECLUTAMIENTO** | 👁️ Ver Pool de Colaboradores | Ver | Ver | Ver | Auto | ⏸️ |
| | 🔍 Buscar / filtrar candidatos | Ver | Ver | Ver | Auto | ⏸️ |
| | ➕ Crear colaborador (alta Fase 1) | Crear | Crear | Crear | — | ⏸️ |
| | 📝 Editar colaborador | C · E | C · E | C · E | — | ⏸️ |
| | 📝 Validar alta en app (Fase 2) | C · E | C · E | — | Auto | ⏸️ |
| | ➕ Habilitar accesos | Crear | Crear | — | Auto | ⏸️ |
| | ➕ Registrar entrevista | Crear | Crear | — | Auto | ⏸️ |
| | 👁️ Ver historial de entrevistas | Ver | Ver | Ver | Auto | ⏸️ |
| | ➕ Asignar colaborador a hotel | Crear | Crear | C · E | Auto | ⏸️ |
| | ➕ Asignar al Schedule | Crear | Crear | C · E | Auto | ⏸️ |
| | 📝 Reasignar colaborador | C · E | C · E | C · E | — | ⏸️ |
| | 📝 Desasignar colaborador | C · E | C · E | C · E | — | ⏸️ |
| **BLACKLIST** | 👁️ Consultar Blacklist | Ver | Ver | Ver | Auto | ⏸️ |
| | ➕ Agregar a Blacklist | Crear | Crear | Crear | — | ⏸️ |
| | 🔍 Resolver disputa | — | — | Investigar | — | ⏸️ |
| | 📝 Remover de Blacklist | — | — | C · E | — | ⏸️ |
| **MI GRUPO** *(Líder)* | 👁️ Ver Reclutadoras del grupo | — | Ver | — | — | ⏸️ |
| | 👁️ Ver métricas individuales | — | Ver | Ver | Auto | ⏸️ |
| | 📝 Comunicar con Reclutadora | — | C · E | C · E | — | ⏸️ |
| **MI EQUIPO** *(Manager)* | 👁️ Ver Líderes + Reclutadoras | — | — | Ver | — | ⏸️ |
| | ➕ Dar de alta Líder/Reclutadora | — | — | Crear | — | ⏸️ |
| | 📝 Editar usuario del depto | — | — | C · E | — | ⏸️ |
| | 📝 Mover Reclutadora a otro Líder | — | — | C · E | — | ⏸️ |
| **INCIDENCIAS** *(Manager)* | ✓ Resolver incidencia | — | — | Aprobar | — | ⏸️ |
| | 🚨 Escalar a comercial | — | C · E | C · E | — | ⏸️ |
| **REPORTES** | ➕ Generar reporte del grupo | — | Crear | Crear | Auto | ⏸️ |
| | ✅ Enviar reporte al Manager | — | Aprobar | — | — | ⏸️ |
| | 👁️ Ver cobertura individual | Ver | Ver | Ver | Auto | ⏸️ |
| | 👁️ Ver cobertura por zona | — | Ver | Ver | Auto | ⏸️ |
| | 👁️ Ver cobertura global | — | — | Ver | Auto | ⏸️ |
| **DASHBOARD** | 👁️ Ver KPIs personales | Ver | Ver | Ver | Auto | ⏸️ |
| | 👁️ Ver KPIs de grupo | — | Ver | Ver | Auto | ⏸️ |
| | 👁️ Ver KPIs globales | — | — | Ver | Auto | ⏸️ |
| **SISTEMA** *(transversal)* | 👁️ Recibir notificación | Ver | Ver | Ver | Auto | ⏸️ |
| | ⚙️ Enviar notificación automática | — | — | — | Auto | ⏸️ |
| **CONFIGURACIÓN** *(Admin EN PAUSA)* | ⏸️ Configurar alertas | — | — | — | — | ⏸️ Por confirmar |
| | ⏸️ CRUD de usuarios | — | — | — | — | ⏸️ Por confirmar |
| | ⏸️ Editar catálogos | — | — | — | — | ⏸️ Por confirmar |

---

## Cambios respecto a la versión anterior

- **Blacklist** — La columna `Agregar a Blacklist` ahora es `Crear` para los 3 roles del depto (Reclutadora, Líder, Manager). Antes solo el Manager podía. La regla actualizada (RR-03) deja al Manager como único que **resuelve disputas** y **remueve**.
- **Submódulos reorganizados** — Pool, Entrevistas y Asignación quedan dentro del módulo **RECLUTAMIENTO**. La toma de requisición y los semáforos quedan dentro del módulo **REQUISICIÓN**.
- **Notificaciones** ya no es módulo del sidebar — pasó a sección "Sistema (transversal)".
- **Schedule** ya no es módulo aparte — es vista contextual dentro del proceso de asignar.
- **Admin en pausa** — todas las celdas del ROL-05 marcadas con ⏸️.
