---
tags:
  - arquitectura
  - rol/bdc
  - caso-de-uso
aliases:
  - CU RF-V-18
---

# 🪪 ID: RF-V-18
🏷️ **Nombre:** Desbloquear estancamiento (Café)

**Historia:**
Cuando un BD marca un prospecto como **Café** por estancamiento, el caso queda en la bandeja Café del BDC. El BDC investiga el contexto (notas del BD, histórico de contactos, intentos previos), diagnostica la causa real y acuerda una solución para retomar la negociación. Esta acción es **exclusiva del BDC** (RR-V-04) y precede a la reactivación (RF-V-19).

**Criterios de aceptación:**
Solo el BDC puede desbloquear Café (RR-V-04). Diagnóstico obligatorio (mín. 50 caracteres). Solución acordada obligatoria (mín. 50 caracteres). Decisión obligatoria: Reactivar a Azul Claro / Reasignar a otro BD / Cerrar como Rojo. Notifica al BD original con la solución. Queda en log auditable.

**Documentación:**
- PRD: PRD-VENTAS-03 BDC
- Flow: Desbloquear Café
- Prototipo: (link de Figma)

**Flujo:**
`Bandeja Café del BDC` → MANUAL → `Click en prospecto` → `Investiga histórico, notas del BD, intentos de contacto` → MANUAL → `Click "Desbloquear Café"` → `Diagnóstico (mín. 50 caracteres)` → `Solución acordada (mín. 50 caracteres)` → `Decisión (catálogo: Reactivar / Reasignar / Cerrar como Rojo)` → `Confirmar` → AUTOMATICO → Si Reactivar → `Status regresa a Azul Claro + Notifica al BD original (dispara RF-V-19)` / Si Reasignar → `Cambia BD asignado + Status a Azul Claro + Notifica a ambos BDs` / Si Cerrar como Rojo → `Status pasa a Rojo + Notifica al BD original`
