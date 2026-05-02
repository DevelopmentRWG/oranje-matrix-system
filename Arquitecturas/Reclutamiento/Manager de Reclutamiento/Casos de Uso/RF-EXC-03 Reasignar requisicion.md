---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
  - excepcion
aliases:
  - CU RF-EXC-03
---

# 🪪 ID: RF-EXC-03
🏷️ **Nombre:** Reasignar requisición entre Reclutadoras

**Historia:**
**Excepción al modelo Self-Pick (RR-01).** Cuando una Reclutadora ya tomó una requisición pero no puede continuarla (ausencia inesperada, sobrecarga, escalamiento del Líder), el Manager mueve la requisición a otra Reclutadora. La Reclutadora original pierde acceso y la nueva la recibe con todo el contexto previo (notas, candidatos preseleccionados, historial).

**Criterios de aceptación:**
La acción rompe el Self-Pick y requiere motivo obligatorio. Queda en log auditable (regla RR-12). La Reclutadora original recibe notificación de pérdida de acceso. La nueva Reclutadora recibe la requisición con todo el contexto. Si la requisición tenía colaboradores preseleccionados, esos quedan visibles para la nueva Reclutadora. El semáforo no se resetea.

**Documentación:**
- PRD: PRD-RECL-03 Manager
- Flow: Reasignación excepcional
- Prototipo: (link de Figma)

**Flujo:**
`Detalle de requisición tomada` → MANUAL → `Click "Reasignar"` → `Selecciona nueva Reclutadora + motivo obligatorio (ausencia / sobrecarga / escalamiento)` → `Confirmar` → AUTOMATICO → `Reclutadora original pierde acceso + Notificación a Reclutadora original + Nueva Reclutadora recibe la requisición con contexto completo (notas + candidatos preseleccionados + historial) + Notificación a nueva Reclutadora + Notificación a ambos Líderes (si distintos) + Registro de excepción en log auditable`
