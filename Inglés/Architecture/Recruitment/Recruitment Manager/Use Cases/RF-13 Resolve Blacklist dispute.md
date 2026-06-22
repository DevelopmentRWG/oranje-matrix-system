---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - UC RF-13
---

# 🪪 ID: RF-13
🏷️ **Name:** Resolve Blacklist dispute

**Story:**
When a collaborator disputes the reason for their ban in the Blacklist, the case is left in "Disputed" status and only the Manager can resolve it. The Manager reviews the evidence, the proposer's comments and the collaborator's history, and decides whether to maintain the ban or remove it.

**Acceptance criteria:**
The dispute can only be resolved by the Manager (rule RR-03). The final decision requires a mandatory comment. After resolving, the system notifies the collaborator and the Recruiter who proposed the ban. If the decision is to remove, it automatically triggers the RF-14 flow.

**Documentation:**
- PRD: PRD-RECL-03 Manager
- Flow: Blacklist dispute resolution
- Prototype: (Figma link)

**Flow:**
`Bandeja Blacklist (caso disputado)` → MANUAL → `Click "Investigar"` → `Revisa evidencia + comentarios + historial` → MANUAL → `Click "Resolver"` → `Selecciona decisión (Mantener veto / Remover)` → `Comentario obligatorio` → `Confirmar` → AUTOMATICO → `Cierra disputa + Notifica al colaborador y Reclutadora + Registra en log` → Si decisión = Remover → `Dispara flujo RF-14`
