---
tags:
  - architecture
  - department/inspection
aliases:
  - Inspector Architecture
  - Inspector Wireframe
---

# Architecture — Inspector

Index and anchor of the architecture for the [[Inspector]] role within the Oranje system. The Inspector is the field-operative role of the [[Inspección/Inspección|Inspection department]]: verifies arrivals, delivers uniforms, investigates reported cases, and manages workplace accidents in their zone.

> [!info]
> The source of truth for the role and its rules lives in:
> - [[Inspector]] — role definition and responsibilities.
> - [[Inspección/Reglas de Inspección|Inspection Rules]] — department business rules.
> - [[Inspección/Inspección|Inspection]] — general department module.

> [!important]
> **Inspector's own authority in disputes:**
> The Inspector is the **only role** that can manually execute an entry into the Blacklist. When a collaborator is in Red status (reported by the hotel), the Inspector investigates and resolves:
> - In the hotel's favor → **Black** ([[Core/Módulos/Blacklist|Blacklist]]) — permanent ban.
> - In the collaborator's favor → **Strong Green** — reinstatement.
> This does not escalate to the Recruitment Manager.

## Scope of this architecture

This folder documents the platform architecture of the Inspector: the use cases assigned to them, the interaction flows with the system, and the rules that govern their actions. It does not cover the architecture of the [[Inspección/Coordinador|Coordinator]] (which will be documented separately if needed).

## Documented use cases

| ID | Name | Description |
|---|---|---|
| [[RF-13 Resolve collaborator dispute]] | Resolve collaborator dispute | The Inspector investigates a Red case and issues a verdict: Black (Blacklist) or Strong Green (reinstatement). |

## Inspector responsibilities (operational summary)

| Action | Source |
|---|---|
| Verify Day 1 arrival (Strong Green → Apple Green) | [[Inspección/Reglas de Inspección\|Inspection Rules]] |
| Deliver uniform Day 3+ (Apple Green → Light Blue) | [[Inspección/Reglas de Inspección\|Inspection Rules]] |
| Investigate Red-status cases | [[Inspector]] |
| Execute manual Blacklist entry (Red → Black) | [[Inspección/Reglas de Inspección\|Inspection Rules]] |
| Reinstate collaborator (Red → Strong Green) | [[Inspector]] |
| Complete and close workplace accident report | [[Inspección/Reglas de Inspección\|Inspection Rules]] |
| Manage Grey → Strong Green transition (medical clearance) | [[Inspector]] |
| Consult Extended Lunch Indicator | [[Inspección/Reglas de Inspección\|Inspection Rules]] |

## Related

- [[Inspector]]
- [[Inspección/Inspección|Inspection]]
- [[Inspección/Coordinador|Coordinator]]
- [[Inspección/Reglas de Inspección|Inspection Rules]]
- [[Semáforo del Colaborador|Collaborator Status Light]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Workplace Accident]]
- [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Workplace Accident Flow]]
- [[Manager de Reclutamiento|Recruitment Manager]]
