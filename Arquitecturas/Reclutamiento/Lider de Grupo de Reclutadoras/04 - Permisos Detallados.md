---
tags:
  - arquitectura
  - rol/lider-de-grupo
aliases:
  - Permisos Detallados Líder de Grupo
---

# PERMISOS DETALLADOS POR ROL

## ROL-02 · 🧑‍🏫 Líder de Grupo de Reclutadoras

---

| Módulo        | Funcionalidad                   | Permiso   | Descripción                                                |
| ------------- | ------------------------------- | --------- | ---------------------------------------------------------- |
| Requisición   | Ver cola de Autorizadas         | 👁️ Ver   | Cola de requisiciones disponibles                          |
| Requisición   | Tomar requisición (Self-Pick colaborativo) | ➕ Crear | Toma libremente igual que Reclutadora; no bloquea a otros (RR-15) |
| Requisición   | Unirse a requisición (RF-39)    | ➕ Crear   | Se une como reclutador participante a una ya tomada (RR-15) |
| Requisición   | Ver reclutadores activos (RF-40)| 👁️ Ver   | Lista de reclutadores participantes que la trabajan ahora  |
| Requisición   | Ver historial de la requisición (RF-41) | 👁️ Ver | Timeline inmutable con actor de cada evento (RR-16)      |
| Requisición   | Salir de la requisición (RF-03) | 📝 Editar | Te retira solo a ti; sigue activa si quedan otros reclutadores |
| Requisición   | Marcar como en proceso          | 📝 Editar | Cambia estado a "en proceso"                               |
| Requisición   | Marcar como cubierta            | 📝 Editar | Cuando él/ella tomó la requisición y posiciones al 100%    |
| Requisición   | **Aprobar cierre de cobertura** | ✓ Aprobar | **Aprueba cierres marcados por sus Reclutadoras** (semáforo Azul claro) |
| Reclutamiento | Buscar candidatos en Pool       | 👁️ Ver   | Filtros por posición, zona, modalidad, inglés              |
| Reclutamiento | Crear colaborador (Fase 1)      | ➕ Crear   | Alta tras entrevista                                       |
| Reclutamiento | Editar colaborador              | 📝 Editar | Captura datos básicos                                      |
| Reclutamiento | Validar alta en App (Fase 2)    | 📝 Editar | Aprueba colaborador                                        |
| Reclutamiento | Habilitar accesos               | ➕ Crear   | Activa paneles del colaborador                             |
| Reclutamiento | Registrar entrevista            | ➕ Crear   | Documenta resultado                                        |
| Reclutamiento | Asignar colaborador a hotel     | ➕ Crear   | Cubre la requisición                                       |
| Reclutamiento | Asignar al Schedule             | ➕ Crear   | Genera entrada en Schedule semanal del hotel               |
| Reclutamiento | Reasignar colaborador           | 📝 Editar | Rotación entre hoteles                                     |
| Reclutamiento | Desasignar colaborador          | 📝 Editar | Retiro por fin/problema                                    |
| Blacklist     | Consultar Blacklist             | 👁️ Ver   | Consulta obligatoria antes de asignar                      |
| Blacklist     | Agregar a Blacklist             | ➕ Crear   | Cualquier rol del depto puede vetar con motivo y evidencia |
| **Mi Grupo**  | Ver Reclutadoras del grupo      | 👁️ Ver   | Lista con métricas                                         |
| **Mi Grupo**  | Ver métricas individuales       | 👁️ Ver   | Detalle de desempeño por Reclutadora                       |
| **Mi Grupo**  | Ver carga detallada (RF-36)     | 👁️ Ver   | Requisiciones en proceso de la Reclutadora                 |
| **Mi Grupo**  | Reasignar requisición (RF-37)   | 📝 Editar | Pasa una requisición a otra Reclutadora del grupo          |
| **Mi Grupo**  | Marcar disponibilidad (RF-38)   | 📝 Editar | Toggle Activa ↔ Vacaciones de la Reclutadora               |
| **Reportes**  | Generar reporte del grupo       | ➕ Crear   | Cobertura, desempeño, casos escalados                      |
| **Reportes**  | Enviar reporte al Manager       | ✓ Aprobar | Envío formal con notificación                              |
| **Reportes**  | Exportar reporte                | 👁️ Ver   | CSV / PDF                                                  |
| Reportes      | Ver cobertura individual        | 👁️ Ver   | KPIs propios                                               |
| Reportes      | Ver cobertura del grupo         | 👁️ Ver   | KPIs del grupo                                             |
| Reportes      | Ver cobertura por zona          | 👁️ Ver   | Filtros por zona                                           |
| Dashboard     | Ver KPIs personales y del grupo | 👁️ Ver   | Vista del Dashboard                                        |
| Sistema       | Recibir notificación            | 👁️ Ver   | Alertas automáticas                                        |
