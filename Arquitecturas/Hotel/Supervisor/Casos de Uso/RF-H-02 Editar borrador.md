---
tags:
  - arquitectura
  - rol/supervisor-hotel
  - caso-de-uso
aliases:
  - CU RF-H-02
---

# 🪪 ID: RF-H-02
🏷️ **Nombre:** Editar borrador de requisición

**Historia:**
Antes de enviar una requisición a autorización, el Supervisor puede editarla libremente para agregar/quitar posiciones, ajustar horarios, cambiar modalidades o complementar las notas. También puede editar requisiciones **rechazadas** por el Manager de Área (que volvieron a estado Verde manzana — En elaboración con observaciones), corrigiendo lo que el Manager señaló.

**Criterios de aceptación:**
Solo el Supervisor que creó la requisición puede editarla en estado borrador o rechazada. Los cambios persisten en menos de 2s. El estado se mantiene tras la edición. Las observaciones del Manager de Área (en caso de rechazo) son visibles durante la edición para guiar la corrección. Si la requisición pasa a Autorizada o cualquier otro estado posterior, ya no es editable por el Supervisor.

**Documentación:**
- PRD: PRD-HOTEL-02 Supervisor
- Flow: Edición de requisición
- Prototipo: (link de Figma)

**Flujo:**
`Mis Requisiciones → Borradores o Rechazadas` → MANUAL → `Click en requisición` → `Click "Editar"` → `Modifica campos (posiciones / horarios / modalidad / notas)` → Si era rechazada → `Lee observaciones del Manager visible en el detalle` → MANUAL → `Guardar cambios` → AUTOMATICO → `Cambios persisten + Estado se mantiene` → MANUAL → `Reenviar a autorización` (dispara RF-H-03)
