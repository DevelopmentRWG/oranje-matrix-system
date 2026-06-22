---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-38
---

# 🪪 ID: RF-38
🏷️ **Nombre:** Marcar disponibilidad de la Reclutadora

**Historia:**
El Líder marca a una Reclutadora de su grupo como **en vacaciones** (o de **vuelta / disponible**) desde su ficha de detalle. Mientras está en vacaciones, la Reclutadora **no recibe reasignaciones** y su estado se refleja en la lista del grupo y en los KPIs del Líder.

**Criterios de aceptación:**
Solo aplica a Reclutadoras del propio grupo (regla RR-10). Es un **toggle Activa ↔ Vacaciones**. El cambio se refleja en la **lista** (columna Estado) y en los **KPIs** del grupo (Reclutadoras activas / en vacaciones). Queda registrado en log.

> [!note]
> No equivale a una **baja** del sistema: el alta/edición/baja definitiva de usuarios del depto es exclusiva del Manager (RF-29). Esto solo marca disponibilidad operativa temporal.

**Documentación:**
- PRD: PRD-RECL-03 Líder de Grupo
- Flow: Disponibilidad de la Reclutadora
- Prototipo: (link de Figma)

**Flujo:**
`Mi Grupo → Click en Reclutadora` → MANUAL → `Click "Marcar vacaciones" / "Marcar disponible"` → AUTOMATICO → `Cambia el estado de la Reclutadora + Actualiza la lista y los KPIs del grupo + Registra en log`
