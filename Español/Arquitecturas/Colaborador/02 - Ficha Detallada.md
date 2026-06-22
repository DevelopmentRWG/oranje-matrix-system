---
tags:
  - arquitectura
  - rol/colaborador
aliases:
  - Ficha Detallada Colaborador
---

# FICHA DETALLADA — COLABORADOR

---

| Campo                          | Contenido                                                                                                                                                                                                                              |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **ID Rol**                     | ROL-C-01                                                                                                                                                                                                                               |
| **Nombre del Rol**             | 👷 Colaborador (COL)                                                                                                                                                                                                                   |
| **Descripción**                | Persona reclutada, asignada y gestionada operativamente en los hoteles. Sujeto pasivo del sistema: solo ejecuta autoservicio personal. No gestiona a nadie ni tiene acceso a datos de otros colaboradores.                             |
| **Objetivo en el Sistema**     | Completar su alta, registrar asistencia diaria, informar disponibilidad voluntaria, reportar accidentes y consultar sus propios datos operativos.                                                                                       |
| **Módulos que Usa**            | Dashboard · Mi Schedule · Asistencia (Ponche QR) · Mi Timesheet · Mi Pago · Disponibilidad · Reportar Accidente · Notificaciones · Mi Perfil                                                                                          |
| **Permisos (CRUD)**            | Ver (solo propio) · Crear (alta, ponches, reporte de accidente, activar Amarillo) · Editar limitado (datos propios de perfil/emergencia)                                                                                               |
| **Acciones Principales**       | Completar Fase 2 · Completar Fase 3 · Ponchar QR · Activar Amarillo · Reportar accidente · Consultar Schedule · Consultar Timesheet · Consultar Mi Pago · Ver notificaciones · Ver Mi Perfil                                          |
| **Nivel de Acceso**            | 🟢 Bajo (solo datos propios)                                                                                                                                                                                                           |
| **Dispositivo**                | Mobile + Web (responsive) — el ponche por QR (RF-C-03) es exclusivo de móvil; onboarding, vistas de consulta y disponibilidad disponibles en ambos canales                                                                             |
| **Frecuencia de Uso**          | Alta — diaria                                                                                                                                                                                                                          |
| **Dolor / Necesidad Actual**   | El colaborador no tiene visibilidad de su propio schedule ni de sus horas; no puede declarar disponibilidad sin intermediario; el reporte de accidente dependía exclusivamente del Supervisor. La app resuelve estas fricciones.        |
| **Notas UX / Recomendaciones** | App mobile-first con UX simplificada (el colaborador puede tener nivel básico de dominio tecnológico); ponche QR como acción principal en home; notificaciones push para cambios de estado; formularios breves con validación progresiva. |

---

## Responsabilidades

### Lo que SÍ hace el Colaborador

- **Completar su alta (Fase 2):** ingresa posición, nivel de inglés, nivel de experiencia, tipo de transporte y modalidad de contratación (obligatorios); SSN, ITIN y el documento de SSN/ITIN son opcionales. Si no proporciona ni SSN ni ITIN, el sistema activa automáticamente la retención del 16% sobre su pago (reembolsable) — ver [[Deducciones]].
- **Completar datos de emergencia (Fase 3):** ingresa contacto de emergencia (nombre, teléfono, parentesco), tipo de sangre y alergias/condiciones médicas.
- **Ponchar vía QR:** escanea el QR generado por el Manager de Área o Manager General y registra cada uno de los 6 ponches de la jornada (Entrada, Salida Lunch, Entrada Lunch, Salida Break, Entrada Break, Salida).
- **Activar Amarillo:** activa su disponibilidad voluntaria desde la app cuando está en periodo de descanso y desea ser considerado para asignación temporal. Esta es su única acción autónoma de cambio de estado.
- **Reportar accidente:** crea la tarjeta inicial de accidente laboral desde la app cuando es él quien detecta o sufre el accidente (Escenario A).
- **Consultar Mi Schedule:** visualiza sus turnos asignados de la semana en curso y la siguiente (solo lectura).
- **Consultar Mi Timesheet:** visualiza sus horas brutas, deducción de lunch, horas netas y estado de cumplimiento (solo lectura).
- **Consultar Mi Pago:** visualiza el resumen de su consolidado semanal (monto a cobrar, horas por hotel si aplica) (solo lectura).
- **Ver notificaciones:** recibe alertas del sistema sobre cambios de estado, asignaciones, validaciones de alta y resultados de reportes.
- **Ver Mi Perfil:** consulta su perfil completo, estado actual del semáforo y datos registrados.

### Lo que NO hace el Colaborador

- **NO acepta ni rechaza asignaciones** — la asignación la ejecuta la Reclutadora o el Líder de Grupo.
- **NO solicita reasignación** — si está en Rosa, puede activar Amarillo (si aplica), pero no pide ser reasignado directamente.
- **NO autoriza ninguna acción** de otro rol ni del sistema.
- **NO asigna a nadie ni gestiona a otros colaboradores.**
- **NO edita el Schedule** — es solo lectura para él.
- **NO corrige ponches** — la corrección es exclusiva del Manager de Área.
- **NO ve datos de otros colaboradores** — su visibilidad está restringida a sus propios registros (RR-C-01).
- **NO accede a módulos de gestión** (requisiciones, pool, contabilidad general, QA).
- **NO puede ponchar por web** — el ponche por QR (RF-C-03) requiere la cámara del teléfono y es exclusivo de móvil (RR-C-04).

---

## Interacciones con otros roles

Ver fuente: [[Colaborador#Roles que interactúan con el Colaborador]]

| Rol | Cómo interactúa con el Colaborador |
|---|---|
| [[Reclutadora]] | Lo recluta, captura Fase 1, valida Fase 2/3, lo asigna a un hotel; gestiona su estado en el Pool |
| [[Manager de Reclutamiento]] | Supervisa casos de Blacklist; no interviene en la operación diaria del Colaborador |
| [[Hotel/Manager de Área\|Manager de Área]] | Genera el QR de acceso, gestiona su Schedule, corrige ponches, lo puede poner en Rosa o Rojo |
| [[Hotel/Supervisor\|Supervisor]] | Puede reportar accidente Escenario B, puede poner en Rosa o Rojo |
| [[Hotel/Manager General\|Manager General]] | Genera QR, puede poner en Rosa o Rojo; visibilidad global del hotel |
| [[Inspector]] | Verifica llegada el Día 1, entrega uniforme en Día 3+, investiga casos Rojo, cierra tarjetas de accidente |
