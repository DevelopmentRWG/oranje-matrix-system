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
Tras aprobar, el colaborador queda habilitado para asignación. Se propagan accesos automáticamente. Estado del semáforo: Verde fuerte (Disponible).

**Documentación:**
- PRD: PRD-RECL-02 Reclutadora
- Flow: Validar colaborador
- Prototipo: (link de Figma)

**Flujo (aprobación):**
`Bandeja "Pendientes de validar"` → MANUAL → `Abrir candidato` → `Revisar datos y documentos` → MANUAL → `Click "Aprobar"` → AUTOMATICO → `Sistema habilita colaborador + Propaga accesos + Notifica al colaborador` → `Semáforo: Verde fuerte (Disponible)`

**Flujo (rechazo):**
`Bandeja "Pendientes de validar"` → MANUAL → `Abrir candidato` → `Revisar datos y documentos` → MANUAL → `Click "Rechazar"` → `Ingresar motivo (campo obligatorio)` → AUTOMATICO → `Sistema notifica al colaborador con el motivo para que corrija datos/documentos en la app` → `NO se habilitan accesos` → `El registro permanece en "Pendientes de validación" hasta una nueva revisión`

> [!info]
> El rechazo NO es una baja definitiva. El colaborador puede corregir sus datos o documentos en la app y volver a quedar en estado "Pendiente de validación" para una nueva revisión por la Reclutadora.
