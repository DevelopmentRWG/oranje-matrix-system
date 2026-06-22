---
tags:
  - arquitectura
  - rol/bdc
aliases:
  - BDC PRD
---

# PRODUCT REQUIREMENTS DOCUMENT
## PRD – BUSINESS DEVELOPER COORDINATOR

**Personnel Management System · BDC Role — Sales**

---

| Field                   | Content                                                                        |
| ----------------------- | ----------------------------------------------------------------------------- |
| **PRD ID**              | PRD-VENTAS-03                                                                 |
| **User Story**          | HU-VENTAS-03                                                                  |
| **Department**          | Sales                                                                         |
| **Functionality**       | Validate T&C, approve conversions, supervise BDs, manage special cases        |
| **Main Actor**          | Business Developer Coordinator (BDC)                                          |
| **Device**              | Web – Desktop / Tablet                                                        |
| **Status**              | In definition                                                                |
| **Version**             | 1.0                                                                           |

---

## Objective

Allow the BDC to **validate the quality** of each T&C before closing, **approve the final conversion** of the prospect into a client, **supervise the BD team** and **manage special cases** (Brown, Black). It is the role that safeguards the quality of client entry into the system.

---

## General Flow

**I review pending T&C → I validate or reject → I negotiate (Pink) alongside the BD → I create the Hotel User → I approve the conversion → Automatic Trigger → Active client (Orange) | In parallel: I manage Brown and Black cases, I supervise the team, I generate reports**

---

## Use Cases

| ID      | Use Case                       | Priority  |
| ------- | ------------------------------ | --------- |
| RF-V-08 | Create T&C Document (support)  | 🔴 High   |
| RF-V-09 | Start negotiation (Pink)       | 🔴 High   |
| RF-V-10 | Validate T&C                   | 🔴 High   |
| RF-V-11 | Create Hotel User              | 🔴 High   |
| RF-V-12 | Approve conversion to client   | 🔴 High   |
| RF-V-17 | Mark stagnation (Brown)        | 🟡 Medium |
| RF-V-18 | Unblock stagnation             | 🟡 Medium |
| RF-V-19 | Reactivate from Brown          | 🟡 Medium |
| RF-V-20 | Mark client Black              | 🟡 Medium |
| RF-V-21 | Reactivate from Black          | 🟢 Low    |
| RF-V-22 | View Pipeline (global)         | 🔴 High   |
| RF-V-24 | View My Team                   | 🔴 High   |
| RF-V-25 | Individual metrics per BD      | 🟡 Medium |
| RF-V-26 | Generate Sales report          | 🟡 Medium |
| RF-V-27 | Send report to management      | 🟡 Medium |
| RF-V-29 | View Active Clients            | 🟡 Medium |

---

## Applicable Business Rules

| ID      | Rule                                  | Description / How it applies to the BDC                                                                                       | Priority  |
| ------- | ------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | --------- |
| RR-V-01 | Conversion exclusive to the BDC       | The BDC is the ONLY one who can approve the conversion of prospect to active client. The BD can never execute this action.    | 🔴 High   |
| RR-V-02 | Precondition — Hotel User             | Before approving conversion, the BDC MUST create the Hotel User. Without this step, the "Approve" button stays blocked.       | 🔴 High   |
| RR-V-03 | Automatic Trigger runs 3 actions      | When approving conversion, the system fires 3 actions in parallel: welcome email + notif to the BD + removal from Pipeline.   | 🔴 High   |
| RR-V-04 | Brown unblocking exclusive to the BDC | When a BD marks Brown, the case passes to the BDC who investigates, diagnoses and reactivates (or reassigns / closes as Red). | 🔴 High   |
| RR-V-05 | Black client exclusive to the BDC     | Only the BDC marks and reactivates Black clients (paused / inactive). The BD only receives a notification, does not intervene.| 🔴 High   |
| RR-V-07 | Reactivations always to Light Blue    | When the BDC reactivates from Brown or Black, the status returns to Light Blue — never to Gray.                               | 🔴 High   |
| RR-V-11 | Traceability of status changes        | Every BDC decision (T&C validation, conversion, Brown, Black) is recorded in an auditable log with date, author and reason.   | 🔴 High   |
| RR-V-15 | Contract results from successful close | When approving the conversion, the system generates the Contract using the BDC-validated T&C as a mandatory input.           | 🔴 High   |

---

## Restrictions / Permissions

| #   | Action the BDC CANNOT do                        | Why (rule / decision)                              | Who CAN                            |
| --- | ----------------------------------------------- | -------------------------------------------------- | ---------------------------------- |
| 1   | Identify prospects (Gray)                       | It is an operational field action, exclusive to the BD | BD                             |
| 2   | Draft Personalized Proposal                     | Action exclusive to the BD (RR-V-09 — only in Green)   | BD                             |
| 3   | Mark prospect as Red                            | RR-V-06 — rejection management exclusive to the BD     | BD                             |
| 4   | Reactivate prospect from Red                    | Belongs to the BD cycle                            | BD                                 |
| 5   | Edit the hotel post-Orange                      | RR-V-12 — commercial reference without operation   | Area Manager / Recruitment         |
| 6   | Create requisitions                             | Post-Orange operation, exclusive to the Hotel module | Supervisor / Area Manager        |
| 7   | Register / deregister BDs                        | User management is exclusive to the Administrator  | Administrator *(on hold)*          |
| 8   | Operate the operational cycle (Schedule, Timesheet) | Outside the scope of the Sales department       | Hotel + Recruitment + Inspection   |
