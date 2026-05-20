---
tags:
  - module/customer-service
aliases:
  - Customer Service Rules
  - CS Rules
---

# Customer Service Rules

Consolidation of the business rules that apply to the Customer Service department within the Oranje system. Cross-reference with [[Business Rules]] (system-wide consolidated rules).

## Department Hierarchy

| Role | Function |
|---|---|
| [[Customer Service/Customer Service Manager\|Customer Service Manager]] | Supervises agents, manages escalations, and reports satisfaction metrics |
| [[Customer Service/Customer Service Agent\|Customer Service Agent]] | First point of contact; receives, documents, and resolves hotel requests |

## Escalation Hierarchy

Escalation follows a defined order based on severity and case type:

```
CS Agent → CS Manager → Business Developer Coordinator → Management
```

| Level | Responsible | Escalation Criteria |
|---|---|---|
| **1 - Direct handling** | [[Customer Service/Customer Service Agent\|CS Agent]] | General inquiries, simple operational requests |
| **2 - Supervision** | [[Customer Service/Customer Service Manager\|CS Manager]] | Cases unresolved within timeframe, recurring complaints, multiple departments involved |
| **3 - Commercial** | [[Sales/Roles/Business Developer Coordinator\|BDC]] | Contractual disputes, client loss risk, unresolved billing matters |
| **4 - Management** | General Management | Cases unresolved at previous levels, reputational risk |

## Relationship with the Onboarding Status Indicator

- Customer Service operates exclusively with hotels in **Orange** status (active client) of the [[Core/Modules/Status Indicators/Onboarding Status Indicator|Onboarding Status Indicator]].
- If a commercial dispute managed by Customer Service is not resolved and the hotel decides to pause or terminate the relationship, the [[Sales/Roles/Business Developer Coordinator|BDC]] is the one who executes the transition to **Black** status.
- Customer Service **cannot** modify the status of the [[Core/Modules/Status Indicators/Onboarding Status Indicator|Onboarding Status Indicator]]; it only reports and escalates.

## Department Limits

> [!important] Customer Service does not substitute the operations of any department. It coordinates, channels, and follows up, but execution belongs to the responsible department.

- **Does not create or approve** [[Requisition|requisitions]] — that is the [[Hotel/Hotel|Hotel]]'s responsibility.
- **Does not assign** associates — that is [[Recruitment/Recruitment|Recruitment]]'s responsibility.
- **Does not inspect** on-site — that is [[Inspection/Inspection|Inspection]]'s responsibility.
- **Does not acquire** new hotels — that is [[Sales/Sales|Sales]]'s responsibility.
- **Does not modify** contracts or commercial terms — that is the [[Sales/Roles/Business Developer Coordinator|BDC]]'s responsibility.

## Quality Supervision (QA)

- A [[QA Operator]] is permanently assigned to the Customer Service department.
- QA does **not execute** Customer Service operations; it only observes, measures, and provides feedback.
- If the [[Core/Modules/Status Indicators/Quality Indicator|Quality Indicator]] of the department reaches **Red** status without improvement after notification, the [[QA Manager]] escalates to management.

## Related

- [[Business Rules]]
- [[Customer Service/Customer Service Manager|Customer Service Manager]]
- [[Customer Service/Customer Service Agent|Customer Service Agent]]
- [[Customer Service/Customer Service|Customer Service]]
- [[Core/Modules/Status Indicators/Onboarding Status Indicator|Onboarding Status Indicator]]
- [[Sales/Roles/Business Developer Coordinator|Business Developer Coordinator]]
- [[Core/Modules/Status Indicators/Quality Indicator|Quality Indicator]]
- [[Hotel/Hotel|Hotel]]
