---
tags:
  - modulo/customer-service
aliases:
  - Customer Service Business Rules
  - CS Business Rules
---

# Customer Service Business Rules

Consolidation of the business rules that apply to the Customer Service department within the Oranje system. Cross-referenced with [[Business Rules|Business Rules]] (general system summary).

## Department hierarchy

| Role | Function |
|---|---|
| [[Customer Service/Customer Service Manager\|Customer Service Manager]] | Supervises agents, manages escalations and reports satisfaction metrics |
| [[Customer Service/Customer Service Agent\|Customer Service Agent]] | First point of contact; receives, documents and resolves hotel requests |

## Escalation hierarchy

Escalation follows a defined order according to the severity and type of the case:

```
CS Agent → CS Manager → Business Developer Coordinator → Management
```

| Level | Responsible | Escalation criteria |
|---|---|---|
| **1 - Direct handling** | [[Customer Service/Customer Service Agent\|CS Agent]] | General inquiries, simple operational requests |
| **2 - Supervision** | [[Customer Service/Customer Service Manager\|CS Manager]] | Cases not resolved on time, recurring complaints, multiple departments involved |
| **3 - Commercial** | [[Sales/Roles/Business Developer Coordinator\|BDC]] | Contractual disputes, risk of client loss, unresolved billing matters |
| **4 - Management** | General Management | Cases without resolution at previous levels, reputational risk |

## Relationship with the Onboarding Status Light

- Customer Service operates exclusively with hotels in **Orange** status (active client) of the [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]].
- If a commercial dispute managed by Customer Service is not resolved and the hotel decides to pause or terminate the relationship, the [[Sales/Roles/Business Developer Coordinator|BDC]] is the one who executes the transition to **Black** status.
- Customer Service **cannot** modify the status of the [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]]; it only reports and escalates.

## Department limits

> [!important] Customer Service does not replace the operation of any department. It coordinates, channels and follows up, but the execution is the responsibility of the responsible department.

- **Does not create or approve** [[Requisition|requisitions]] — that belongs to the [[Hotel/Hotel|Hotel]].
- **Does not assign** collaborators — that belongs to [[Recruitment/Recruitment|Recruitment]].
- **Does not inspect** on site — that belongs to [[Inspection/Inspection|Inspection]].
- **Does not acquire** new hotels — that belongs to [[Sales/Sales|Sales]].
- **Does not modify** contracts or commercial terms — that belongs to the [[Sales/Roles/Business Developer Coordinator|BDC]].

## Quality Supervision (QA)

- A [[QA Operator|QA Operator]] is permanently assigned to the Customer Service department.
- QA **does not execute** the Customer Service operation; it only observes, measures and gives feedback.
- If the department's [[Core/Modules/Status Lights/Quality Indicator|Quality Indicator]] reaches **Red** status without improvement after notification, the [[QA Manager|QA Manager]] escalates to management.

## Related

- [[Business Rules|Business Rules]]
- [[Customer Service/Customer Service Manager|Customer Service Manager]]
- [[Customer Service/Customer Service Agent|Customer Service Agent]]
- [[Customer Service/Customer Service|Customer Service]]
- [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]]
- [[Sales/Roles/Business Developer Coordinator|Business Developer Coordinator]]
- [[Core/Modules/Status Lights/Quality Indicator|Quality Indicator]]
- [[Hotel/Hotel|Hotel]]
