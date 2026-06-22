---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - CU RF-30
---

# 🪪 ID: RF-30
🏷️ **Nombre:** Resolver incidencia

**Historia:**
El Manager recibe casos escalados por Líderes de Grupo o Inspectores: problemas operativos, conflictos hotel-colaborador, situaciones que exceden el alcance del rol que las detectó. El Manager investiga (revisa evidencia, comentarios e historial) y emite una decisión final que cierra el caso o lo escala a comercial.

**Criterios de aceptación:**
La incidencia llega al Manager en menos de 1 min tras el escalamiento. La resolución requiere comentario obligatorio. El cierre notifica a todos los involucrados (Líder, Reclutadora, Inspector, hotel si aplica). Si la decisión es escalar a comercial, dispara el flujo RF-31. Queda en log auditable.

**Documentación:**
- PRD: PRD-RECL-03 Manager
- Flow: Resolución de incidencias
- Prototipo: (link de Figma)

**Flujo:**
`Bandeja de Incidencias` → MANUAL → `Selecciona caso` → `Click "Investigar"` → `Revisa evidencia + comentarios + historial + involucrados` → MANUAL → `Click "Resolver"` → `Selecciona decisión (Resolver / Escalar a comercial / Solicitar más info) + comentario obligatorio` → `Confirmar` → AUTOMATICO → `Cierra caso o cambia estado + Notifica a involucrados + Registra en log` → Si decisión = Escalar → `Dispara flujo RF-31`
