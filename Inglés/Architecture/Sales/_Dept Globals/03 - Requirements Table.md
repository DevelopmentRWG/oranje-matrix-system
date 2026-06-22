---
tags:
  - arquitectura
  - departamento/ventas
aliases:
  - Sales Requirements Table
---

# REQUIREMENTS TABLE — SALES DEPARTMENT

**Personnel Management System · PRD-VENTAS-01 · STEP 5 OF DISCOVERY**

---

| Field               | Content                                                          |
| ------------------- | ---------------------------------------------------------------- |
| **Document**        | Requirements Table – Sales                                       |
| **Step in process** | 5 of 6 · Discovery → Requirements                                |
| **Related to**      | PRD-VENTAS-01 · Roles (ROL-V-01 to ROL-V-04) · Permissions Matrix |
| **Department**      | Sales                                                            |
| **Version**         | 1.0                                                              |
| **Status**          | In definition                                                    |

---

## REQUIREMENT TYPES

| Prefix | Type | Description |
|---|---|---|
| **RF** | Functional Requirement | Defines WHAT the system does |
| **RNF** | Non-Functional Requirement | Defines HOW it does it — performance, security, usability |
| **RR** | Business Requirement | Defines WHY it exists — rules, policies |
| **RI** | Integration Requirement | Defines WHAT it connects with |

---

## REQUIREMENTS TABLE

