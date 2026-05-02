---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - CU RF-23
---

# 🪪 ID: RF-23
🏷️ **Nombre:** Métricas individuales por Reclutadora

**Historia:**
El Manager consulta el desempeño individual de cualquier Reclutadora del depto (sin importar a qué Líder pertenezca). A diferencia del Líder de Grupo —que solo ve a sus Reclutadoras— el Manager tiene visibilidad total para detectar bajo desempeño, balancear cargas o tomar decisiones de gestión.

**Criterios de aceptación:**
Acceso global a métricas de cualquier Reclutadora del depto. Métricas mínimas: cobertura del mes, tiempo promedio de asignación, casos escalados, requisiciones cubiertas vs parciales. Filtros por rango de fechas y zona. Métricas actualizadas diariamente.

**Documentación:**
- PRD: PRD-RECL-03 Manager
- Flow: Métricas individuales (vista global)
- Prototipo: (link de Figma)

**Flujo:**
`Módulo Mi Equipo` → MANUAL → `Selecciona Líder de Grupo` → `Selecciona Reclutadora` → AUTOMATICO → `Sistema compila métricas individuales (cobertura, tiempo promedio, casos)` → MANUAL → `Aplica filtros (rango fechas / zona)` → `Exporta o envía al Líder`
