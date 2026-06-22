---
tags:
  - modulo/customer-service
  - flujo
aliases:
  - Customer Service Flow
  - Client Service Flow
---

# Customer Service Flow

Step-by-step process for handling requests from the active client hotel. The flow covers from the receipt of a request to its closure or escalation. It applies only to hotels in **Orange** status of the [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]].

## Step 1 — Receipt of the request

**Responsible:** [[Customer Service/Customer Service Agent|Customer Service Agent]]

The hotel contacts Customer Service through the enabled channels. The hotel's point of contact can be the [[Hotel/General Manager|General Manager]], the [[Hotel/Area Manager|Area Manager]] or the [[Hotel/Supervisor|Supervisor]].

**Action:** the Agent registers the request with the following data:
- Hotel and contact.
- Date and time of receipt.
- Description of the request.
- Category (inquiry, complaint, incident, operational request).

**Advance →** upon registering the request, it moves to Step 2.

## Step 2 — Classification and initial response

**Responsible:** [[Customer Service/Customer Service Agent|Customer Service Agent]]

The Agent evaluates the request and determines whether it can be resolved directly or whether it requires coordination with another department.

**Decision: Can the Agent resolve it directly?**

- **YES →** the Agent resolves it, documents the solution and moves to Step 5 (Closure).
- **NO →** moves to Step 3 (Interdepartmental coordination).

**Decision: Does the request involve a commercial dispute or risk of transition to Black?**

- **YES →** immediate escalation to the [[Customer Service/Customer Service Manager|Customer Service Manager]] (Step 4).

## Step 3 — Interdepartmental coordination

**Responsible:** [[Customer Service/Customer Service Agent|Customer Service Agent]]

The Agent contacts the relevant internal department to obtain the necessary information or action:

| Type of incident | Department to contact | Contact |
|---|---|---|
| Collaborator did not show up / performance issues | [[Inspection/Inspection\|Inspection]] | [[Inspection/Coordinator\|Coordinator]] |
| Coverage of positions / staff assignment | [[Recruitment/Recruitment\|Recruitment]] | [[Recruitment Manager\|Recruitment Manager]] |
| Billing or payment questions | Accounting | [[Accounting Manager\|Accounting Manager]] |
| Contractual or commercial matters | [[Sales/Sales\|Sales]] | [[Sales/Roles/Business Developer Coordinator\|BDC]] |

**Action:** the Agent documents the coordination carried out and the response obtained.

**Decision: Was a resolution obtained from the department?**

- **YES →** the Agent communicates the resolution to the hotel and moves to Step 5 (Closure).
- **NO →** the case is escalated to the [[Customer Service/Customer Service Manager|Customer Service Manager]] (Step 4).

## Step 4 — Escalation

The escalation follows the hierarchy defined in the [[Customer Service/Customer Service Rules|Customer Service Business Rules]]:

### Level 2 — Customer Service Manager

**Responsible:** [[Customer Service/Customer Service Manager|Customer Service Manager]]

Receives cases that the Agent could not resolve or that involve multiple departments.

**Actions:**
- Reviews the case history.
- Coordinates directly with the people responsible for the departments involved.
- Resolves the case and communicates with the hotel.

**Decision: Was it resolved?**

- **YES →** moves to Step 5 (Closure).
- **NO →** escalates to Level 3.

### Level 3 — Business Developer Coordinator

**Responsible:** [[Sales/Roles/Business Developer Coordinator|Business Developer Coordinator]]

Receives cases with a commercial or contractual component, or with a risk of client loss.

**Actions:**
- Evaluates the commercial impact.
- Negotiates a solution with the hotel.
- Coordinates contractual adjustments if applicable.

**Decision: Was it resolved?**

- **YES →** moves to Step 5 (Closure).
- **NO →** escalates to Level 4 (General Management).

### Level 4 — General Management

Cases without resolution at previous levels or with reputational risk.

> [!warning] If the dispute is not resolved and the hotel decides to pause or terminate the relationship, the [[Sales/Roles/Business Developer Coordinator|BDC]] executes the transition to **Black** status in the [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]]. Customer Service cannot modify the status of the status light.

## Step 5 — Closure

**Responsible:** [[Customer Service/Customer Service Agent|Customer Service Agent]] or [[Customer Service/Customer Service Manager|Customer Service Manager]] (depending on who resolved it)

**Actions:**
- Documents the resolution of the case.
- Confirms with the hotel that the request was handled.
- Closes the case in the system.

## Key points

- Customer Service **cannot modify** the status of the [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]]; it only reports and escalates.
- Customer Service **does not replace** the operation of any department; it coordinates, channels and follows up.
- Every request must be documented regardless of whether it is resolved in Step 2 or reaches Step 4.
- Cases with a commercial dispute are always escalated immediately to the [[Customer Service/Customer Service Manager|CS Manager]], without waiting for the normal cycle.

## Related

- [[Customer Service/Customer Service|Customer Service]]
- [[Customer Service/Customer Service Rules|Customer Service Business Rules]]
- [[Customer Service/Customer Service Manager|Customer Service Manager]]
- [[Customer Service/Customer Service Agent|Customer Service Agent]]
- [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]]
- [[Sales/Roles/Business Developer Coordinator|Business Developer Coordinator]]