| ID       | Type | Module            | Requirement                                | Detailed Description                                                                    | Role(s)                          | Acceptance Criterion                                        | Priority  | Status      | Notes             |
| -------- | ---- | ----------------- | ------------------------------------------ | -------------------------------------------------------------------------------------- | -------------------------------- | ----------------------------------------------------------- | --------- | ----------- | ----------------- |
| RF-V-01  | RF   | Pipeline          | Identify prospect                          | The BD identifies a hotel in their territory and creates an initial record.            | BD                               | Hotel stays in Gray status with minimal data.               | 🔴 High   | ⬜ Pending  | Gray status       |
| RF-V-02  | RF   | Pipeline          | Create hotel profile                       | The BD collects data: name, email, phone, contact, need. Moves to Light Blue.          | BD                               | Complete profile with required data.                        | 🔴 High   | ⬜ Pending  | Light Blue status |
| RF-V-03  | RF   | Pipeline          | Register cold visit                        | The BD documents their visit to the hotel (date, contact, result).                     | BD                               | Record stays in the prospect's history.                     | 🟡 Medium | ⬜ Pending  | —                 |
| RF-V-04  | RF   | Proposals         | Draft Personalized Proposal                | The BD creates the proposal with services, prices, conditions (RR-V-09).               | BD                               | Proposal stays as a draft.                                  | 🔴 High   | ⬜ Pending  | Green status      |
| RF-V-05  | RF   | Proposals         | Send proposal to hotel                     | The BD attaches and sends the proposal. Moves to Green.                                 | BD                               | Notification to the BD; sending recorded.                   | 🔴 High   | ⬜ Pending  | Green status      |
| RF-V-06  | RF   | Pipeline          | Register contact attempts                  | The BD documents each attempt (call, email, visit) with result.                        | BD                               | Contact history visible in the prospect's detail.           | 🟡 Medium | ⬜ Pending  | —                 |
| RF-V-07  | RF   | Pipeline          | Advance to Yellow (hotel's interest)       | Upon receiving interest, the BD moves the prospect to Yellow.                           | BD                               | Status changes to Yellow with mandatory comment.            | 🔴 High   | ⬜ Pending  | RR-V-11           |
| RF-V-08  | RF   | T&C Documents     | Create T&C Document                        | BD or BDC creates the document with: Pay rate, Bill rate, Overtime, Holidays, Calendar. | BD / BDC                         | Document with required fields completed (RR-V-10).          | 🔴 High   | ⬜ Pending  | Yellow status     |
| RF-V-09  | RF   | Pipeline          | Start negotiation (Pink)                   | BD + BDC start formal negotiation with the hotel.                                       | BD + BDC                         | Status changes to Pink.                                     | 🔴 High   | ⬜ Pending  | —                 |
| RF-V-10  | RF   | T&C Documents     | Validate T&C                               | The BDC reviews the T&C and gives the final yes.                                        | BDC                              | Validation stays in the log with author and date.          | 🔴 High   | ⬜ Pending  | RR-V-15           |
| RF-V-11  | RF   | Conversion        | Create Hotel User                          | Mandatory precondition before approving conversion.                                     | BDC                              | User created with basic data.                               | 🔴 High   | ⬜ Pending  | RR-V-02           |
| RF-V-12  | RF   | Conversion        | Approve conversion to client               | The BDC gives the final yes and approves; fires the Automatic Trigger.                  | BDC                              | Status moves to Orange; Trigger executes 3 actions.         | 🔴 High   | ⬜ Pending  | RR-V-01, RR-V-03  |
| RF-V-13  | RF   | System (cross-cut) | Automatic Conversion Trigger              | 3 parallel actions: welcome email, notify the BD, hotel leaves prospects.              | System                           | The 3 actions execute in <1 min.                            | 🔴 High   | ⬜ Pending  | RR-V-03           |
| RF-V-14  | RF   | System (cross-cut) | Automatic change to Orange                | After the Trigger, the system marks the hotel as active (Orange).                      | System                           | Hotel enabled to generate requisitions.                     | 🔴 High   | ⬜ Pending  | RR-V-08           |
| RF-V-15  | RF   | Pipeline          | Manage rejection (Red)                     | When the hotel rejects, the BD marks it as Red with a reason.                          | BD                               | Status moves to Red with comment.                           | 🟡 Medium | ⬜ Pending  | RR-V-06           |
| RF-V-16  | RF   | Pipeline          | Reactivate prospect from Red               | The BD decides to reactivate and returns it to Light Blue.                              | BD                               | Status returns to Light Blue.                               | 🟡 Medium | ⬜ Pending  | RR-V-07           |
| RF-V-17  | RF   | Pipeline          | Mark stall (Brown)                         | When a prospect stalls, the BD/BDC marks it as Brown.                                   | BD / BDC                         | Status moves to Brown with a reason.                        | 🟡 Medium | ⬜ Pending  | RR-V-04           |
| RF-V-18  | RF   | Pipeline          | Unblock stall (Brown)                       | The BDC investigates and provides a solution to resume.                                 | BDC                              | Action stays in the log.                                    | 🟡 Medium | ⬜ Pending  | RR-V-04           |
| RF-V-19  | RF   | Pipeline          | Reactivate from Brown                      | The BDC reactivates and returns it to Light Blue.                                       | BDC                              | Status returns to Light Blue.                               | 🟡 Medium | ⬜ Pending  | RR-V-07           |
| RF-V-20  | RF   | Pipeline          | Mark Black client (pause/inactive)         | When an active client stops operating, the BDC marks it as Black.                       | BDC                              | Status moves to Black with a reason.                        | 🟡 Medium | ⬜ Pending  | RR-V-05           |
| RF-V-21  | RF   | Pipeline          | Reactivate from Black                      | The BDC reactivates the client.                                                         | BDC                              | Status returns to Light Blue.                               | 🟢 Low    | ⬜ Pending  | RR-V-07           |
| RF-V-22  | RF   | Pipeline          | View Pipeline (all prospects)              | View of prospects by status, with filters.                                             | BD (my territory) / BDC (all)    | Paginated and filterable list.                              | 🔴 High   | ⬜ Pending  | —                 |
| RF-V-23  | RF   | My Territory      | View My Territory (BD)                      | The BD views their assigned routes and zones with prospects by status.                 | BD                               | Map or list by route/zone.                                  | 🔴 High   | ⬜ Pending  | —                 |
| RF-V-24  | RF   | My Team           | View My Team (BDC)                          | The BDC views the BDs in their charge with metrics.                                     | BDC                              | List with individual metrics.                               | 🔴 High   | ⬜ Pending  | BDC exclusive     |
| RF-V-25  | RF   | My Team           | Individual metrics per BD                  | Detail of each BD's performance.                                                       | BDC                              | Coverage, conversion, average time.                         | 🟡 Medium | ⬜ Pending  | —                 |
| RF-V-26  | RF   | Reports           | Generate Sales report                      | Consolidated reports (pipeline, conversion, performance).                              | BDC                              | Exportable CSV/PDF/Excel.                                   | 🟡 Medium | ⬜ Pending  | —                 |
| RF-V-27  | RF   | Reports           | Send report to management                  | Formal sending of the executive report.                                                | BDC                              | Sending history.                                            | 🟡 Medium | ⬜ Pending  | —                 |
| RF-V-28  | RF   | System (cross-cut) | Status change traceability               | Every change is recorded with date, owner and comment.                                 | System                           | Auditable log accessible from the prospect's detail.        | 🔴 High   | ⬜ Pending  | RR-V-11           |
| RF-V-29  | RF   | Active Clients    | View Active Clients (commercial contact)   | Post-Orange view: BD/BDC are contacts, no operation.                                    | BD / BDC                         | List of clients with commercial data.                       | 🟡 Medium | ⬜ Pending  | RR-V-12           |
| RNF-V-01 | RNF  | Global            | Response time                              | Searches and queries do not exceed 2s.                                                  | All                              | Load test.                                                  | 🔴 High   | ⬜ Pending  | —                 |
| RNF-V-02 | RNF  | Global            | Availability                               | 99.5% monthly.                                                                          | All                              | Documented SLA.                                             | 🔴 High   | ⬜ Pending  | —                 |
| RNF-V-03 | RNF  | Security          | Traceability                               | All critical actions in the log.                                                       | All                              | Log with author, date, reason.                              | 🔴 High   | ⬜ Pending  | RR-V-11           |
| RNF-V-04 | RNF  | Usability         | Mobile for BD                              | BD operates from mobile during visits.                                                  | BD                               | Responsive design from 5".                                  | 🔴 High   | ⬜ Pending  | —                 |
| RR-V-01  | RR   | Business          | Conversion exclusive to the BDC            | Only BDC approves conversion.                                                           | System                           | Permission validation.                                      | 🔴 High   | ⬜ Pending  | —                 |
| RR-V-02  | RR   | Business          | Precondition — Hotel User                  | Without a Hotel User, conversion cannot be approved.                                    | System                           | Button block.                                               | 🔴 High   | ⬜ Pending  | —                 |
| RR-V-03  | RR   | Business          | Automatic Trigger executes 3 actions       | Email + Notify + Leave prospects in parallel.                                           | System                           | The 3 execute in <1 min.                                    | 🔴 High   | ⬜ Pending  | —                 |
| RR-V-04  | RR   | Business          | Brown unblock exclusive to the BDC         | Only BDC unblocks.                                                                      | System                           | Permission validation.                                      | 🔴 High   | ⬜ Pending  | —                 |
| RR-V-05  | RR   | Business          | Black client exclusive to the BDC          | Only BDC manages.                                                                       | System                           | Permission validation.                                      | 🔴 High   | ⬜ Pending  | —                 |
| RR-V-07  | RR   | Business          | Reactivations to Light Blue                | They always return to Light Blue.                                                       | System                           | Validation when changing status.                            | 🔴 High   | ⬜ Pending  | —                 |
| RR-V-08  | RR   | Business          | Orange enables requisitions                | The only status that enables the Hotel module.                                         | System                           | Block in Hotel if not Orange.                               | 🔴 High   | ⬜ Pending  | —                 |
| RR-V-10  | RR   | Business          | T&C — mandatory content                    | Pay/Bill/Overtime/Holidays/Calendar.                                                    | System                           | Validation when creating T&C.                               | 🔴 High   | ⬜ Pending  | —                 |
| RR-V-11  | RR   | Business          | Change traceability                        | Everything stays in the log.                                                            | System                           | System-level validation.                                    | 🔴 High   | ⬜ Pending  | —                 |
| RR-V-12  | RR   | Business          | Post-Orange: commercial contacts           | BD/BDC without operation.                                                               | System                           | Permission validation in the Hotel module.                  | 🔴 High   | ⬜ Pending  | —                 |
| RI-V-01  | RI   | Integration       | Sales ↔ Hotel                              | Enablement upon reaching Orange.                                                        | System                           | Documented API.                                             | 🔴 High   | ⬜ Pending  | —                 |
| RI-V-02  | RI   | Integration       | Sales ↔ Recruitment                        | Active client hotel receives Recruiters.                                                | System                           | Automatic notification.                                     | 🔴 High   | ⬜ Pending  | —                 |
| RI-V-03  | RI   | Integration       | Sales ↔ Inspection                         | Inspector assignment upon activation.                                                   | System                           | By hotel zone.                                              | 🔴 High   | ⬜ Pending  | —                 |
| RI-V-04  | RI   | Integration       | Sales ↔ Contract                           | Pink closing generates Contract.                                                        | System                           | Input: validated T&C.                                       | 🔴 High   | ⬜ Pending  | —                 |
| RI-V-05  | RI   | Integration       | Sales ↔ Email                              | Automatic welcome email.                                                                | System                           | Configured template.                                        | 🔴 High   | ⬜ Pending  | —                 |
| RI-V-06  | RI   | Integration       | Sales ↔ QA                                 | Fixed QA operator.                                                                      | System                           | Metrics and Quality Indicator.                              | 🟡 Medium | ⬜ Pending  | —                 |
