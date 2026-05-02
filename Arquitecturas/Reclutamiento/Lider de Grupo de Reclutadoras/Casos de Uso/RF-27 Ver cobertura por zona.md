---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-27 (Líder)
---

# 🪪 ID: RF-27
🏷️ **Nombre:** Ver cobertura por zona

**Historia:**
El Líder visualiza la cobertura agregada por las zonas donde operan sus Reclutadoras (Centro, Sur, Este, Oeste, Noroeste, Sureste, según corresponda). Le permite identificar zonas con baja cobertura dentro de su grupo, balancear cargas entre Reclutadoras o priorizar requisiciones críticas por zona. A diferencia del Manager —que ve todas las zonas del depto— el Líder solo ve las zonas asignadas a su grupo.

**Criterios de aceptación:**
Alcance limitado a las zonas donde están asignadas las Reclutadoras del grupo. KPIs por zona: requisiciones totales, cubiertas, parciales, pendientes, % cobertura, tiempo promedio. Filtros por rango de fechas y posición. Visualización en mapa o tabla. Drill-down hasta el nivel de hotel / requisición.

**Documentación:**
- PRD: PRD-RECL-02 Líder de Grupo
- Flow: Cobertura por zona (alcance grupo)
- Prototipo: (link de Figma)

**Flujo:**
`Dashboard del grupo` → MANUAL → `Filtro: Por zona` → AUTOMATICO → `Sistema agrupa requisiciones por zona del grupo del Líder + Calcula KPIs` → MANUAL → `Vista mapa o tabla` → `Click en zona para drill-down (hotel / requisición / Reclutadora)`
