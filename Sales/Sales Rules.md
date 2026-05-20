---
tags:
  - module/sales
aliases:
  - Sales Rules
---

# Sales Rules

Consolidation of all business rules that apply to the Sales department within the Oranje system. Cross-reference with [[Business Rules]] (system-wide general reference).

## Department Hierarchy

| Role | Function |
|---|---|
| [[Sales/Roles/Business Developer Coordinator\|Business Developer Coordinator (BDC)]] | Supervises BDs in their territory. Validates terms, approves conversions, and manages stalls |
| [[Sales/Roles/Business Developer\|Business Developer (BD)]] | Field commercial executor. Identifies prospects, prepares proposals, and follows up |

## Onboarding Status Indicator Cycle

The hotel acquisition process follows the [[Core/Modules/Status Indicators/Onboarding Status Indicator|Onboarding Status Indicator]], documented in detail in the [[Sales/Onboarding-Hotel/Onboarding Flow|Onboarding Flow]].

| Status | Description | Primary Responsible |
|---|---|---|
| **Gray** | Identified prospect with no contact | [[Sales/Roles/Business Developer\|BD]] |
| **Light Blue** | Profile created, data collected, cold visit completed | [[Sales/Roles/Business Developer\|BD]] |
| **Green** | Customized Proposal prepared and sent; active follow-up | [[Sales/Roles/Business Developer\|BD]] |
| **Yellow** | T&C document created; post-proposal follow-up | [[Sales/Roles/Business Developer\|BD]] + [[Sales/Roles/Business Developer Coordinator\|BDC]] (support) |
| **Pink** | Terms negotiation; final validation and close | [[Sales/Roles/Business Developer\|BD]] + [[Sales/Roles/Business Developer Coordinator\|BDC]] |
| **Orange** | Active hotel client; moves to operations | [[Inspector]] + [[Recruiter]] (operational) / BD and BDC (commercial reference) |
| **Red** | Hotel rejection; decision to reactivate or archive | [[Sales/Roles/Business Developer\|BD]] |
| **Black** | Paused or inactive client | [[Sales/Roles/Business Developer Coordinator\|BDC]] |
| **Brown** | Stall; unblocking bridge | [[Sales/Roles/Business Developer Coordinator\|BDC]] |

## Customized Proposal

- Prepared and sent at **Green** status of the [[Core/Modules/Status Indicators/Onboarding Status Indicator|Onboarding Status Indicator]].
- Adjusted or resumed from **Brown** status when there is a stall.
- Reference: [[Sales/Onboarding-Hotel/Conceptos/Customized Proposal|Customized Proposal]].

## Terms and Conditions Document

| Phase | Status | Responsible |
|---|---|---|
| Creation | **Yellow** | [[Sales/Roles/Business Developer\|BD]] or [[Sales/Roles/Business Developer Coordinator\|BDC]] |
| Negotiation | **Pink** | [[Sales/Roles/Business Developer\|BD]] + [[Sales/Roles/Business Developer Coordinator\|BDC]] |
| Final validation | **Pink** (before close) | [[Sales/Roles/Business Developer Coordinator\|BDC]] |

Required content:

| Field |
|---|
| Pay rate |
| Bill rate |
| Overtime |
| Holidays |
| Calendar |

- Reference: [[Sales/Onboarding-Hotel/Conceptos/Terms and Conditions Document|Terms and Conditions Document]].

## Contract

The [[Core/Modules/Contract|Contract]] results from a successful close at **Pink** status:

- Required input: [[Sales/Onboarding-Hotel/Conceptos/Terms and Conditions Document|Terms and Conditions Document]].
- The [[Sales/Roles/Business Developer Coordinator|BDC]] validates before the close.

| Contract Field | Effect in the system |
|---|---|
| Pay rate | Associate payment calculations |
| Bill rate | Hotel billing calculations |
| Overtime | Overtime rules |
| Holidays | Holiday calendar |
| Week start and end | Configures the hotel's weekly [[Core/Modules/Schedule\|Schedule]] structure |
| Term | Contract validity period |
| Renewal | Renewal terms |

