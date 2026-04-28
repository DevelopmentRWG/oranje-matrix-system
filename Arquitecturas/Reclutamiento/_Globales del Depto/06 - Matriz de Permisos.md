---
tags:
  - arquitectura
  - departamento/reclutamiento
aliases:
  - Matriz de Permisos Reclutamiento
---

# MATRIZ DE PERMISOS — DEPARTAMENTO DE RECLUTAMIENTO

**PRD-RECL-01 · Sistema de Gestión de Personal**

---

| Módulo | Funcionalidad / Acción | ROL-01 Reclutadora | ROL-02 Líder de Grupo | ROL-03 Manager | ROL-04 Sistema | ROL-05 Admin | Notas / Condiciones |
|---|---|---|---|---|---|---|---|
| **BANDEJA DE RECLUTAMIENTO** | 👁️ Ver bandeja de Autorizadas | Ver | Ver | Ver | Auto | CRUD | Todos pueden ver. |
| | 🎯 Tomar requisición (Self-Pick) | Crear | Crear | Crear | Auto | CRUD | Modelo Self-Pick aprobado. |
| | 📝 Liberar requisición tomada | C · E | C · E | C · E | Auto | CRUD | Devuelve a Autorizadas. |
| | 📝 Marcar requisición en proceso | C · E | C · E | — | Auto | CRUD | Trigger automático al tomar. |
| | ✅ Marcar requisición como cubierta | C · E | C · E | Aprobar | Auto | CRUD | Manager valida cierre. |
| | 👁️ Ver vista global de requisiciones | — | Ver | Ver | Auto | CRUD | Manager ve todas. |
| | ⚠️ Asignar manualmente (excepción) | — | — | C · E | — | CRUD | Solo casos especiales con justificación. |
| **POOL DE COLABORADORES** | 👁️ Ver Pool | Ver | Ver | Ver | Auto | CRUD | Consulta para encontrar match. |
| | 🔍 Buscar / filtrar candidatos | Ver | Ver | Ver | Auto | CRUD | Filtros por posición, zona, modalidad, inglés. |
| | ➕ Crear colaborador (alta Fase 1) | Crear | Crear | — | — | CRUD | Reclutadora registra tras entrevista. |
| | 📝 Editar colaborador | C · E | C · E | C · E | — | CRUD | Reclutadora captura datos básicos. |
| | 📝 Validar alta en app (Fase 2) | C · E | C · E | — | Auto | CRUD | Solo Reclutador valida. |
| | ➕ Habilitar accesos | Crear | Crear | — | Auto | CRUD | Sistema propaga accesos. |
| **ENTREVISTAS** | ➕ Registrar entrevista | Crear | Crear | — | Auto | CRUD | Documenta resultado. |
| | 👁️ Ver historial de entrevistas | Ver | Ver | Ver | Auto | CRUD | Trazabilidad. |
| **BLACKLIST** | 👁️ Consultar Blacklist | Ver | Ver | Ver | Auto | CRUD | Consulta obligatoria antes de asignar. |
| | ➕ Agregar a Blacklist | — | — | Crear | — | CRUD | Solo Manager veta. |
| | 🔍 Investigar disputa | — | — | Investigar | — | CRUD | Manager decide. |
| | 📝 Remover de Blacklist | — | — | C · E | — | CRUD | Con justificación obligatoria. |
| **ASIGNACIÓN** | ➕ Asignar colaborador a hotel | Crear | Crear | Aprobar | Auto | CRUD | Reclutador asigna. |
| | ➕ Asignar al Schedule | Crear | Crear | C · E | Auto | CRUD | Genera entrada automática. |
| | 📝 Reasignar colaborador | C · E | C · E | Aprobar | — | CRUD | Rotación entre hoteles. |
| | 📝 Desasignar colaborador | C · E | C · E | Aprobar | — | CRUD | Cierre o problema operativo. |
| **SEMÁFOROS** | 👁️ Ver semáforos | Ver | Ver | Ver | Auto | CRUD | Monitoreo. |
| | 📝 Forzar cambio de semáforo | — | — | C · E | Auto | CRUD | Excepcional, con justificación. |
| **MI GRUPO** *(Líder)* | 👁️ Ver Reclutadoras del grupo | — | Ver | — | — | CRUD | Exclusivo del Líder. |
| | 👁️ Métricas individuales | — | Ver | Ver | Auto | CRUD | Líder y Manager. |
| **MI EQUIPO** *(Manager)* | 👁️ Ver Líderes + Reclutadoras | — | — | Ver | — | CRUD | Vista anidada. |
| | ➕ Dar de alta Líder/Reclutadora | — | — | Crear | — | CRUD | Solo Manager. |
| | 📝 Editar usuario del depto | — | — | C · E | — | CRUD | Solo Manager. |
| | 📝 Mover Reclutadora a otro Líder | — | — | C · E | — | CRUD | Reasignación organizacional. |
| **INCIDENCIAS** | ✓ Resolver incidencia | — | — | Aprobar | — | CRUD | Decisión final del Manager. |
| | 🚨 Escalar a comercial | — | C · E | C · E | — | CRUD | A BD/BDC. |
| **REPORTES** | ➕ Generar reporte del grupo | — | Crear | Crear | Auto | CRUD | Líder y Manager. |
| | ✅ Enviar reporte al Manager | — | Aprobar | — | — | CRUD | Solo Líder envía. |
| | 👁️ Ver cobertura individual | Ver | Ver | Ver | Auto | CRUD | KPIs propios. |
| | 👁️ Ver cobertura por zona | — | Ver | Ver | Auto | CRUD | Líder/Manager. |
| | 👁️ Ver cobertura global | — | — | Ver | Auto | CRUD | Solo Manager y Admin. |
| **NOTIFICACIONES** | 👁️ Recibir notificación | Ver | Ver | Ver | Auto | CRUD | Automática según rol. |
| | ⚙️ Enviar notificación | — | — | — | Auto | CRUD | Solo el sistema. |
| | ⚙️ Configurar alertas | — | — | — | — | CRUD | Solo Admin. |
| **USUARIOS** | ➕ Crear usuario | — | — | — | — | CRUD | Solo Admin. |
| | 📝 Editar usuario | — | — | — | — | CRUD | Solo Admin. |
| | 📝 Eliminar usuario | — | — | — | — | CRUD | Eliminación lógica. |
| | 👁️ Ver listado de usuarios | — | — | — | Auto | CRUD | Solo Admin. |
| **CATÁLOGOS** | 👁️ Ver catálogos | Ver | Ver | Ver | Auto | CRUD | Todos consultan. |
| | 📝 Editar catálogos | — | — | — | — | CRUD | Solo Admin. |
| **SCHEDULE** *(consulta)* | 👁️ Ver Schedule del hotel | Ver | Ver | Ver | Auto | CRUD | Consulta para asignar. |
