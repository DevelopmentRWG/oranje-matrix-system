---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - CU RF-27
---

# 🪪 ID: RF-27
🏷️ **Nombre:** Ver cobertura por zona

**Historia:**
El Manager visualiza la cobertura agregada por zona (Centro, Sur, Este, Oeste, Noroeste, Sureste) para detectar desbalances geográficos: zonas con baja cobertura, zonas saturadas, zonas con tiempos de cobertura altos. Permite tomar decisiones de balanceo entre Líderes y Reclutadoras.

**Criterios de aceptación:**
Vista por zona con: requisiciones totales, cubiertas, parciales, pendientes, % cobertura, tiempo promedio. Filtros por rango de fechas y posición. Visualización en mapa o tabla. Drill-down hasta el nivel de hotel/requisición.

**Documentación:**
- PRD: PRD-RECL-03 Manager
- Flow: Cobertura por zona
- Prototipo: (link de Figma)

**Flujo:**
`Dashboard global` → MANUAL → `Filtro: Por zona` → AUTOMATICO → `Sistema agrupa requisiciones por zona + Calcula KPIs` → MANUAL → `Vista mapa o tabla` → `Click en zona para drill-down (hotel / requisición / Reclutadora)`
