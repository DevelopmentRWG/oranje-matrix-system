---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - CU RF-41
---

# 🪪 ID: RF-41
🏷️ **Nombre:** Ver Historial de la requisición

**Historia:**
La Reclutadora abre el detalle de una requisición y consulta su **Historial**: un timeline cronológico **inmutable** que registra cada evento con su **actor** (rol + nombre) y timestamp. El Historial muestra quién la tomó / se unió, quién salió, quién asignó/desasignó qué colaborador a qué posición y quién la cerró. En el modelo colaborativo (RR-15) varios reclutadores participantes trabajan la misma requisición a la vez, por lo que el Historial es la fuente de trazabilidad compartida (RR-16). Es visible para todos los reclutadores participantes, el [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo]] y el [[Hotel/Manager de Área|Manager de Área]].

**Criterios de aceptación:**
El Historial muestra cronológicamente quién tomó/salió y quién asignó/desasignó cada colaborador, con fecha y autor (AC-24). El timeline es inmutable (no se puede editar ni borrar). Es visible para todos los reclutadores participantes, el Líder de Grupo y el Manager de Área.

**Documentación:**
- PRD: PRD-RECL-02 Reclutadora
- Flow: Ver historial de la requisición
- Prototipo: (link de Figma)

**Flujo:**
`Detalle de Requisición` → MANUAL → `Click en "Ver historial"` → AUTOMATICO → `Carga el timeline cronológico inmutable (RR-16)` → `Lista cada evento con actor (rol + nombre) y timestamp: tomó / se unió / salió / asignó / desasignó (colaborador → posición) / cerró`
