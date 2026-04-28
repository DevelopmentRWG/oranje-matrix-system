---
tags:
  - arquitectura
  - rol/reclutadora
aliases:
  - Permisos Detallados Reclutadora
---

# PERMISOS DETALLADOS POR ROL

## ROL-01 · 👤 Reclutadora

---

| Módulo | Funcionalidad | Permiso | Descripción |
|---|---|---|---|
| Bandeja | Ver bandeja de Autorizadas | 👁️ Ver | Cola de requisiciones disponibles para tomar |
| Bandeja | Tomar requisición (Self-Pick) | ➕ Crear | Toma libremente la requisición a trabajar |
| Bandeja | Liberar requisición | 📝 Editar | Devuelve la requisición a la bandeja si no puede cubrirla |
| Bandeja | Marcar como en proceso | 📝 Editar | Cambia estado a "en proceso" |
| Bandeja | Marcar como cubierta | 📝 Editar | Solicita cierre al Manager (cuando 100%) |
| Pool | Buscar candidatos | 👁️ Ver | Filtros por posición, zona, modalidad, inglés |
| Pool | Crear colaborador | ➕ Crear | Alta tras entrevista (Fase 1) |
| Pool | Editar datos colaborador | 📝 Editar | Captura datos básicos |
| Pool | Validar alta en app | 📝 Editar | Aprueba colaborador tras auto-alta (Fase 2) |
| Pool | Habilitar accesos | ➕ Crear | Activa paneles del colaborador |
| Entrevistas | Registrar entrevista | ➕ Crear | Documenta resultado |
| Blacklist | Consultar Blacklist | 👁️ Ver | Revisa antes de asignar |
| Asignación | Asignar a hotel | ➕ Crear | Cubre la requisición |
| Asignación | Asignar al Schedule | ➕ Crear | Genera entrada en Schedule semanal |
| Asignación | Reasignar colaborador | 📝 Editar | Rotación entre hoteles |
| Asignación | Desasignar colaborador | 📝 Editar | Retiro por fin/problema |
| Schedule | Ver Schedule del hotel | 👁️ Ver | Consulta para entender la semana |
| Reportes | Ver cobertura individual | 👁️ Ver | KPIs propios |
| Notificaciones | Recibir notificación | 👁️ Ver | Alertas automáticas |
