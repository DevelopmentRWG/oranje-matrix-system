---
tags:
  - module/customer-service
  - flow
aliases:
  - Customer Service Flow
  - Customer Service Attendance Flow
---

# Customer Service Flow

Step-by-step process for handling requests from the active client hotel. The flow covers from the receipt of a request through to its closure or escalation. Applies exclusively to hotels in **Orange** status of the [[Core/Modules/Status Indicators/Onboarding Status Indicator|Onboarding Status Indicator]].

## Step 1 — Request Receipt

**Responsible:** [[Customer Service/Customer Service Agent|Customer Service Agent]]

The hotel contacts Customer Service through the enabled channels. The hotel's point of contact may be the [[Hotel/General Manager|General Manager]], the [[Hotel/Area Manager|Area Manager]], or the [[Hotel/Supervisor|Supervisor]].

**Action:** the Agent records the request with the following data:
- Hotel and contact.
- Date and time of receipt.
- Description of the request.
- Category (inquiry, complaint, incident, operational request).

**Advance →** upon recording the request, it moves to Step 2.

## Step 2 — Classification and Initial Response

**Responsible:** [[Customer Service/Customer Service Agent|Customer Service Agent]]

The Agent evaluates the request and determines whether it can be resolved directly or requires coordination with another department.

**Decision: Can the Agent resolve it directly?**

- **YES →** the Agent resolves it, documents the solution, and moves to Step 5 (Closure).
- **NO →** moves to Step 3 (Interdepartmental Coordination).

**Decision: Does the request involve a commercial dispute or risk of transitioning to Black?**

- **YES →** immediate escalation to the [[Customer Service/Customer Service Manager|Customer Service Manager]] (Step 4).

## Step 3 — Interdepartmental Coordination

**Responsible:** [[Customer Service/Customer Service Agent|Customer Service Agent]]

The Agent contacts the corresponding internal department to obtain the necessary information or action:

| Incident Type | Department to Contact | Contact |
|---|---|---|
| Associate did not show up / performance issues | [[Inspection/Inspection\|Inspection]] | [[Inspection/Coordinator\|Coordinator]] |
| Position coverage / staff assignment | [[Recruitment/Recruitment\|Recruitment]] | [[Recruitment Manager]] |
| Billing or payment inquiries | Accounting | [[Accounting Manager]] |
| Contractual or commercial matters | [[Sales/Sales\|Sales]] | [[Sales/Roles/Business Developer Coordinator\|BDC]] |

**Action:** the Agent documents the coordination performed and the response received.

**Decision: Was a resolution obtained from the department?**

- **YES →** the Agent communicates the resolution to the hotel and moves to Step 5 (Closure).
- **NO →** the case is escalated to the [[Customer Service/Customer Service Manager|Customer Service Manager]] (Step 4).

## Step 4 — Escalation

Escalation follows the hierarchy defined in the [[Customer Service/Customer Service Rules|Customer Service Rules]]:

### Level 2 — Customer Service Manager

**Responsible:** [[Customer Service/Customer Service Manager|Customer Service Manager]]

Receives cases the Agent could not resolve or that involve multiple departments.

**Actions:**
- Reviews the case history.
- Coordinates directly with the responsible parties from the involved departments.
- Resolves the case and communicates to the hotel.

**Decision: Was it resolved?**

- **YES →** moves to Step 5 (Closure).
- **NO →** escalates to Level 3.

### Level 3 — Business Developer Coordinator

**Responsible:** [[Sales/Roles/Business Developer Coordinator|Business Developer Coordinator]]

Receives cases with a commercial, contractual component or with client loss risk.

**Actions:**
- Evaluates the commercial impact.
- Negotiates a solution with the hotel.
- Coordinates contractual adjustments if applicable.

**Decision: Was it resolved?**

- **YES →** moves to Step 5 (Closure).
- **NO →** escalates to Level 4 (General Management).

### Level 4 — General Management

Cases unresolved at previous levels or with reputational risk.

> [!warning] If the dispute is not resolved and the hotel decides to pause or terminate the relationship, the [[Sales/Roles/Business Developer Coordinator|BDC]] executes the transition to **Black** status in the [[Core/Modules/Status Indicators/Onboarding Status Indicator|Onboarding Status Indicator]]. Customer Service cannot modify the status indicator.

## Step 5 — Closure

**Responsible:** [[Customer Service/Customer Service Agent|Customer Service Agent]] or [[Customer Service/Customer Service Manager|Customer Service Manager]] (depending on who resolved it)

**Actions:**
- Documents the case resolution.
- Confirms with the hotel that the request was handled.
- Closes the case in the system.

## Key Points

- Customer Service **cannot modify** the status of the [[Core/Modules/Status Indicators/Onboarding Status Indicator|Onboarding Status Indicator]]; it only reports and escalates.
- Customer Service **does not substitute** the operations of any department; it coordinates, channels, and follows up.
- Every request must be documented regardless of whether it is resolved at Step 2 or reaches Step 4.
- Cases involving a commercial dispute are always escalated immediately to the [[Customer Service/Customer Service Manager|CS Manager]], without waiting for the normal cycle.

## Related

- [[Customer Service/Customer Service|Customer Service]]
- [[Customer Service/Customer Service Rules|Customer Service Rules]]
- [[Customer Service/Customer Service Manager|Customer Service Manager]]
- [[Customer Service/Customer Service Agent|Customer Service Agent]]
- [[Core/Modules/Status Indicators/Onboarding Status Indicator|Onboarding Status Indicator]]
- [[Sales/Roles/Business Developer Coordinator|Business Developer Coordinator]]
