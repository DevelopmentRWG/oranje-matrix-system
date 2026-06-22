---
tags:
  - arquitectura
  - departamento/ventas
aliases:
  - Sales Department PRD
---

# PRODUCT REQUIREMENTS DOCUMENT
## PRD – SALES

**Personnel Management System · Sales Department**

---

| Field | Content |
|---|---|
| **PRD ID** | PRD-VENTAS-01 |
| **User Story** | HU-VENTAS-01 |
| **Department** | Sales |
| **Functionality** | Manage the commercial cycle of acquiring hotels from their identification to conversion into an active client |
| **Primary Actor** | Business Developer · Business Developer Coordinator |
| **Device** | Web – Desktop / Mobile (BD in the field) |
| **Status** | In definition |
| **Version** | 1.0 |

---

## Objective

Enable the commercial team to **identify, contact, propose and convert prospect hotels into active clients** of Oranje, following the [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]]. The Sales department is the client's **gateway** into the system: nothing operates (Recruitment, Schedule, Timesheet) until Sales has closed the onboarding (Orange status).

---

## Scope

**Includes:**
- Identification of prospects by territory.
- Data collection and cold visit.
- Drafting and sending of the Personalized Proposal.
- Creation and validation of the Terms and Conditions Document.
- Negotiation of terms.
- Final approval and conversion to client (BDC exclusive).
- Automatic Conversion Trigger (3 parallel actions).
- Management of rejections (Red), stalls (Brown) and paused clients (Black).
- Reactivations (always to Light Blue).
- Territory supervision and BD performance (BDC).
- Executive reports.
- Status change traceability.

**Out of scope:**
- Post-Orange operation (Recruitment, Schedule, Timesheet) — moves to the Hotel and Recruitment departments.
- Operational inspection (Inspection module).
- Quality audit (QA module — observes, does not operate).
- System configuration (Administrator — on hold).

---

## General Flow

**Identify prospect (Gray) → Collect data and visit (Light Blue) → Send Proposal (Green) → Follow up (Yellow) → Negotiate (Pink) → BDC approves conversion + creates Hotel User + Automatic Trigger → Active client (Orange) → Hotel moves to operations**

```
GRAY (BD)
  ↓
LIGHT BLUE (BD)
  ↓
GREEN (BD) — Personalized Proposal
  ↓
YELLOW (BD + BDC support) — T&C Document
  ↓
PINK (BD + BDC) — Negotiation
  ↓ (BDC approves)
ORANGE — Automatic Trigger → Active client hotel

Alternate branches:
  • RED (BD) — Rejection → reactivate to Light Blue
  • BROWN (BDC) — Stall → unblock to Light Blue
  • BLACK (BDC) — Paused client → reactivate to Light Blue
```

---

## Actors

| Actor                          | Type           | Main responsibility                                         |
| ------------------------------ | -------------- | ----------------------------------------------------------- |
| Business Developer (BD)        | Operational    | Identifies, proposes, follows up, manages rejections        |
| Business Developer Coordinator | Supervisor     | Validates T&C, approves conversion, manages Brown and Black  |
| System                         | Automation     | Automatic trigger, traceability, notifications, status lights |
| Administrator *(on hold)*      | Configuration  | Users, catalogs, permissions                                |

---

## Constraints / Applicable business rules

See [[07 - Business Rules|07 - Business Rules]] for the detail. The most important ones:

- **RR-V-01:** Only the BDC approves the conversion.
- **RR-V-02:** Precondition — Hotel User created before the Trigger.
- **RR-V-03:** Automatic Trigger executes 3 actions in parallel.
- **RR-V-04:** Only the BDC unblocks a stall (Brown).
- **RR-V-08:** Orange is the only status that enables generating requisitions.

---

## Integrations (RI)

| ID      | Integration               | Description                                                                            |
| ------- | ------------------------- | ------------------------------------------------------------------------------------- |
| RI-V-01 | Sales ↔ Hotel             | Upon reaching Orange, the hotel is enabled in the Hotel module (generates requisitions). |
| RI-V-02 | Sales ↔ Recruitment       | The active client hotel receives Recruiters and Leaders to cover requisitions.        |
| RI-V-03 | Sales ↔ Inspection        | Upon activation, the hotel is assigned to an Inspector by zone.                        |
| RI-V-04 | Sales ↔ Contract          | Closing in Pink generates the Contract with validated T&C.                             |
| RI-V-05 | Sales ↔ Email System      | Automatic trigger sends a welcome email to the hotel.                                  |
| RI-V-06 | Sales ↔ QA                | Fixed QA operator assigned to the department. Metrics and Quality Indicator.          |

---

## Dependencies

See [[09 - Dependencies|09 - Dependencies]] for the detail.

- Depends on the [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]] as the backbone of the process.
- Depends on the [[Core/Modules/Contrato|Contract]] as the artifact generated at closing.
- Depends on [[Hotel/Hotel|Hotel]] as the final destination of the onboarding.
- Depends on [[Recruitment/Recruitment|Recruitment]] and [[Inspection/Inspection|Inspection]] as post-Orange receivers.
- Depends on [[QA/QA|QA]] as the department's observer.
