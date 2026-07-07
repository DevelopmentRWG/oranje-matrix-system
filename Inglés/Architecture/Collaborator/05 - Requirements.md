---
tags:
  - architecture
  - role/collaborator
aliases:
  - Collaborator Requirements
---

# REQUIREMENTS BY ROLE

## 👷 ROL-C-01 · Collaborator (COL)

---

## Functional Requirements

| ID      | Requirement                                              | Priority  |
| ------- | -------------------------------------------------------- | --------- |
| RF-C-01 | Complete app sign-up — Phase 2                           | 🔴 High   |
| RF-C-02 | Complete emergency data — Phase 3                        | 🔴 High   |
| RF-C-03 | Clock in via QR (6 punch types)                          | 🔴 High   |
| RF-C-04 | Activate voluntary availability — Yellow                 | 🔴 High   |
| RF-C-05 | Report workplace accident from the app                   | 🔴 High   |
| RF-C-06 | View My Schedule                                         | 🟡 Medium |
| RF-C-07 | View My Timesheet                                        | 🟡 Medium |
| RF-C-08 | View My weekly Pay                                       | 🟡 Medium |
| RF-C-09 | View notifications                                       | 🟡 Medium |
| RF-C-10 | View My profile and status light state                   | 🟡 Medium |

---

## Non-Functional Requirements

| ID       | Requirement                                                                                                                                                                                                                  | Priority  |
| -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| RNF-C-01 | **Responsive, web and mobile:** the platform must work on mobile (Android and iOS) and in a web browser; designed with a mobile-first approach but adapted for desktop. QR clock-in (RF-C-03) is a mobile-only feature (requires device camera). | 🔴 High |
| RNF-C-02 | **Offline-tolerant for clock-in:** QR scanning and punch registration must tolerate temporary connectivity loss, queuing the record locally and syncing when signal is restored | 🔴 High |
| RNF-C-03 | **Sensitive data security:** SSN/ITIN must be stored encrypted; must not be displayed in plain text in the interface (mask after Phase 2 validation) | 🔴 High |
| RNF-C-04 | **99.5% availability** especially during the shift start/end time window (QR clock-in) | 🔴 High |
| RNF-C-05 | **Simplified UX:** the app must be usable by collaborators with a basic level of tech proficiency; clear text, recognizable icons, flows of maximum 3 steps | 🔴 High |
| RNF-C-06 | **Push notifications:** the system must send push notifications to the collaborator on status light changes, new assignment, sign-up validation approved/rejected | 🟡 Medium |
| RNF-C-07 | **Multilingual support:** Spanish as the primary language; English as secondary for collaborators who prefer it | 🟢 Low   |
| RNF-C-08 | **Camera compatibility:** the QR scanning feature must work with the device's native camera, without requiring an external app | 🔴 High |

---

## Business Rules

| ID      | Rule                                                                                                                                                                                | Priority  |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| RR-C-01 | The Collaborator can only view and edit THEIR OWN data — no other collaborator's data is visible                                                                                    | 🔴 High   |
| RR-C-02 | Yellow is the only state transition the Collaborator activates on their own, without approval                                                                                       | 🔴 High   |
| RR-C-03 | The Collaborator cannot clock in without an active Timesheet (requires Schedule + active assignment)                                                                                | 🔴 High   |
| RR-C-04 | The Collaborator accesses the platform from **mobile and web (responsive)**. Onboarding (Phase 2 and 3) and read-only views (My Schedule, My Timesheet, My Pay, Notifications, My Profile) and availability activation (Yellow) are available on both channels. QR clock-in (RF-C-03) is a native mobile action (scanning the physical QR at the hotel with the phone camera). | 🔴 High   |
| RR-C-05 | The Collaborator can view the **history of their already-received payments** (week, hotel(s), hours, amount paid, and payment date). **They cannot see the amount of their current or upcoming payment**: pay calculation is exclusive to Accounting and is only revealed to the Collaborator once the payment has been released. The full Weekly Consolidated (internal rate, deductions, billing) remains exclusive to Accounting. See [[RF-C-08 View My Pay]]. | 🟡 Medium |

> [!info]
> Rules on lunch deduction, 3 absences → Blacklist, Gray protection for workplace accidents, and weekly pay calculation are defined in [[Collaborator Rules]] and are not redefined here.
