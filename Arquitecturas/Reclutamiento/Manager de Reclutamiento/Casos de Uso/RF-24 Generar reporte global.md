---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - CU RF-24
---

# 🪪 ID: RF-24
🏷️ **Nombre:** Generar reporte global

**Historia:**
El Manager genera reportes consolidados del depto Reclutamiento para Dirección u otras áreas. Incluye cobertura global, desempeño por Líder, casos escalados, distribución por zona y tendencias del periodo. El reporte puede exportarse o programarse para envío recurrente (semanal/mensual).

**Criterios de aceptación:**
El reporte se genera con datos actualizados al cierre del día anterior. Incluye filtros por rango de fechas, zona, posición y hotel. Soporta exportación CSV / PDF / Excel. Permite programar envío recurrente con destinatarios configurables. Queda histórico de reportes enviados.

**Documentación:**
- PRD: PRD-RECL-03 Manager
- Flow: Generar reporte global
- Prototipo: (link de Figma)

**Flujo:**
`Módulo Reportes` → MANUAL → `Click "Nuevo reporte"` → `Tipo: Global` → `Selecciona rango de fechas + filtros (zona / posición / hotel)` → AUTOMATICO → `Sistema compila datos del periodo` → MANUAL → `Vista previa del reporte` → `Acción: Exportar (CSV/PDF/Excel) / Enviar a Dirección / Programar envío recurrente`
