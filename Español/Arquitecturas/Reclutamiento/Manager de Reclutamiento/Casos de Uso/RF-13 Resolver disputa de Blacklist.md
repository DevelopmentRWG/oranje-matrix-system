---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - CU RF-13
---

# 🪪 ID: RF-13
🏷️ **Nombre:** Resolver disputa de Blacklist

**Historia:**
Cuando un colaborador disputa el motivo de su veto en la Blacklist, el caso queda en estado "Disputado" y solo el Manager puede resolverlo. El Manager revisa la evidencia, los comentarios del proponente y el historial del colaborador, y decide si mantiene el veto o lo remueve.

**Criterios de aceptación:**
La disputa solo puede ser resuelta por el Manager (regla RR-03). La decisión final requiere comentario obligatorio. Tras resolver, el sistema notifica al colaborador y a la Reclutadora que propuso el veto. Si la decisión es remover, dispara automáticamente el flujo RF-14.

**Documentación:**
- PRD: PRD-RECL-03 Manager
- Flow: Resolución de disputa de Blacklist
- Prototipo: (link de Figma)

**Flujo:**
`Bandeja Blacklist (caso disputado)` → MANUAL → `Click "Investigar"` → `Revisa evidencia + comentarios + historial` → MANUAL → `Click "Resolver"` → `Selecciona decisión (Mantener veto / Remover)` → `Comentario obligatorio` → `Confirmar` → AUTOMATICO → `Cierra disputa + Notifica al colaborador y Reclutadora + Registra en log` → Si decisión = Remover → `Dispara flujo RF-14`
