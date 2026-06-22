---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - CU RF-18
---

# 🪪 ID: RF-18
🏷️ **Nombre:** Solicitar desasignación de colaborador

**Historia:**
Cuando un colaborador termina su asignación (fin de contrato, problema operativo, solicitud del hotel), la Reclutadora lo desasigna del hotel. La posición queda liberada en la requisición y el colaborador vuelve a Verde fuerte (Disponible) en el Pool.

**Criterios de aceptación:**
La desasignación libera la posición; notifica al hotel. El colaborador vuelve a Disponible (Verde fuerte) en el Pool. Si era una requisición cubierta al 100%, la cobertura baja.

**Documentación:**
- PRD: PRD-RECL-02 Reclutadora
- Flow: Desasignación
- Prototipo: (link de Figma)

**Flujo:**
`Asignación activa` → MANUAL → `Click "Desasignar"` → `Seleccionar motivo` → `Confirmar` → AUTOMATICO → `Libera posición en requisición + Notifica al hotel + Colaborador vuelve a Verde fuerte + Actualiza Schedule`
