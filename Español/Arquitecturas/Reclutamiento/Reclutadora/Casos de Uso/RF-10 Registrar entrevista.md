---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - CU RF-10
---

# 🪪 ID: RF-10
🏷️ **Nombre:** Registrar entrevista

**Historia:**
La Reclutadora documenta el resultado de la entrevista realizada al candidato (aprobado, rechazado, observaciones). El registro queda ligado al perfil del candidato con fecha y autor para trazabilidad.

**Criterios de aceptación:**
El registro queda ligado al perfil del candidato. Visible en el historial de entrevistas. Incluye fecha, autor (Reclutadora), resultado y observaciones.

**Documentación:**
- PRD: PRD-RECL-02 Reclutadora
- Flow: Registro de entrevista
- Prototipo: (link de Figma)

**Flujo:**
`Perfil del candidato` → MANUAL → `Click "Registrar entrevista"` → `Llena formulario (resultado, observaciones)` → `Confirmar` → AUTOMATICO → `Registra en historial + Liga al perfil del candidato`
