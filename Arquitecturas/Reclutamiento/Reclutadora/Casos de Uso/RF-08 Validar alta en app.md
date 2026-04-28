---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - CU RF-08
---

# 🪪 ID: RF-08
🏷️ **Nombre:** Validar alta en App (Fase 2)

**Historia:**
Tras el auto-registro del candidato en la app Oranje (donde completa SSN, ITIN, posición, inglés, experiencia, transporte, modalidad), la Reclutadora revisa los datos y documentos cargados. Si todo está bien, aprueba al colaborador y queda habilitado en el Pool.

**Criterios de aceptación:**
Tras aprobar, el colaborador queda habilitado para asignación. Se propagan accesos automáticamente. Estado del semáforo: Blanco (Pre-asignación).

**Documentación:**
- PRD: PRD-RECL-02 Reclutadora
- Flow: Validar colaborador
- Prototipo: (link de Figma)

**Flujo:**
`Bandeja "Pendientes de validar"` → MANUAL → `Abrir candidato` → `Revisar datos y documentos` → MANUAL → `Click "Aprobar"` → AUTOMATICO → `Sistema habilita colaborador + Propaga accesos + Notifica al colaborador`
