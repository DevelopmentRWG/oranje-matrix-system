---
tags:
  - arquitectura
  - departamento/reclutamiento
aliases:
  - Recruitment By Module
---

# REQUIREMENTS GROUPED BY MODULE

---

## 📊 Dashboard

| ID  | Requirement                                                            | Priority | Status |
| --- | ------------------------------------------------------------------------ | --------- | ------ |
| —   | (KPIs and summary views — no RFs of their own; all come from other modules) | —         | —      |

---

## 🧑‍🤝‍🧑 Recruitment

Includes Collaborator Pool, creation/interview of new collaborators, validation, assignment and management of the hotel's Schedule.

| ID    | Requirement                           | Priority | Status      |
| ----- | --------------------------------------- | --------- | ----------- |
| RF-06 | Search candidates in Pool               | 🔴 High   | ⬜ Pending |
| RF-07 | Create collaborator (Phase 1 — Interview) | 🔴 High   | ⬜ Pending |
| RF-08 | Validate app registration (Phase 2)            | 🔴 High   | ⬜ Pending |
| RF-09 | Enable access                       | 🟡 Medium  | ⬜ Pending |
| RF-10 | Register interview                    | 🟡 Medium  | ⬜ Pending |
| RF-15 | Assign collaborator to hotel             | 🔴 High   | ⬜ Pending |
| RF-16 | Assign to Schedule                     | 🔴 High   | ⬜ Pending |
| RF-17 | Reassign collaborator                   | 🟡 Medium  | ⬜ Pending |
| RF-18 | Unassign collaborator                  | 🟡 Medium  | ⬜ Pending |

---

## 📋 Requisition

Includes reception, free take (Self-Pick), management of the requisition status and the associated status lights (Urgency, Positions).

| ID    | Requirement                    | Priority | Status      |
| ----- | -------------------------------- | --------- | ----------- |
| RF-01 | Receive incoming requisition     | 🔴 High   | ⬜ Pending |
| RF-02 | Take requisition (Self-Pick)    | 🔴 High   | ⬜ Pending |
| RF-03 | Release requisition              | 🟡 Medium  | ⬜ Pending |
| RF-04 | Mark requisition in progress    | 🔴 High   | ⬜ Pending |
| RF-05 | Mark requisition as covered | 🔴 High   | ⬜ Pending |
| RF-19 | Calculate Urgency Status Light    | 🔴 High   | ⬜ Pending |
| RF-20 | Calculate Positions Status Light  | 🔴 High   | ⬜ Pending |
| RF-21 | Force status light change        | 🟢 Low   | ⬜ Pending |
| RF-39 | Take / Join an already-taken requisition (collaborative) | 🔴 High   | ⬜ Pending |
| RF-40 | View active recruiters of the requisition | 🟡 Medium  | ⬜ Pending |
| RF-41 | View Requisition History  | 🔴 High   | ⬜ Pending |

---

## ⚫ Blacklist

| ID    | Requirement                                   | Priority | Status      |
| ----- | ----------------------------------------------- | --------- | ----------- |
| RF-11 | Check Blacklist                             | 🔴 High   | ⬜ Pending |
| RF-12 | Add to Blacklist (all dept roles) | 🔴 High   | ⬜ Pending |
| RF-13 | Resolve Blacklist dispute (Manager)         | 🟡 Medium  | ⬜ Pending |
| RF-14 | Remove from Blacklist (Manager)                  | 🟢 Low   | ⬜ Pending |

---

## 👥 My Group *(Leader exclusive)*

| ID    | Requirement                         | Priority | Status      |
| ----- | ------------------------------------- | --------- | ----------- |
| RF-22 | View group Recruiters            | 🔴 High   | ⬜ Pending |
| RF-23 | Individual metrics per Recruiter | 🟡 Medium  | ⬜ Pending |

---

## 📈 Reports *(Leader and Manager)*

