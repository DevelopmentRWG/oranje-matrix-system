---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-23 (Líder)
---

# 🪪 ID: RF-23
🏷️ **Nombre:** Métricas individuales por Reclutadora

**Historia:**
El Líder consulta el detalle de desempeño de una Reclutadora específica de su grupo: cobertura del mes, tiempo promedio de asignación, casos escalados, requisiciones cubiertas vs parciales, tendencias respecto al mes anterior. A diferencia del Manager —que ve a cualquier Reclutadora del depto— el Líder solo accede a las que están en su grupo (regla RR-10 de jerarquía).

**Criterios de aceptación:**
Acceso restringido a Reclutadoras del propio grupo. Métricas mínimas: % cobertura, tiempo promedio de asignación, requisiciones cubiertas / parciales / pendientes, casos escalados, comparativa contra mes anterior. Filtros por rango de fechas y posición. Métricas actualizadas diariamente. Acción de "Comunicar con Reclutadora" disponible desde el detalle.

**Documentación:**
- PRD: PRD-RECL-02 Líder de Grupo
- Flow: Métricas individuales (alcance grupo)
- Prototipo: (link de Figma)

**Flujo:**
`Mi Grupo → Click en Reclutadora` → AUTOMATICO → `Sistema valida que pertenezca al grupo del Líder + Compila métricas individuales (cobertura, tiempo promedio, casos)` → MANUAL → `Aplica filtros (rango fechas / posición)` → `Acciones: Comunicar / Exportar métricas / Incluir en próximo reporte al Manager`
