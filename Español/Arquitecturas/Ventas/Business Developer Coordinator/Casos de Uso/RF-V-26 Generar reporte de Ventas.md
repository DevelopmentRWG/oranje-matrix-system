---
tags:
  - arquitectura
  - rol/bdc
  - caso-de-uso
aliases:
  - CU RF-V-26
---

# 🪪 ID: RF-V-26
🏷️ **Nombre:** Generar reporte de Ventas

**Historia:**
El BDC genera reportes consolidados del territorio para uso interno y para enviar a dirección. Las plantillas disponibles son: Pipeline del territorio, Conversión por BD/zona/mes, Casos Café desbloqueados, Clientes Negro, Indicador de Calidad y Reporte Ejecutivo. Cada reporte se puede comparar contra el periodo anterior.

**Criterios de aceptación:**
Acción exclusiva del BDC. Vista previa antes de exportar / enviar. Soporta exportación CSV / PDF / Excel. Filtros por rango de fechas, BDs, rutas y zonas. Comparativa contra periodo anterior opcional. Queda en histórico de reportes generados.

**Documentación:**
- PRD: PRD-VENTAS-03 BDC
- Flow: Generar reporte de Ventas
- Prototipo: (link de Figma)

**Flujo:**
`Sidebar → Reportes → Click "Nuevo reporte"` → MANUAL → `Selecciona tipo (Pipeline / Conversión / Desempeño / Café / Negro / Calidad / Ejecutivo)` → `Selecciona rango de fechas` → `BDs incluidos opcional (todos por defecto)` → `Rutas/Zonas opcional` → `Marca "Comparativa contra periodo anterior" opcional` → `Selecciona formato de salida (PDF / CSV / Excel)` → `Click "Generar"` → AUTOMATICO → `Sistema compila datos del periodo + Genera vista previa` → MANUAL → `Acción: Exportar / Enviar a dirección (RF-V-27) / Guardar como plantilla`
