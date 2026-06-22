---
tags:
  - arquitectura
  - rol/manager-general
  - caso-de-uso
aliases:
  - CU RF-H-23
---

# 🪪 ID: RF-H-23
🏷️ **Nombre:** Ver Timesheet global del hotel

**Historia:**
El Manager General consulta el Timesheet **consolidado de todos los departamentos** del hotel. Visualiza el Indicador de Cumplimiento por colaborador y por depto, las horas brutas / netas y las deducciones. Detecta deptos con bajo cumplimiento y solicita reportes específicos al Gerente correspondiente.

**Criterios de aceptación:**
Vista exclusiva del Manager General (solo jerarquía extendida). Tabla consolidada del hotel con filtros por depto, colaborador, posición, semana. Indicador de Cumplimiento del Timesheet semaforizado (Verde / Amarillo / Rojo). Resumen por depto: horas pagables, brutas, deducciones. Drill-down a jornada individual. Sin acceso al Indicador de Lunch Extendido (RR-H-15).

**Documentación:**
- PRD: PRD-HOTEL-04 Manager General
- Flow: Timesheet Global del Hotel
- Prototipo: (link de Figma)

**Flujo:**
`Sidebar → Timesheet Global` → AUTOMATICO → `Sistema consolida Timesheet de todos los deptos + Calcula Indicador de Cumplimiento por colaborador y depto` → MANUAL → `Aplica filtros (depto / colaborador / posición / semana)` → `Click en colaborador para drill-down a jornadas` → `Acción: Exportar consolidado / Solicitar reporte al Gerente / Generar reporte ejecutivo`
