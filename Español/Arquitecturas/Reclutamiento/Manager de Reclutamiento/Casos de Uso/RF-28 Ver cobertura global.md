---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - CU RF-28
---

# 🪪 ID: RF-28
🏷️ **Nombre:** Ver cobertura global

**Historia:**
El Manager consulta el indicador maestro del depto Reclutamiento: % cobertura total, requisiciones cubiertas / pendientes / parciales, ranking de Líderes por desempeño, alertas críticas (semáforos rojos, casos escalados). Es el dashboard de mando para tomar decisiones del depto y para su propio seguimiento y supervisión.

**Criterios de aceptación:**
Vista exclusiva del Manager. KPIs globales del mes en curso actualizados al cierre del día anterior. Permite drill-down por zona, Líder o Reclutadora. Alertas visibles para semáforos rojos y casos escalados pendientes. Comparativa contra mes anterior.

**Documentación:**
- PRD: PRD-RECL-03 Manager
- Flow: Cobertura global del depto
- Prototipo: (link de Figma)

**Flujo:**
`Dashboard Manager` → AUTOMATICO → `Sistema compila KPIs globales del mes en curso (cobertura total, req. cubiertas/pendientes/parciales, ranking Líderes, alertas)` → MANUAL → `Click en métrica para drill-down (zona / Líder / Reclutadora)` → `Acción: Ver detalle / Exportar / Generar reporte`
