---
tags:
  - arquitectura
  - rol/business-developer
  - caso-de-uso
aliases:
  - CU RF-V-17 (BD)
---

# 🪪 ID: RF-V-17
🏷️ **Nombre:** Marcar estancamiento (Café)

**Historia:**
Cuando un prospecto no avanza tras múltiples intentos de contacto (sin respuesta, cambio de contacto, indecisión), el BD lo marca como **Café (Estancamiento)**. A partir de ese momento, **el caso pasa al BDC** que es el único que puede investigar la causa, dar solución y reactivar (RF-V-18, RF-V-19). El BD ya no puede modificar este prospecto hasta que el BDC lo desbloquee.

**Criterios de aceptación:**
Motivo obligatorio (catálogo: Sin respuesta / Cambio de contacto / Indefinido / Otro). Notas para el BDC obligatorias (mín. 30 caracteres) — ayudan al BDC a entender el contexto. Notifica al BDC en menos de 1 min. Bloquea edición por parte del BD hasta desbloqueo. Queda en línea de tiempo.

**Documentación:**
- PRD: PRD-VENTAS-02 Business Developer
- Flow: Marcar estancamiento (Café)
- Prototipo: (link de Figma)

**Flujo:**
`Detalle de prospecto estancado` → MANUAL → `Click "Marcar Café"` → `Selecciona motivo (catálogo)` → `Notas para el BDC (mín. 30 caracteres)` → `Confirmar` → AUTOMATICO → `Status pasa a Café + Notifica al BDC + Bloquea edición del BD + Aparece en bandeja Café del BDC + Línea de tiempo actualizada`

> [!info]
> El BDC desbloquea Café (RF-V-18) y luego reactiva el prospecto (RF-V-19) regresándolo a Azul Claro. A partir de ahí, el BD recupera el control y puede continuar el proceso.