| ID    | Requirement             | Priority | Status      |
| ----- | ------------------------- | --------- | ----------- |
| RF-24 | Generate group report | 🟡 Medium  | ⬜ Pending |
| RF-25 | Send report to the Manager | 🟡 Medium  | ⬜ Pending |
| RF-26 | View individual coverage  | 🟢 Low   | ⬜ Pending |
| RF-27 | View coverage by zone    | 🟡 Medium  | ⬜ Pending |
| RF-28 | View global coverage      | 🟡 Medium  | ⬜ Pending |

---

## 👨‍💼 My Team *(Manager exclusive)*

| ID    | Requirement                     | Priority | Status      |
| ----- | --------------------------------- | --------- | ----------- |
| RF-29 | Management of Leaders and Recruiters | 🔴 High   | ⬜ Pending |

---

## ⚠️ Incidents *(Manager exclusive)*

| ID    | Requirement       | Priority | Status      |
| ----- | ------------------- | --------- | ----------- |
| RF-30 | Resolve incident | 🟡 Medium  | ⬜ Pending |
| RF-31 | Escalate to commercial | 🟡 Medium  | ⬜ Pending |

---

## ⚙️ System (cross-cutting — NOT a sidebar module)

| ID    | Requirement                     | Priority | Status      |
| ----- | --------------------------------- | --------- | ----------- |
| RF-32 | Send automatic notifications | 🔴 High   | ⬜ Pending |

---

## 🛠️ Configuration *(Admin exclusive — PAUSED)*

> [!warning] Admin paused
> These requirements remain documented but are **not landed** in this scope. They are picked up again at the end when the business rules are stable.

| ID | Requirement | Priority | Status |
|---|---|---|---|
| RF-33 | Configure alerts | 🟢 Low | ⏸️ Admin paused |
| RF-34 | User CRUD | 🔴 High | ⏸️ Admin paused |
| RF-35 | Edit catalogs | 🟡 Medium | ⏸️ Admin paused |

---

## ⚙️ Non-Functional (Cross-cutting)

| ID     | Requirement                    | Priority | Status      |
| ------ | -------------------------------- | --------- | ----------- |
| RNF-01 | Response time < 2s         | 🔴 High   | ⬜ Pending |
| RNF-02 | Availability 99.5%             | 🔴 High   | ⬜ Pending |
| RNF-03 | Encryption of sensitive data       | 🔴 High   | ⬜ Pending |
| RNF-04 | Multi-device compatibility | 🟡 Medium  | ⬜ Pending |

---

## 📜 Business Rules

| ID    | Requirement                                 | Priority | Status      |
| ----- | --------------------------------------------- | --------- | ----------- |
| RR-01 | Collaborative Self-Pick model                 | 🔴 High   | ⬜ Pending |
| RR-02 | Mandatory Blacklist check             | 🔴 High   | ⬜ Pending |
| RR-03 | Manager resolves disputes and removes from Blacklist | 🔴 High   | ⬜ Pending |
| RR-04 | 100% coverage for closure                    | 🔴 High   | ⬜ Pending |
| RR-15 | Collaborative requisition model            | 🔴 High   | ⬜ Pending |
| RR-16 | Requisition history / traceability    | 🔴 High   | ⬜ Pending |

---

## 🔗 Integrations

| ID    | Requirement                       | Priority | Status      |
| ----- | ----------------------------------- | --------- | ----------- |
| RI-01 | Integration with the Hotel module        | 🔴 High   | ⬜ Pending |
| RI-02 | Integration with Schedule            | 🔴 High   | ⬜ Pending |
| RI-03 | Integration with Timesheet           | 🟡 Medium  | ⬜ Pending |
| RI-04 | Integration with the collaborator's app | 🔴 High   | ⬜ Pending |
| RI-05 | Integration with Onboarding-Hotel    | 🟡 Medium  | ⬜ Pending |
