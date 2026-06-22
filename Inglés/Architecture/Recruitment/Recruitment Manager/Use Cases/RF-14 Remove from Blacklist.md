---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
aliases:
  - UC RF-14
---

# 🪪 ID: RF-14
🏷️ **Name:** Remove from Blacklist

**Story:**
After a review, a dispute resolved in the collaborator's favor or a case clarified by new evidence, the Manager manually removes a collaborator from the Blacklist. The action is exclusive to the Manager (rule RR-03) and automatically reactivates the collaborator in the Pool with Strong Green status (Available).

**Acceptance criteria:**
Only the Manager can remove (rule RR-03). Justification is mandatory. The collaborator is reactivated in the Pool in under 1 min. An auditable record is kept of who removed, when and with what reason. The collaborator is notified.

**Documentation:**
- PRD: PRD-RECL-03 Manager
- Flow: Blacklist removal
- Prototype: (Figma link)

**Flow:**
`Detalle de colaborador en Blacklist` → MANUAL → `Click "Remover"` → `Justificación obligatoria` → `Confirmar` → AUTOMATICO → `Reactiva en Pool (Verde fuerte) + Registra remoción en log auditable + Notifica al colaborador y Reclutadora`
