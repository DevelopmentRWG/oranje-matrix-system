---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - CU RF-17
---

# 🪪 ID: RF-17
🏷️ **Nombre:** Solicitar reasignación de colaborador

**Historia:**
Cuando un colaborador necesita ser rotado de un hotel a otro (por solicitud del hotel, del colaborador o decisión operativa), la Reclutadora solicita la reasignación. El historial queda visible y, si es un caso sensible (hotel VIP), se escala al Manager para aprobación.

**Criterios de aceptación:**
La reasignación queda registrada en el historial. Si el caso es sensible, el sistema notifica al Manager para aprobación. El Schedule de ambos hoteles se actualiza automáticamente.

**Documentación:**
- PRD: PRD-RECL-02 Reclutadora
- Flow: Reasignación
- Prototipo: (link de Figma)

**Flujo:**
`Asignación activa` → MANUAL → `Click "Reasignar"` → `Seleccionar nuevo hotel` → `Confirmar` → AUTOMATICO → Si es sensible → `Notifica al Manager` → MANUAL Manager → `Aprueba` → AUTOMATICO → `Actualiza Schedule en ambos hoteles + Registra historial`
