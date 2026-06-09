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

| Módulo        | Funcionalidad                 | Permiso   | Descripción                                                              |
| ------------- | ----------------------------- | --------- | ------------------------------------------------------------------------ |
| Requisición   | Ver cola de Autorizadas       | 👁️ Ver   | Cola de requisiciones disponibles para tomar                             |
| Requisición   | Tomar / Unirme a requisición (Self-Pick colaborativo) | ➕ Crear   | Toma libremente la requisición; si ya hay otros, se une como reclutador participante adicional (RR-15) |
| Requisición   | Ver reclutadores activos      | 👁️ Ver   | Lista de los reclutadores participantes que trabajan la requisición      |
| Requisición   | Ver historial de la requisición | 👁️ Ver   | Timeline cronológico inmutable con actor (RR-16)                         |
| Requisición   | Salir de la requisición       | 📝 Editar | Se retira solo a sí misma; vuelve a Autorizada solo cuando sale el último reclutador |
| Requisición   | Marcar como en proceso        | 📝 Editar | Cambia estado a "en proceso"                                             |
| Requisición   | Marcar como cubierta          | 📝 Editar | Solicita cierre al **Líder de Grupo** cuando posiciones al 100%          |
| Reclutamiento | Buscar candidatos en Pool     | 👁️ Ver   | Filtros por posición, zona, modalidad, inglés                            |
| Reclutamiento | Crear colaborador (Fase 1)    | ➕ Crear   | Alta tras entrevista inicial                                             |
| Reclutamiento | Editar datos colaborador      | 📝 Editar | Captura datos básicos                                                    |
| Reclutamiento | Validar alta en app (Fase 2)  | 📝 Editar | Aprueba colaborador tras auto-alta                                       |
| Reclutamiento | Habilitar accesos             | ➕ Crear   | Activa paneles del colaborador                                           |
| Reclutamiento | Registrar entrevista          | ➕ Crear   | Documenta resultado                                                      |
| Reclutamiento | Asignar colaborador a hotel   | ➕ Crear   | Cubre la requisición                                                     |
| Reclutamiento | Asignar al Schedule           | ➕ Crear   | Genera entrada en Schedule semanal del hotel                             |
| Reclutamiento | Reasignar colaborador         | 📝 Editar | Rotación entre hoteles                                                   |
| Reclutamiento | Desasignar colaborador        | 📝 Editar | Retiro por fin/problema                                                  |
| Blacklist     | Consultar Blacklist           | 👁️ Ver   | Consulta obligatoria antes de asignar                                    |
| Blacklist     | Agregar a Blacklist           | ➕ Crear   | Cualquier rol del depto puede enviar al Blacklist con motivo y evidencia |
| Reportes      | Ver cobertura individual      | 👁️ Ver   | KPIs propios                                                             |
| Dashboard     | Ver KPIs personales           | 👁️ Ver   | Vista del Dashboard                                                      |
| Sistema       | Recibir notificación          | 👁️ Ver   | Alertas automáticas                                                      |
