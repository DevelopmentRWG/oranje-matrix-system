---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-24 (Líder)
---

# 🪪 ID: RF-24
🏷️ **Nombre:** Generar reporte del grupo

**Historia:**
El Líder genera reportes consolidados del desempeño de su grupo: cobertura agregada, desempeño por Reclutadora, casos escalados, tiempos promedio, distribución por zona. A diferencia del Manager —que genera reportes globales del depto— el Líder genera reportes con alcance del grupo. El reporte puede exportarse o enviarse formalmente al Manager (flujo RF-25).

**Criterios de aceptación:**
Alcance restringido al grupo del Líder. Tipos de reporte: Cobertura del grupo, Desempeño individual por Reclutadora, Casos escalados, Distribución por zona. Filtros por rango de fechas, zona y posición. Soporta exportación CSV / PDF. Vista previa antes de exportar / enviar. Histórico de reportes generados.

**Documentación:**
- PRD: PRD-RECL-02 Líder de Grupo
- Flow: Generar reporte del grupo
- Prototipo: (link de Figma)

**Flujo:**
`Módulo Reportes` → MANUAL → `Click "Nuevo reporte"` → `Tipo: Grupo` → `Selecciona subtipo (Cobertura / Desempeño individual / Casos escalados / Por zona) + rango de fechas + filtros` → AUTOMATICO → `Sistema compila datos del grupo del Líder` → MANUAL → `Vista previa` → `Acción: Exportar (CSV/PDF) / Guardar borrador / Enviar al Manager (dispara RF-25)`
