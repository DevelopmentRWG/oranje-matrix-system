---
tags:
  - architecture
  - role/collaborator
aliases:
  - Collaborator Architecture
  - Collaborator Wireframe
  - COL Architecture
---

# Architecture — Collaborator

Wireframe of the Oranje app for the [[Collaborator]] role. Defines the onboarding flow, the structure of the mobile app, and the detail of each feature the collaborator has access to as a **personal self-service user**.

> [!info]
> The Collaborator is the **passive subject** of the system. Their only autonomous state-change action is activating voluntary availability (Yellow). All other state transitions are executed by other roles. They access exclusively THEIR OWN data — never data from other collaborators or management tools.

> [!important]
> The Collaborator accesses the platform from **mobile and web (responsive)** (RR-C-04). Onboarding, read-only views, and availability activation are available on both channels. QR clock-in (RF-C-03) is a native mobile action: it requires scanning the hotel's physical QR code with the phone camera.

---

## N0 — Entry

```
ORANJE APP (MOBILE)
        │
        ▼
LOGIN / AUTHENTICATION
        │
        ▼
ROLE IDENTIFIED / COLLABORATOR
        │
        ▼
PERSONAL DASHBOARD
```

---

## N1 — Collaborator App Structure

```
COLLABORATOR PLATFORM — MOBILE + WEB (COL)
   │
   ├─ DASHBOARD (my status, next shift)
   ├─ MY SCHEDULE       (read-only)
   ├─ ATTENDANCE        (scan QR — clock in)
   ├─ MY TIMESHEET      (net hours — read-only)
   ├─ MY PAY            (weekly consolidated — read-only)
   ├─ AVAILABILITY      (activate Yellow)
   ├─ REPORT ACCIDENT
   ├─ NOTIFICATIONS
   └─ MY PROFILE        (own data + status light status)
```

---

## Documents for this Role

| File | Description |
|---|---|
| [[01 - Role Sheet]] | Summary table: ID, name, type, key permissions, device |
| [[02 - Detailed Sheet]] | Full responsibilities, what the collaborator CAN and CANNOT do |
| [[03 - PRD]] | PRD-COLAB-01 · Use cases RF-C-01 to RF-C-10 |
| [[04 - Detailed Permissions]] | CRUD matrix by module |
| [[05 - Requirements]] | Functional and non-functional requirements |
| [[06 - Quick Summary]] | One-page executive summary |
| [[07 - Feature Map]] | ASCII tree of the Collaborator app |
| [[08 - User Actions]] | Action → Result table |
| [[09 - Form Fields]] | Fields for Phase 2, Phase 3, accident report, and availability |
| [[10 - Validations]] | Validation rules per form |
| [[11 - System Responses]] | System messages and notifications |
| [[12 - Mockup and UI Decisions]] | Interactive web mockup and UI design decisions |

---

## Domain Concept Sources

- [[Collaborator]] — entity, data in 3 phases, interacting roles
- [[Collaborator Rules]] — status light, QR clock-in, lunch, absences, pay, accident, pool
- [[Collaborator Status Light]] — 12 states and full transitions

---

## Related

- [[Collaborator]]
- [[Collaborator Rules]]
- [[Collaborator Status Light]]
- [[Schedule]]
- [[Timesheet]]
- [[Collaborator Weekly Summary]]
- [[Workplace Accident]]
- [[Collaborator Pool]]
- [[12 - Mockup and UI Decisions]]
- [[Design Conventions]]
