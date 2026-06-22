---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-05 (Líder)
---

# 🪪 ID: RF-05
🏷️ **Nombre:** Aprobar cierre de cobertura del grupo

**Historia:**
Cuando una Reclutadora del grupo marca una requisición como cubierta (todas las posiciones al 100%), el sistema deja la requisición en estado **Pendiente de aprobación** y notifica al Líder. El Líder revisa que la cobertura sea real (verifica posiciones, colaboradores asignados, datos del Schedule) y aprueba o rechaza el cierre. Solo tras la aprobación del Líder, la requisición pasa a semáforo Azul claro (Cubierta y cerrada).

**Criterios de aceptación:**
La aprobación del cierre es exclusiva del Líder de Grupo (regla actualizada — el Manager NO aprueba). El Líder solo puede aprobar requisiciones tomadas por Reclutadoras de su grupo. La aprobación requiere comentario opcional. Si rechaza, la requisición vuelve a estado "En proceso" (Amarillo) con motivo. La aprobación / rechazo queda en log auditable. Notifica a la Reclutadora.

**Documentación:**
- PRD: PRD-RECL-02 Líder de Grupo
- Flow: Aprobación de cierre del grupo
- Prototipo: (link de Figma)

**Flujo:**
`Bandeja "Pendientes de aprobación"` → MANUAL → `Selecciona requisición marcada como cubierta` → `Verifica cobertura (posiciones / colaboradores asignados / Schedule)` → MANUAL → `Click "Aprobar cierre" o "Rechazar"` → Si Aprueba → `Comentario opcional` → AUTOMATICO → `Semáforo a Azul claro (Cubierta) + Notifica a Reclutadora + Log de cierre` / Si Rechaza → `Motivo obligatorio` → AUTOMATICO → `Vuelve a Amarillo (En proceso) + Notifica a Reclutadora + Log`