## Prospect-to-Client Conversion

> [!important] **Only** the [[Sales/Roles/Business Developer Coordinator\|BDC]] can approve the conversion of a prospect to a client.

**Mandatory precondition:** creation of the [[Sales/Onboarding-Hotel/Conceptos/Hotel User|Hotel User]] in the system before triggering the conversion.

### Automatic Conversion Trigger

Upon approving the conversion, the system automatically executes three actions in parallel:

1. Sends a welcome email to the hotel.
2. Notifies the assigned [[Sales/Roles/Business Developer\|BD]].
3. The hotel disappears from the prospect list.

- Reference: [[Sales/Onboarding-Hotel/Conceptos/Automatic Conversion Trigger|Automatic Conversion Trigger]].

## Reactivations

| Origin status | Reactivation destination | Responsible |
|---|---|---|
| **Red** (rejection) | → **Light Blue** | [[Sales/Roles/Business Developer\|BD]] |
| **Black** (paused/inactive) | → **Light Blue** | [[Sales/Roles/Business Developer Coordinator\|BDC]] |
| **Brown** (stall) | → **Light Blue** | [[Sales/Roles/Business Developer Coordinator\|BDC]] |

> [!note] **Brown** is not a terminal status. It is an unblocking bridge operated exclusively by the [[Sales/Roles/Business Developer Coordinator\|BDC]], who investigates the cause of the stall and provides a solution to resume.

## Transition to Operations (Orange)

> [!important] **Orange** is the only status in the [[Core/Modules/Status Indicators/Onboarding Status Indicator\|Onboarding Status Indicator]] that enables the hotel to generate requisitions.

- Upon reaching Orange, the hotel passes to the operational responsibility of the [[Inspector]] and the [[Recruiter|Recruiters]].
- The [[Sales/Roles/Business Developer\|BD]] and [[Sales/Roles/Business Developer Coordinator\|BDC]] remain as **commercial references**, not as operators.
- The operational cycle begins: Requisitions → coverage → [[Core/Modules/Schedule\|Schedule]] → [[Timesheet]].

## Traceability

> [!info] Every status change in the [[Core/Modules/Status Indicators/Onboarding Status Indicator\|Onboarding Status Indicator]] is recorded with: **date, responsible, and comment**.

## Quality Supervision (QA)

- A [[QA/QA Operator\|QA Operator]] is permanently assigned to the Sales department.
- QA does **not execute** Sales operations; it only observes, measures, and provides feedback.
- The specific metrics the QA Operator monitors for Sales are defined in [[QA/Metrics and KPIs by Department#Sales|Metrics and KPIs — Sales]].
- If the department's [[Core/Modules/Status Indicators/Quality Indicator\|Quality Indicator]] reaches **Red** status without improvement after notification, the QA Manager escalates to management.

## Responsibility Summary by Role

| Action | [[Sales/Roles/Business Developer\|BD]] | [[Sales/Roles/Business Developer Coordinator\|BDC]] |
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

- [[Business Rules]]
- [[Sales/Roles/Business Developer|Business Developer]]
- [[Sales/Roles/Business Developer Coordinator|Business Developer Coordinator]]
- [[Sales/Onboarding-Hotel/Onboarding Flow|Onboarding Flow]]
- [[Core/Modules/Status Indicators/Onboarding Status Indicator|Onboarding Status Indicator]]
- [[Sales/Onboarding-Hotel/Conceptos/Customized Proposal|Customized Proposal]]
- [[Sales/Onboarding-Hotel/Conceptos/Terms and Conditions Document|Terms and Conditions Document]]
- [[Sales/Onboarding-Hotel/Conceptos/Automatic Conversion Trigger|Automatic Conversion Trigger]]
- [[Sales/Onboarding-Hotel/Conceptos/Hotel User|Hotel User]]
- [[Core/Modules/Contract|Contract]]
- [[Core/Modules/Schedule|Schedule]]
- [[Timesheet]]
- [[Core/Modules/Status Indicators/Quality Indicator|Quality Indicator]]
- [[Inspector]]
- [[Recruiter]]
