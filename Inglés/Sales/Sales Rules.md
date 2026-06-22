---
tags:
  - modulo/ventas
aliases:
  - Sales Rules
---

# Sales Rules

Consolidation of all the business rules that apply to the Sales department within the Oranje system. Cross-reference with [[Business Rules|Business Rules]] (general system summary).

## Department hierarchy

| Role | Function |
|---|---|
| [[Sales/Roles/Business Developer Coordinator\|Business Developer Coordinator (BDC)]] | Supervises the BDs in their territory. Validates terms, approves conversions and manages stalls |
| [[Sales/Roles/Business Developer\|Business Developer (BD)]] | Commercial executor in the field. Identifies prospects, prepares proposals and follows up |

## Onboarding Status Light cycle

The process of capturing a hotel follows the [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]], documented in detail in the [[Sales/Hotel Onboarding/Onboarding Flow|Onboarding Flow]].

| Status | Description | Main responsible |
|---|---|---|
| **Gray** | Prospect identified without contact | [[Sales/Roles/Business Developer\|BD]] |
| **Light Blue** | Profile created, data collected, cold visit performed | [[Sales/Roles/Business Developer\|BD]] |
| **Green** | Customized Proposal prepared and sent; active follow-up | [[Sales/Roles/Business Developer\|BD]] |
| **Yellow** | T&C Document created; post-proposal follow-up | [[Sales/Roles/Business Developer\|BD]] + [[Sales/Roles/Business Developer Coordinator\|BDC]] (support) |
| **Pink** | Terms negotiation; final validation and closing | [[Sales/Roles/Business Developer\|BD]] + [[Sales/Roles/Business Developer Coordinator\|BDC]] |
| **Orange** | Active client hotel; moves to operations | [[Inspector]] + [[Recruiter|Recruiter]] (operational) / BD and BDC (commercial reference) |
| **Red** | Hotel rejection; decision to reactivate or archive | [[Sales/Roles/Business Developer\|BD]] |
| **Black** | Client paused or inactive | [[Sales/Roles/Business Developer Coordinator\|BDC]] |
| **Brown** | Stall; unblocking bridge | [[Sales/Roles/Business Developer Coordinator\|BDC]] |

## Customized Proposal

- It is prepared and sent in **Green** status of the [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]].
- It is adjusted or resumed from **Brown** status when there is a stall.
- Reference: [[Sales/Hotel Onboarding/Concepts/Personalized Proposal|Customized Proposal]].

## Terms and Conditions Document

| Phase | Status | Responsible |
|---|---|---|
| Creation | **Yellow** | [[Sales/Roles/Business Developer\|BD]] or [[Sales/Roles/Business Developer Coordinator\|BDC]] |
| Negotiation | **Pink** | [[Sales/Roles/Business Developer\|BD]] + [[Sales/Roles/Business Developer Coordinator\|BDC]] |
| Final validation | **Pink** (prior to closing) | [[Sales/Roles/Business Developer Coordinator\|BDC]] |

Mandatory content:

| Field |
|---|
| Pay rate |
| Bill rate |
| Overtime |
| Holidays |
| Calendar |

- Reference: [[Sales/Hotel Onboarding/Concepts/Terms and Conditions Document|Terms and Conditions Document]].

## Contract

The [[Core/Modules/Contrato|Contract]] results from the successful closing in **Pink** status:

- Mandatory input: [[Sales/Hotel Onboarding/Concepts/Terms and Conditions Document|Terms and Conditions Document]].
- The [[Sales/Roles/Business Developer Coordinator|BDC]] validates before closing.

| Contract Field | Effect on the system |
|---|---|
| Pay rate | Calculation of payments to the collaborator |
| Bill rate | Calculation of billing to the hotel |
| Overtime | Overtime rules |
| Holidays | Holiday calendar |
| Start and end of week | Configures the structure of the hotel's weekly [[Core/Modules/Schedule\|Schedule]] |
| Validity | Contract validity period |
| Renewal | Renewal terms |

## Prospect to client conversion

> [!important] **Only** the [[Sales/Roles/Business Developer Coordinator\|BDC]] can approve the prospect to client conversion.

**Mandatory precondition:** creation of the [[Sales/Hotel Onboarding/Concepts/Hotel User|Hotel User]] in the system before triggering the conversion.

