---
tags:
  - module/sales
aliases:
  - Sales Rules
---

# Sales Rules

Consolidation of all business rules that apply to the Sales department within the Oranje system. Cross-reference with [[Reglas de Negocio]] (system-wide general reference).

## Department Hierarchy

| Role | Function |
|---|---|
| [[Ventas/Roles/Business Developer Coordinator\|Business Developer Coordinator (BDC)]] | Supervises BDs in their territory. Validates terms, approves conversions, and manages stalls |
| [[Ventas/Roles/Business Developer\|Business Developer (BD)]] | Field commercial executor. Identifies prospects, prepares proposals, and follows up |

## Onboarding Status Indicator Cycle

The hotel acquisition process follows the [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]], documented in detail in the [[Ventas/Onboarding-Hotel/Flujo de Onboarding|Flujo de Onboarding]].

| Status | Description | Primary Responsible |
|---|---|---|
| **Gray** | Identified prospect with no contact | [[Ventas/Roles/Business Developer\|BD]] |
| **Light Blue** | Profile created, data collected, cold visit completed | [[Ventas/Roles/Business Developer\|BD]] |
| **Green** | Customized Proposal prepared and sent; active follow-up | [[Ventas/Roles/Business Developer\|BD]] |
| **Yellow** | T&C document created; post-proposal follow-up | [[Ventas/Roles/Business Developer\|BD]] + [[Ventas/Roles/Business Developer Coordinator\|BDC]] (support) |
| **Pink** | Terms negotiation; final validation and close | [[Ventas/Roles/Business Developer\|BD]] + [[Ventas/Roles/Business Developer Coordinator\|BDC]] |
| **Orange** | Active hotel client; moves to operations | [[Inspector]] + [[Reclutadora]] (operational) / BD and BDC (commercial reference) |
| **Red** | Hotel rejection; decision to reactivate or archive | [[Ventas/Roles/Business Developer\|BD]] |
| **Black** | Paused or inactive client | [[Ventas/Roles/Business Developer Coordinator\|BDC]] |
| **Brown** | Stall; unblocking bridge | [[Ventas/Roles/Business Developer Coordinator\|BDC]] |

## Customized Proposal

- Prepared and sent at **Green** status of the [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]].
- Adjusted or resumed from **Brown** status when there is a stall.
- Reference: [[Ventas/Onboarding-Hotel/Conceptos/Propuesta Personalizada|Propuesta Personalizada]].

## Terms and Conditions Document

| Phase | Status | Responsible |
|---|---|---|
| Creation | **Yellow** | [[Ventas/Roles/Business Developer\|BD]] or [[Ventas/Roles/Business Developer Coordinator\|BDC]] |
| Negotiation | **Pink** | [[Ventas/Roles/Business Developer\|BD]] + [[Ventas/Roles/Business Developer Coordinator\|BDC]] |
| Final validation | **Pink** (before close) | [[Ventas/Roles/Business Developer Coordinator\|BDC]] |

Required content:

| Field |
|---|
| Pay rate |
| Bill rate |
| Overtime |
| Holidays |
| Calendar |

- Reference: [[Ventas/Onboarding-Hotel/Conceptos/Documento de Términos y Condiciones|Documento de Términos y Condiciones]].

## Contract

The [[Core/Módulos/Contrato|Contrato]] results from a successful close at **Pink** status:

- Required input: [[Ventas/Onboarding-Hotel/Conceptos/Documento de Términos y Condiciones|Documento de Términos y Condiciones]].
- The [[Ventas/Roles/Business Developer Coordinator|BDC]] validates before the close.

| Contract Field | Effect in the system |
|---|---|
| Pay rate | Associate payment calculations |
| Bill rate | Hotel billing calculations |
| Overtime | Overtime rules |
| Holidays | Holiday calendar |
| Week start and end | Configures the hotel's weekly [[Core/Módulos/Schedule\|Schedule]] structure |
| Term | Contract validity period |
| Renewal | Renewal terms |

## Prospect-to-Client Conversion

> [!important] **Only** the [[Ventas/Roles/Business Developer Coordinator\|BDC]] can approve the conversion of a prospect to a client.

**Mandatory precondition:** creation of the [[Ventas/Onboarding-Hotel/Conceptos/Usuario del Hotel|Usuario del Hotel]] in the system before triggering the conversion.

### Automatic Conversion Trigger

