---
tags:
  - arquitectura
  - rol/bdc
  - caso-de-uso
aliases:
  - CU RF-V-10
---

# 🪪 ID: RF-V-10
🏷️ **Nombre:** Validar Documento de T&C

**Historia:**
Cuando el BD termina de armar el Documento de Términos y Condiciones, lo envía al BDC para validación. El BDC revisa los 5 campos obligatorios (Pay rate, Bill rate, Overtime, Festivos, Calendario) y otras condiciones, y emite una decisión: **aprobar** (permite avanzar a Rosa) o **rechazar con observaciones** (vuelve al BD para corrección). La validación del T&C es **prerequisito** para la conversión final.

**Criterios de aceptación:**
Solo el BDC puede validar (acción exclusiva). Al aprobar, el T&C queda como "Validado" y el prospecto puede avanzar a Rosa. Al rechazar, las observaciones son obligatorias (mín. 30 caracteres) y el T&C vuelve a estado editable por el BD. Notifica al BD en menos de 1 min en ambos casos. Queda en log auditable con autor y fecha.

**Documentación:**
- PRD: PRD-VENTAS-03 BDC
- Flow: Validar T&C
- Prototipo: (link de Figma)

**Flujo:**
`Bandeja "T&C pendientes de validación"` → MANUAL → `Click en T&C` → `Revisa los 5 campos obligatorios + condiciones generales` → MANUAL → `Decisión: Aprobar o Rechazar` → Si Aprueba → `Comentario opcional` → `Confirmar` → AUTOMATICO → `T&C queda como Validado + Notifica al BD + Permite avanzar a Rosa + Log auditable` / Si Rechaza → `Observaciones obligatorias (mín. 30 caracteres)` → `Confirmar` → AUTOMATICO → `T&C vuelve a editable por el BD + Notifica al BD con observaciones + Log auditable`
