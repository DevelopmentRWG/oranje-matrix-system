---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-40
---

# 🪪 ID: RF-40
🏷️ **Nombre:** Ver reclutadores activos de la requisición

**Historia:**
Como el modelo de requisiciones es **colaborativo (RR-15)**, una misma requisición puede tener **varios reclutadores participantes** trabajándola a la vez. Desde el detalle de la requisición, cualquier participante (y el Líder/Manager) ve la **lista de reclutadores activos**: quién la está trabajando ahora mismo, con su rol y desde cuándo se unió. Es la base visual del modelo colaborativo: saber con quién se comparte el trabajo antes de asignar o de unirse.

**Criterios de aceptación:**
Visible en el detalle de cualquier requisición En proceso. Lista a cada reclutador participante con: rol (Reclutadora / Líder de Grupo), nombre y momento en que se unió. Se actualiza automáticamente cuando alguien se une (RF-39) o sale (RF-03). El primero que la tomó y los que se unieron después se muestran por igual (no hay dueño único). Visible para todos los participantes, el Líder del grupo y el Manager. Desde aquí se accede al Historial completo (RF-41).

**Documentación:**
- PRD: PRD-RECL-03 Líder de Grupo
- Flow: Reclutadores activos de la requisición
- Prototipo: (link de Figma)

**Flujo:**
`Requisiciones → Abrir requisición (detalle)` → AUTOMATICO → `Sistema lista los reclutadores participantes activos (rol + nombre + "se unió hace X")` → MANUAL → `(opcional) Unirme (RF-39)` · `Ver Historial de la requisición (RF-41)`
