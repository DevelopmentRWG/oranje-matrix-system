---
tags:
  - arquitectura
  - departamento/ventas
aliases:
  - Sales Requirements By Module
---

# REQUIREMENTS BY MODULE — SALES DEPARTMENT

Grouping of the RFs defined in [[03 - Requirements Table|03 - Requirements Table]] according to the sidebar module they belong to.

---

## 📊 Dashboard

Entry view of the role. Concentrates personal KPIs (of the BD) or consolidated territory KPIs (of the BDC) and upcoming follow-ups. Has no RFs of its own — the KPIs come from other modules.

| ID  | Requirement                                | Role(s) | Priority  |
| --- | ------------------------------------------ | ------- | --------- |
| —   | Personal KPIs (BD: my territory)           | BD      | 🔴 High   |
| —   | Team KPIs and conversion funnel (BDC)      | BDC     | 🔴 High   |

---

## 📋 Pipeline (Prospects)

Operations center of the department. Manages all prospects along the Onboarding Status Light (Gray → Light Blue → Green → Yellow → Pink → Orange, plus the Red, Brown and Black branches). Includes the full cycle of advancement, rejection, stalling and reactivation.

| ID      | Requirement                      | Role(s)  | Priority  |
| ------- | -------------------------------- | -------- | --------- |
| RF-V-01 | Identify prospect                | BD       | 🔴 High   |
| RF-V-02 | Create hotel profile             | BD       | 🔴 High   |
| RF-V-03 | Register cold visit              | BD       | 🟡 Medium |
| RF-V-06 | Register contact attempts        | BD       | 🟡 Medium |
| RF-V-07 | Advance to Yellow (interest)     | BD       | 🔴 High   |
| RF-V-09 | Start negotiation (Pink)         | BD + BDC | 🔴 High   |
| RF-V-15 | Manage rejection (Red)           | BD       | 🟡 Medium |
| RF-V-16 | Reactivate prospect from Red     | BD       | 🟡 Medium |
| RF-V-17 | Mark stall (Brown)               | BD / BDC | 🟡 Medium |
| RF-V-18 | Unblock stall (Brown)            | BDC      | 🟡 Medium |
| RF-V-19 | Reactivate from Brown            | BDC      | 🟡 Medium |
| RF-V-20 | Mark Black client                | BDC      | 🟡 Medium |
| RF-V-21 | Reactivate from Black            | BDC      | 🟢 Low    |
| RF-V-22 | View Pipeline                    | BD / BDC | 🔴 High   |

---

## 📝 Proposals

Construction and sending of the Personalized Proposal to the hotel. It is drafted exclusively in Green status (RR-V-09). Includes templates, duplication and formal sending by email.

| ID      | Requirement                      | Role(s) | Priority  |
| ------- | -------------------------------- | ------- | --------- |
| RF-V-04 | Draft Personalized Proposal      | BD      | 🔴 High   |
| RF-V-05 | Send proposal to hotel           | BD      | 🔴 High   |

---

## 📄 T&C Documents

Creation of the Terms and Conditions Document with the 5 mandatory fields (Pay rate, Bill rate, Overtime, Holidays, Calendar — RR-V-10) and final validation by the BDC. Prerequisite to start Pink.

| ID      | Requirement            | Role(s)  | Priority  |
| ------- | ---------------------- | -------- | --------- |
| RF-V-08 | Create T&C Document    | BD / BDC | 🔴 High   |
| RF-V-10 | Validate T&C           | BDC      | 🔴 High   |

---

## ✅ Conversion *(BDC exclusive)*

Closing of the onboarding. The BDC creates the Hotel User (mandatory precondition — RR-V-02) and approves the conversion, which fires the Automatic Trigger and leaves the hotel as an active client (Orange).

| ID      | Requirement                  | Role(s) | Priority  |
| ------- | ---------------------------- | ------- | --------- |
| RF-V-11 | Create Hotel User            | BDC     | 🔴 High   |
| RF-V-12 | Approve conversion to client | BDC     | 🔴 High   |

---

## 🗺️ My Territory *(BD exclusive)*

Interactive map of the routes and zones assigned to the BD, with prospect pins by status. Allows planning the day's route, identifying new prospects in the field (with automatic geolocation from mobile) and opening the detail of any prospect from the map.

| ID      | Requirement       | Role(s) | Priority  |
| ------- | ----------------- | ------- | --------- |
| RF-V-23 | View My Territory | BD      | 🔴 High   |

---

## 👥 My Team *(BDC exclusive)*

Supervision of the BDs in the BDC's charge. Includes a list of BDs with metrics, individual performance detail and internal communication. Entry point to reassign prospects or request specific reports.

