---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - CU RF-05
---

# 🪪 ID: RF-05
🏷️ **Nombre:** Marcar requisición como cubierta

**Historia:**
La Reclutadora termina de asignar todos los colaboradores requeridos por la requisición. Cuando todas las posiciones están al 100%, marca la requisición como "Cubierta". El Manager recibe la solicitud para validar el cierre.

**Criterios de aceptación:**
Solo se permite marcar como Cubierta si todas las posiciones están al 100% (regla RR-04). Al marcar, se notifica al Manager para validación del cierre.

**Documentación:**
- PRD: PRD-RECL-02 Reclutadora
- Flow: Cerrar requisición
- Prototipo: (link de Figma)

**Flujo:**
`Mis Requisiciones (100% cubierta)` → MANUAL → `Click en "Marcar cubierta"` → AUTOMATICO → `Solicita validación al Manager` → MANUAL Manager → `Aprueba cierre` → AUTOMATICO → `Semáforo Azul claro + Notifica al hotel`
