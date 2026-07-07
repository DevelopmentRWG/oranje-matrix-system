---
tags:
  - architecture
  - role/collaborator
aliases:
  - Collaborator Quick Summary
---

# QUICK SUMMARY — COLLABORATOR

---

| Field                    | Content                                                                                                           |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| **Role**                 | 👷 Collaborator (COL)                                                                                             |
| **Objective**            | Personal self-service: sign-up, QR clock-in, availability, accident report, and own data queries                  |
| **Model**                | Passive — subject of the system. The only state-change action they execute is activating Yellow                   |
| **Key Permissions**      | View (own only) · Create (sign-up, punches, accident, Yellow) · Limited edit (profile/emergency data)             |
| **Device**               | Mobile + Web (responsive) — QR clock-in exclusive to mobile                                                       |
| **Main Actions**         | Complete sign-up (Phase 2 + 3) · Clock in QR · Activate Yellow · Report accident · View schedule, timesheet, pay |
| **Level**                | 🟢 Low (own data only)                                                                                            |
| **Key Rules**            | RR-C-01 (own only) · RR-C-02 (only Yellow is autonomous) · RR-C-03 (clock-in requires active Timesheet) · RR-C-04 (mobile + web; QR clock-in exclusive to mobile) |

---

## What the Collaborator DOES

- Completes their own sign-up in the app (Phase 2 and Phase 3).
- Clocks in and out daily via QR (6 punches).
- Activates voluntary availability (Yellow) — their only autonomous state-change action.
- Reports workplace accidents when they are the first to detect them (Scenario A).
- Views their schedule, timesheet, pay, notifications, and profile (all in read-only mode).

## What the Collaborator does NOT do

- Does not accept or reject assignments.
- Does not edit the Schedule or correct punches.
- Does not see any other collaborator's data.
- Does not authorize, assign, or manage.
- Cannot clock in via web (QR clock-in requires the phone camera).

---

## Domain Sources

- [[Collaborator]] — entity and data in 3 phases
- [[Collaborator Rules]] — clock-in, lunch, pay, absences, accident, pool
- [[Collaborator Status Light]] — 12 states and transitions
