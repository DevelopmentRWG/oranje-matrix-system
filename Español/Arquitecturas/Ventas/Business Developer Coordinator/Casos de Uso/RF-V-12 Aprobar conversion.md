---
tags:
  - arquitectura
  - rol/bdc
  - caso-de-uso
aliases:
  - CU RF-V-12
---

# 🪪 ID: RF-V-12
🏷️ **Nombre:** Aprobar conversión a cliente

**Historia:**
**El sí final.** Tras validar el T&C y crear el Usuario del Hotel, el BDC **aprueba la conversión** del prospecto a cliente activo. Esta acción es **exclusiva del BDC** (RR-V-01) y dispara el **Trigger Automático de Conversión** (RF-V-13) que ejecuta 3 acciones en paralelo: email de bienvenida al hotel, notificación al BD y remoción del Pipeline. El status pasa a Naranja y el hotel queda habilitado para generar requisiciones desde el módulo Hotel.

**Criterios de aceptación:**
Solo el BDC puede aprobar (RR-V-01). Precondición: Usuario del Hotel creado (RR-V-02). Precondición: T&C validado. Confirmación final obligatoria (checkbox). Trigger Automático ejecuta las 3 acciones en menos de 1 min (RR-V-03). Status pasa a Naranja automáticamente. El Contrato se genera con el T&C validado como insumo (RR-V-15). Queda en log auditable.

**Documentación:**
- PRD: PRD-VENTAS-03 BDC
- Flow: Aprobar conversión
- Prototipo: (link de Figma)

**Flujo:**
`Detalle de prospecto en Rosa con T&C validado y Usuario del Hotel creado → Sidebar Conversión` → MANUAL → `Click "Aprobar conversión"` → AUTOMATICO → `Sistema valida que existe Usuario del Hotel (RR-V-02)` → Si OK → MANUAL → `Notas para el cierre opcional` → `Marca confirmación final ("Confirmo que el hotel cumple los requisitos para activarse")` → `Confirmar` → AUTOMATICO → `Status pasa a Naranja + Trigger Automático ejecuta en paralelo las 3 acciones (email + notif al BD + sale de Pipeline) + Genera Contrato con T&C validado + Hotel queda activo + Log auditable + Notifica al BDC del éxito` / Si no hay Usuario del Hotel → `Bloquea con "Debe crear el Usuario del Hotel antes de aprobar la conversión"` / Si T&C no validado → `Bloquea con "El Documento de T&C debe estar validado"`

> [!important]
> Este es el momento exacto en que un prospecto pasa a ser **cliente activo de Oranje**. La operación post-Naranja (Reclutamiento, Schedule, Timesheet) se vuelve disponible para el hotel.