Upon approving the conversion, the system automatically executes three actions in parallel:

1. Sends a welcome email to the hotel.
2. Notifies the assigned [[Ventas/Roles/Business Developer\|BD]].
3. The hotel disappears from the prospect list.

- Reference: [[Ventas/Onboarding-Hotel/Conceptos/Trigger Automático de Conversión|Trigger Automático de Conversión]].

## Reactivations

| Origin status | Reactivation destination | Responsible |
|---|---|---|
| **Red** (rejection) | → **Light Blue** | [[Ventas/Roles/Business Developer\|BD]] |
| **Black** (paused/inactive) | → **Light Blue** | [[Ventas/Roles/Business Developer Coordinator\|BDC]] |
| **Brown** (stall) | → **Light Blue** | [[Ventas/Roles/Business Developer Coordinator\|BDC]] |

> [!note] **Brown** is not a terminal status. It is an unblocking bridge operated exclusively by the [[Ventas/Roles/Business Developer Coordinator\|BDC]], who investigates the cause of the stall and provides a solution to resume.

## Transition to Operations (Orange)

> [!important] **Orange** is the only status in the [[Core/Módulos/Semáforos/Semáforo Onboarding\|Semáforo Onboarding]] that enables the hotel to generate requisitions.

- Upon reaching Orange, the hotel passes to the operational responsibility of the [[Inspector]] and the [[Reclutadora|Recruiters]].
- The [[Ventas/Roles/Business Developer\|BD]] and [[Ventas/Roles/Business Developer Coordinator\|BDC]] remain as **commercial references**, not as operators.
- The operational cycle begins: Requisitions → coverage → [[Core/Módulos/Schedule\|Schedule]] → [[Timesheet]].

## Traceability

> [!info] Every status change in the [[Core/Módulos/Semáforos/Semáforo Onboarding\|Semáforo Onboarding]] is recorded with: **date, responsible, and comment**.

## Quality Supervision (QA)

- A [[QA/Operador de QA\|QA Operator]] is permanently assigned to the Sales department.
- QA does **not execute** Sales operations; it only observes, measures, and provides feedback.
- The specific metrics the QA Operator monitors for Sales are defined in [[QA/Métricas y KPIs por Departamento#Ventas|Metrics and KPIs — Sales]].
- If the department's [[Core/Módulos/Semáforos/Indicador de Calidad\|Quality Indicator]] reaches **Red** status without improvement after notification, the QA Manager escalates to management.

## Responsibility Summary by Role

| Action | [[Ventas/Roles/Business Developer\|BD]] | [[Ventas/Roles/Business Developer Coordinator\|BDC]] |
|---|---|---|
| Identify prospect (Gray) | Yes | No |
| Create hotel profile (Light Blue) | Yes | No |
| Prepare Customized Proposal (Green) | Yes | No |
| Create T&C Document (Yellow) | Yes | Support |
| Negotiate terms (Pink) | Yes | Yes |
| Validate T&C and give final approval | No | Yes (exclusive) |
| Create Hotel User Account | No | Yes (exclusive) |
| Approve conversion to client | No | Yes (exclusive) |
| Manage rejection (Red) | Yes | No |
| Unblock stall (Brown) | No | Yes |
| Manage paused client (Black) | No | Yes |
| Commercial reference post-conversion (Orange) | Yes | Yes |

## Related

- [[Reglas de Negocio]]
- [[Ventas/Roles/Business Developer|Business Developer]]
- [[Ventas/Roles/Business Developer Coordinator|Business Developer Coordinator]]
- [[Ventas/Onboarding-Hotel/Flujo de Onboarding|Flujo de Onboarding]]
- [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]]
- [[Ventas/Onboarding-Hotel/Conceptos/Propuesta Personalizada|Propuesta Personalizada]]
- [[Ventas/Onboarding-Hotel/Conceptos/Documento de Términos y Condiciones|Documento de Términos y Condiciones]]
- [[Ventas/Onboarding-Hotel/Conceptos/Trigger Automático de Conversión|Trigger Automático de Conversión]]
- [[Ventas/Onboarding-Hotel/Conceptos/Usuario del Hotel|Usuario del Hotel]]
- [[Core/Módulos/Contrato|Contrato]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Timesheet]]
- [[Core/Módulos/Semáforos/Indicador de Calidad|Indicador de Calidad]]
- [[Inspector]]
- [[Reclutadora]]