| ID      | Requirement                  | Role(s) | Priority  |
| ------- | ---------------------------- | ------- | --------- |
| RF-V-24 | View My Team (BDs in charge) | BDC     | 🔴 High   |
| RF-V-25 | Individual metrics per BD    | BDC     | 🟡 Medium |

---

## 📈 Reports *(BDC exclusive)*

Consolidated territory reports (Pipeline, Conversion, Performance, Brown, Black, Quality, Executive) with preview, CSV/PDF/Excel export and recurring sending to management.

| ID      | Requirement                | Role(s) | Priority  |
| ------- | -------------------------- | ------- | --------- |
| RF-V-26 | Generate Sales report      | BDC     | 🟡 Medium |
| RF-V-27 | Send report to management  | BDC     | 🟡 Medium |

---

## 🏨 Active Clients

Post-Orange view of the hotel. BD and BDC remain as commercial contacts (no operation — RR-V-12). Also includes the management of the Black status (paused client) which is exclusive to the BDC.

| ID      | Requirement                                | Role(s)  | Priority  |
| ------- | ------------------------------------------ | -------- | --------- |
| RF-V-29 | View Active Clients (commercial contact)   | BD / BDC | 🟡 Medium |

---

## ⚙️ System (cross-cutting — NOT a sidebar module)

Internal automations that the user does not see directly but that happen behind the flow: the Automatic Conversion Trigger, the status change to Orange, change traceability and notifications.

| ID      | Requirement                       | Role(s) | Priority  |
| ------- | --------------------------------- | ------- | --------- |
| RF-V-13 | Automatic Conversion Trigger      | System  | 🔴 High   |
| RF-V-14 | Automatic change to Orange        | System  | 🔴 High   |
| RF-V-28 | Status change traceability        | System  | 🔴 High   |
| —       | Automatic notifications           | System  | 🔴 High   |

---

## 🛠️ Configuration *(Admin exclusive — ON HOLD)*

> [!warning] Admin on hold
> These requirements remain documented but **are not implemented** in this scope. They will be resumed at the end once the system's business rules are stable.

| ID  | Requirement                          | Role(s)       | Priority          |
| --- | ------------------------------------ | ------------- | ----------------- |
| —   | CRUD of Sales department users       | Administrator | ⏸️ Admin on hold  |
| —   | Edit catalogs (zones, templates)     | Administrator | ⏸️ Admin on hold  |

---

## ⚙️ Non-Functional (Cross-cutting)

| ID       | Requirement                  | Priority  |
| -------- | ---------------------------- | --------- |
| RNF-V-01 | Response time < 2s           | 🔴 High   |
| RNF-V-02 | Availability 99.5%           | 🔴 High   |
| RNF-V-03 | Action traceability          | 🔴 High   |
| RNF-V-04 | Mobile-first for BD          | 🔴 High   |

---

## 📜 Business Rules (summary)

| ID      | Rule                                           | Priority  |
| ------- | ---------------------------------------------- | --------- |
| RR-V-01 | Conversion exclusive to the BDC                | 🔴 High   |
| RR-V-02 | Precondition — Hotel User                      | 🔴 High   |
| RR-V-03 | Automatic Trigger executes 3 actions           | 🔴 High   |
| RR-V-04 | Brown unblock exclusive to the BDC             | 🔴 High   |
| RR-V-05 | Black client exclusive to the BDC              | 🔴 High   |
| RR-V-06 | Rejection (Red) management by the BD           | 🔴 High   |
| RR-V-07 | Reactivations always to Light Blue             | 🔴 High   |
| RR-V-08 | Orange enables requisition generation          | 🔴 High   |
| RR-V-09 | Personalized Proposal only in Green            | 🔴 High   |
| RR-V-10 | T&C — mandatory content (5 fields)             | 🔴 High   |
| RR-V-11 | Status change traceability                     | 🔴 High   |
| RR-V-12 | Post-Orange: commercial contacts               | 🔴 High   |
| RR-V-15 | Contract results from a successful Pink closing | 🔴 High   |

> [!info]
> See the full detail of each rule in [[07 - Business Rules|07 - Business Rules]].

---

## 🔗 Integrations

| ID      | Requirement                            | Priority  |
| ------- | -------------------------------------- | --------- |
| RI-V-01 | Sales ↔ Hotel                          | 🔴 High   |
| RI-V-02 | Sales ↔ Recruitment                    | 🔴 High   |
| RI-V-03 | Sales ↔ Inspection                     | 🔴 High   |
| RI-V-04 | Sales ↔ Contract                       | 🔴 High   |
| RI-V-05 | Sales ↔ Email (welcome Trigger)        | 🔴 High   |
| RI-V-06 | Sales ↔ QA                             | 🟡 Medium |
