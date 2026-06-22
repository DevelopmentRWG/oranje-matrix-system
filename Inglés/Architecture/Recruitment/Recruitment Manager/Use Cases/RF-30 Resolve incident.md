---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - UC RF-30
---

# 🪪 ID: RF-30
🏷️ **Name:** Resolve incident

**Story:**
The Manager receives cases escalated by Group Leaders or Inspectors: operational problems, hotel-collaborator conflicts, situations that exceed the scope of the role that detected them. The Manager investigates (reviews evidence, comments and history) and issues a final decision that closes the case or escalates it to commercial.

**Acceptance criteria:**
The incident reaches the Manager in under 1 min after the escalation. The resolution requires a mandatory comment. The closure notifies everyone involved (Leader, Recruiter, Inspector, hotel if applicable). If the decision is to escalate to commercial, it triggers the RF-31 flow. It is kept in an auditable log.

**Documentation:**
- PRD: PRD-RECL-03 Manager
- Flow: Incident resolution
- Prototype: (Figma link)

**Flow:**
`Bandeja de Incidencias` → MANUAL → `Selecciona caso` → `Click "Investigar"` → `Revisa evidencia + comentarios + historial + involucrados` → MANUAL → `Click "Resolver"` → `Selecciona decisión (Resolver / Escalar a comercial / Solicitar más info) + comentario obligatorio` → `Confirmar` → AUTOMATICO → `Cierra caso o cambia estado + Notifica a involucrados + Registra en log` → Si decisión = Escalar → `Dispara flujo RF-31`