### Automatic Conversion Trigger

When the conversion is approved, the system automatically executes three actions in parallel:

1. Sends a welcome email to the hotel.
2. Notifies the assigned [[Sales/Roles/Business Developer\|BD]].
3. The hotel disappears from the prospect list.

- Reference: [[Sales/Hotel Onboarding/Concepts/Automatic Conversion Trigger|Automatic Conversion Trigger]].

## Reactivations

| Source status | Reactivation destination | Responsible |
|---|---|---|
| **Red** (rejection) | → **Light Blue** | [[Sales/Roles/Business Developer\|BD]] |
| **Black** (paused/inactive) | → **Light Blue** | [[Sales/Roles/Business Developer Coordinator\|BDC]] |
| **Brown** (stall) | → **Light Blue** | [[Sales/Roles/Business Developer Coordinator\|BDC]] |

> [!note] **Brown** is not a terminal status. It is an unblocking bridge operated exclusively by the [[Sales/Roles/Business Developer Coordinator\|BDC]], who investigates the cause of the stall and provides a solution to resume.

## Transition to Operations (Orange)

> [!important] **Orange** is the only status of the [[Core/Modules/Status Lights/Onboarding Status Light\|Onboarding Status Light]] that enables the hotel to generate requisitions.

- Upon reaching Orange, the hotel moves to the operational responsibility of the [[Inspector]] and the [[Recruiter|Recruiters]].
- The [[Sales/Roles/Business Developer\|BD]] and the [[Sales/Roles/Business Developer Coordinator\|BDC]] remain as **commercial references**, not as operational staff.
- The operational cycle begins: Requisitions → coverage → [[Core/Modules/Schedule\|Schedule]] → [[Timesheet]].

## Traceability

> [!info] Every status change in the [[Core/Modules/Status Lights/Onboarding Status Light\|Onboarding Status Light]] is recorded with: **date, responsible and comment**.

## Quality Supervision (QA)

- A [[QA/QA Operator\|QA Operator]] is permanently assigned to the Sales department.
- QA **does not execute** the Sales operation; it only observes, measures and gives feedback.
- The specific metrics that the QA Operator monitors for Sales are defined in [[QA/Metrics and KPIs by Department#Ventas|Metrics and KPIs — Sales]].
- If the department's [[Core/Modules/Status Lights/Quality Indicator\|Quality Indicator]] reaches **Red** status without improvement after notification, the QA Manager escalates to management.

## Summary of responsibilities by role

| Action | [[Sales/Roles/Business Developer\|BD]] | [[Sales/Roles/Business Developer Coordinator\|BDC]] |
|---|---|---|
| Identify prospect (Gray) | Yes | No |
| Create hotel profile (Light Blue) | Yes | No |
| Prepare Customized Proposal (Green) | Yes | No |
| Create T&C Document (Yellow) | Yes | Support |
| Negotiate terms (Pink) | Yes | Yes |
| Validate T&C and give final yes | No | Yes (exclusive) |
| Create Hotel User | No | Yes (exclusive) |
| Approve conversion to client | No | Yes (exclusive) |
| Manage rejection (Red) | Yes | No |
| Unblock stall (Brown) | No | Yes |
| Manage paused client (Black) | No | Yes |
| Commercial reference post-conversion (Orange) | Yes | Yes |

## Related

- [[Business Rules|Business Rules]]
- [[Sales/Roles/Business Developer|Business Developer]]
- [[Sales/Roles/Business Developer Coordinator|Business Developer Coordinator]]
- [[Sales/Hotel Onboarding/Onboarding Flow|Onboarding Flow]]
- [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]]
- [[Sales/Hotel Onboarding/Concepts/Personalized Proposal|Customized Proposal]]
- [[Sales/Hotel Onboarding/Concepts/Terms and Conditions Document|Terms and Conditions Document]]
- [[Sales/Hotel Onboarding/Concepts/Automatic Conversion Trigger|Automatic Conversion Trigger]]
- [[Sales/Hotel Onboarding/Concepts/Hotel User|Hotel User]]
- [[Core/Modules/Contrato|Contract]]
- [[Core/Modules/Schedule|Schedule]]
- [[Timesheet]]
- [[Core/Modules/Status Lights/Quality Indicator|Quality Indicator]]
- [[Inspector]]
- [[Recruiter|Recruiter]]
