---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-22
---

# 🪪 ID: RF-22
🏷️ **Nombre:** Ver Reclutadoras del grupo

**Historia:**
El Líder consulta el módulo "Mi Grupo" para ver todas las Reclutadoras a su cargo en una vista única, con sus métricas operativas (n° de requisiciones activas, % cobertura del mes, casos escalados, estado actual). Es el punto de entrada para cualquier acción de supervisión: detectar sobrecarga, identificar bajo desempeño o seleccionar a una Reclutadora para revisar en detalle.

**Criterios de aceptación:**
Vista exclusiva del Líder, mostrando solo a las Reclutadoras de su grupo. Lista con: nombre, zona, n° de requisiciones activas, % cobertura del mes, casos escalados pendientes, estado (activa / vacaciones / inactiva). Filtros por zona, estado y carga. Buscador por nombre. Click en una Reclutadora abre su ficha detallada (RF-23).

**Documentación:**
- PRD: PRD-RECL-02 Líder de Grupo
- Flow: Mi Grupo
- Prototipo: (link de Figma)

**Flujo:**
`Sidebar → Click "Mi Grupo"` → AUTOMATICO → `Sistema lista solo Reclutadoras del grupo del Líder con métricas agregadas` → MANUAL → `Aplica filtros (zona / estado / carga)` o `Click en Reclutadora` → `Abre ficha detallada con métricas individuales (RF-23)`
