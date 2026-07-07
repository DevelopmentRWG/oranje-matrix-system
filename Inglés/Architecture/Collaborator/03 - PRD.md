---
tags:
  - architecture
  - role/collaborator
aliases:
  - Collaborator PRD
---

# PRODUCT REQUIREMENTS DOCUMENT
## PRD — COLLABORATOR

**Staff Management System · Collaborator Role (COL)**

---

| Field                   | Content                                                                                       |
| ----------------------- | --------------------------------------------------------------------------------------------- |
| **PRD ID**              | PRD-COLAB-01                                                                                  |
| **User Story**          | HU-COLAB-01                                                                                   |
| **Department**          | Collaborator / Operations                                                                     |
| **Feature**             | Personal self-service app: sign-up, clock-in, availability, accident report, and data queries |
| **Primary Actor**       | Collaborator (COL)                                                                            |
| **Device**              | Mobile + Web (responsive)                                                                     |
| **Status**              | In definition                                                                                 |
| **Version**             | 1.0                                                                                           |

---

## Objective

Give the Collaborator a **personal self-service mobile app** that allows them to: complete their system sign-up (Phase 2 and Phase 3), register daily attendance via QR clock-in, declare voluntary availability (Yellow), report workplace accidents, and consult their own operational data (schedule, timesheet, pay, notifications, and profile). The collaborator does not manage anyone; they only operate on their own data.

---

## User Story

> As a **Collaborator**, I want to be able to complete my sign-up, clock in and out, view my shifts and weekly pay, and declare my availability, all from my phone, so I don't have to rely on intermediaries to manage my basic operational information.

---

## General Flow

**Download app → Complete Phase 2 (sign-up) → Complete Phase 3 (emergency) → Await Recruiter validation → Become Strong Green → Get assigned → Clock in daily via QR → View schedule and timesheet → When free, activate Yellow if voluntary availability is desired → If accident occurs, report from the app**

---

## Use Cases

| ID | Use Case | Priority |
|---|---|---|
| RF-C-01 | Complete app sign-up (Phase 2) | 🔴 High |
| RF-C-02 | Complete emergency data (Phase 3) | 🔴 High |
| RF-C-03 | Clock in via QR | 🔴 High |
| RF-C-04 | Activate voluntary availability (Yellow) | 🔴 High |
| RF-C-05 | Report workplace accident from the app | 🔴 High |
| RF-C-06 | View My Schedule | 🟡 Medium |
| RF-C-07 | View My Timesheet | 🟡 Medium |
| RF-C-08 | View My weekly Pay | 🟡 Medium |
| RF-C-09 | View notifications | 🟡 Medium |
| RF-C-10 | View My profile and status | 🟡 Medium |

> [!note]
> Detail files for each use case (RF-C-01 to RF-C-10) are available in `Use Cases/`.

---

## Applicable Business Rules

### New rules — specific to the self-service app

| ID | Rule |
|---|---|
| RR-C-01 | The Collaborator can only view and edit THEIR OWN data. No access to other collaborators' data. |
| RR-C-02 | Yellow (voluntary availability) is the only state transition the Collaborator activates on their own, without anyone's approval. |
| RR-C-03 | The Collaborator cannot clock in without an active Timesheet, which requires being enrolled in the Schedule with an active assignment (fixed or temporary). |
| RR-C-04 | The Collaborator accesses the platform from **mobile and web (responsive)**. Onboarding (Phase 2 and 3) and read-only views (My Schedule, My Timesheet, My Pay, Notifications, My Profile) and availability activation (Yellow) are available on both channels. QR clock-in (RF-C-03) is a native mobile action (scanning the physical QR at the hotel with the phone camera). |
| RR-C-05 | The Collaborator can view the **history of their already-received payments** (week, hotel(s), hours, amount paid, and payment date). **They cannot see the amount of their current or upcoming payment**: pay calculation is exclusive to Accounting and is only revealed to the Collaborator once the payment has been released. The full [[Collaborator Weekly Summary]] (internal rate, deductions, billing) remains exclusive to Accounting. See [[RF-C-08 View My Pay]]. |

### Referenced existing rules

For detailed business rules on clock-in, lunch deduction, 3 absences → Blacklist, Gray protection for accidents, and weekly pay, see: [[Collaborator Rules]]

---

## Restrictions / Permissions

- CANNOT accept or reject assignments.
- CANNOT request reassignment directly.
- CANNOT authorize any system action.
- CANNOT assign anyone or manage other collaborators.
- CANNOT edit the Schedule (read-only).
- CANNOT correct punches (exclusive to the Area Manager).
- CANNOT view other collaborators' data (RR-C-01).
- CANNOT access management modules (requisitions, pool, accounting, QA).
- QR clock-in (RF-C-03) is exclusive to mobile; on web the collaborator can view all information but cannot execute the clock-in (RR-C-04).
