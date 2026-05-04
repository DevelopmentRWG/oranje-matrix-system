---
tags:
  - arquitectura
  - rol/manager-general
  - caso-de-uso
aliases:
  - CU RF-H-24
---

# 🪪 ID: RF-H-24
🏷️ **Nombre:** Generar reporte ejecutivo

**Historia:**
El Manager General genera reportes consolidados del hotel para uso interno y para enviar a dirección. Las plantillas disponibles son: Cobertura, Desempeño por Gerente, Cumplimiento del Timesheet, Calidad (QA), Accidentes Laborales e Indicadores Ejecutivos. Cada reporte se puede comparar contra el periodo anterior.

**Criterios de aceptación:**
Acción exclusiva del Manager General. Vista previa antes de exportar / enviar. Soporta exportación en CSV / PDF / Excel. Filtros por rango de fechas, departamentos y filtros adicionales (posición, hotel, Gerente). Comparativa contra periodo anterior opcional. Queda en histórico de reportes generados.

**Documentación:**
- PRD: PRD-HOTEL-04 Manager General
- Flow: Generar reporte ejecutivo
- Prototipo: (link de Figma)

**Flujo:**
`Sidebar → Reportes → Click "Nuevo reporte"` → MANUAL → `Selecciona tipo (Cobertura / Desempeño / Cumplimiento / Calidad / Accidentes / Indicadores)` → `Selecciona rango de fechas` → `Selecciona deptos (opcional — todos por defecto)` → `Filtros adicionales (opcional)` → `Marca "Comparativa contra periodo anterior" (opcional)` → `Selecciona formato de salida (PDF / CSV / Excel)` → `Click "Generar"` → AUTOMATICO → `Sistema compila datos del periodo + Genera vista previa` → MANUAL → `Acción: Exportar / Enviar a dirección (RF-H-25) / Guardar como plantilla`
