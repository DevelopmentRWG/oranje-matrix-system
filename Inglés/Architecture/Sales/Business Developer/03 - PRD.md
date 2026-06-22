---
tags:
  - arquitectura
  - rol/business-developer
aliases:
  - Business Developer PRD
---

# PRODUCT REQUIREMENTS DOCUMENT
## PRD – BUSINESS DEVELOPER

**Personnel Management System · Business Developer (BD) Role — Sales**

---

| Field                   | Content                                                                       |
| ----------------------- | --------------------------------------------------------------------------- |
| **PRD ID**              | PRD-VENTAS-02                                                               |
| **User Story**          | HU-VENTAS-02                                                                |
| **Department**          | Sales                                                                      |
| **Functionality**       | Run the commercial cycle with prospect hotels in the assigned territory     |
| **Main Actor**          | Business Developer (BD)                                                     |
| **Device**              | Mobile (priority) / Tablet / Desktop                                        |
| **Status**              | In definition                                                              |
| **Version**             | 1.0                                                                         |

---

## Objective

Allow the Business Developer to **identify, contact, propose and follow up** with prospect hotels in their assigned territory, taking them through the Onboarding Status Light up to Pink status, where the BDC takes the final conversion.

---

## General Flow

**I identify a prospect (Gray) → I collect data + cold visit (Light Blue) → I prepare and send the Proposal (Green) → Follow-up (Yellow) → I create the T&C → I negotiate with the BDC (Pink) → BDC approves → Orange (active client) → I remain as a commercial reference**

---

## Use Cases

| ID      | Use Case                            | Priority  |
| ------- | ----------------------------------- | --------- |
| RF-V-01 | Identify prospect (Gray)            | 🔴 High   |
| RF-V-02 | Create hotel profile (Light Blue)   | 🔴 High   |
| RF-V-03 | Register cold visit                 | 🟡 Medium |
| RF-V-04 | Prepare Personalized Proposal       | 🔴 High   |
| RF-V-05 | Send proposal to hotel              | 🔴 High   |
| RF-V-06 | Register contact attempts           | 🟡 Medium |
| RF-V-07 | Advance to Yellow (interest)        | 🔴 High   |
| RF-V-08 | Create T&C Document                 | 🔴 High   |
| RF-V-09 | Initiate negotiation (Pink)         | 🔴 High   |
| RF-V-15 | Manage rejection (Red)              | 🟡 Medium |
| RF-V-16 | Reactivate prospect from Red        | 🟡 Medium |
| RF-V-17 | Mark stagnation (Brown)             | 🟡 Medium |
| RF-V-22 | View Pipeline                       | 🔴 High   |
| RF-V-23 | View My Territory                   | 🔴 High   |
| RF-V-29 | View Active Clients (reference)     | 🟡 Medium |

---

## Applicable Business Rules

| ID      | Rule                                  | Description / How it applies to the BD                                                                                        | Priority  |
| ------- | ------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | --------- |
| RR-V-01 | Conversion exclusive to the BDC       | The BD does NOT approve conversion under any circumstances. That action is exclusive to the BDC and triggers the Automatic Trigger. | 🔴 High   |
| RR-V-04 | Brown unblocking exclusive to the BDC | The BD can MARK Brown when they detect stagnation, but can NOT unblock it — the BDC investigates and resolves that.            | 🔴 High   |
| RR-V-06 | Rejection (Red) management by the BD  | The BD is responsible for marking Red when the hotel rejects the proposal. It is their exclusive action, not the BDC's.       | 🔴 High   |
| RR-V-07 | Reactivations always to Light Blue    | When the BD reactivates a prospect from Red, the system automatically returns it to Light Blue — never to Gray.               | 🔴 High   |
| RR-V-09 | Personalized Proposal only in Green   | The BD can only prepare and send the Personalized Proposal in Green status. Outside that status, the action is blocked.       | 🔴 High   |
| RR-V-11 | Traceability of status changes        | Every status change made by the BD is recorded with date, author and mandatory comment.                                      | 🔴 High   |
| RR-V-12 | Post-Orange: commercial references    | Once the hotel moves to Orange, the BD remains as a commercial reference — without operational permissions over the hotel.    | 🔴 High   |

---

## Restrictions / Permissions

| #   | Action the BD can NOT perform          | Why (rule / decision)                             | Who CAN                                     |
| --- | -------------------------------------- | ------------------------------------------------- | ------------------------------------------- |
| 1   | Validate T&C Document                  | RR-V-15 — final yes exclusive to the BDC          | BDC                                         |
| 2   | Create Hotel User                      | RR-V-02 — precondition exclusive to the BDC       | BDC                                         |
| 3   | Approve prospect conversion            | RR-V-01 — action exclusive to the BDC             | BDC                                         |
| 4   | Unblock stagnation (Brown)             | RR-V-04 — investigation exclusive to the BDC      | BDC                                         |
| 5   | Mark client Black                      | RR-V-05 — management exclusive to the BDC         | BDC                                         |
| 6   | Reactivate client from Black           | RR-V-05 — exclusive to the BDC                    | BDC                                         |
| 7   | View prospects outside their territory | Scope limited to assigned routes and zones        | BDC (global view) / other BDs in their zones |
| 8   | View individual metrics of other BDs   | No access to others' performance                  | BDC                                         |
| 9   | Generate executive reports             | No access to the Reports module                   | BDC                                         |
| 10  | Edit the hotel post-Orange             | RR-V-12 — commercial reference without operation  | Area Manager / Recruitment                  |
| 11  | Create requisitions                    | Post-Orange operation exclusive to the Hotel module | Supervisor / Area Manager                 |
