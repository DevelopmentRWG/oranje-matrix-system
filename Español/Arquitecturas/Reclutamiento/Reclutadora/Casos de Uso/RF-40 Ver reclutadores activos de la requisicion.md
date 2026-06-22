---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - CU RF-40 (Reclutadora)
---

# 🪪 ID: RF-40
🏷️ **Nombre:** Ver reclutadores activos de la requisición

**Historia:**
Como el modelo de requisiciones es **colaborativo (RR-15)**, una misma requisición puede tener **varios reclutadores participantes** a la vez. Desde el detalle de la requisición, la Reclutadora ve la **lista de reclutadores activos**: quién la está trabajando ahora mismo, con su rol y desde cuándo se unió. Así sabe con quién comparte el trabajo antes de asignar colaboradores o de unirse.

**Criterios de aceptación:**
Visible en el detalle de cualquier requisición En proceso. Lista a cada reclutador participante con: rol (Reclutadora / Líder de Grupo), nombre y momento en que se unió. Se actualiza al unirse (RF-39) o salir (RF-03) un reclutador. No hay dueño único: todos los participantes se muestran por igual. Desde aquí se accede al Historial completo (RF-41).

**Documentación:**
- PRD: PRD-RECL-02 Reclutadora
- Flow: Reclutadores activos de la requisición
- Prototipo: (link de Figma)

**Flujo:**
`Requisiciones → Abrir requisición (detalle)` → AUTOMATICO → `Sistema lista los reclutadores participantes activos (rol + nombre + "se unió hace X")` → MANUAL → `(opcional) Unirme (RF-39)` · `Ver Historial de la requisición (RF-41)`
