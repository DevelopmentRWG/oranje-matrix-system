---
tags:
  - architecture
  - role/collaborator
aliases:
  - Collaborator Feature Map
---

# FEATURE MAP — COLLABORATOR

---

## Feature Map (Primary / Secondary)

```
COLLABORATOR PLATFORM — MOBILE + WEB (COL)
│
├── PRIMARY
│   │
│   ├── Onboarding
│   │   ├── Phase 2 — App sign-up
│   │   │   ├── SSN / ITIN (optional; without both → 16% refundable retention notice, see Deductions)
│   │   │   ├── SSN/ITIN Document (attachment — JPG/PNG/PDF, optional · recommended if SSN/ITIN provided)
│   │   │   ├── Position (catalog)
│   │   │   ├── English level (catalog)
│   │   │   ├── Experience level
│   │   │   ├── Transportation type
│   │   │   └── Hiring modality (catalog)
│   │   └── Phase 3 — Emergency data
│   │       ├── Emergency contact (name, phone, relationship)
│   │       ├── Blood type
│   │       └── Allergies or medical conditions
│   │
│   ├── Attendance / QR Clock-in
│   │   ├── Scan QR (device camera)
│   │   ├── Punch — Clock-in (start of shift)
│   │   ├── Punch — Lunch Out
│   │   ├── Punch — Lunch In (return from lunch)
│   │   ├── Punch — Break Out
│   │   ├── Punch — Break In (return from break)
│   │   └── Punch — Clock-out (end of shift)
│   │
│   ├── Availability
│   │   ├── Toggle — Activate Yellow (voluntarily available)
│   │   └── Toggle — Deactivate Yellow
│   │
│   └── Report Accident
│       ├── Create accident card (Scenario A — collaborator reports first)
│       │   ├── Date and time of incident
│       │   ├── Accident description
│       │   └── Photos / evidence (optional)
│       └── View my reported accidents (own history)
│
└── SECONDARY
    │
    ├── Dashboard
    │   ├── My current status (status light color + name)
    │   └── Next shift (date, time, hotel — if assigned)
    │
    ├── My Schedule
    │   ├── Weekly view of my assigned shifts
    │   ├── Current and next week (if applicable)
    │   └── Shift detail (hotel, position, schedule)
    │
    ├── My Timesheet
    │   ├── Weekly punch table (6 columns)
    │   ├── Gross hours per shift
    │   ├── Lunch deduction per shift
    │   ├── Net hours per shift
    │   └── Total net hours for the week
    │
    ├── My Pay
    │   ├── Released payment history (week · hotel · hours · amount · date)
    │   ├── Current week → "In calculation" (no amount)
    │   └── Upcoming payment NOT visible (RR-C-05)
    │
    ├── Notifications
    │   ├── Sign-up validated (Recruiter approved → Strong Green)
    │   ├── Sign-up pending correction
    │   ├── New assignment received (→ Café state)
    │   ├── Temporary assignment ended
    │   ├── Status light change
    │   └── Update on accident card
    │
    └── My Profile
        ├── Phase 1 data (name, age, gender, address, phone — editable with limits)
        ├── Phase 2 data (SSN/ITIN masked, position, English, experience, transportation, modality; SSN/ITIN document stored)
        ├── Phase 3 data (emergency contact, blood type, allergies — editable)
        ├── Current status light state (color + name)
        └── Settings (change password, notification preferences)
```

---

## Collaborator Features

| Feature | Allowed |
|---|---|
| Complete Phase 2 sign-up | ✅ onboarding action |
| Complete Phase 3 emergency data | ✅ onboarding action |
| Clock in via QR (6 punches) | ✅ primary daily action |
| Activate voluntary availability (Yellow) | ✅ only autonomous state-change action |
| Report accident (Scenario A) | ✅ |
| View My Schedule | ✅ (read-only) |
| View My Timesheet | ✅ (read-only) |
| View My weekly Pay | ✅ (read-only) |
| View notifications | ✅ (read-only) |
| View My Profile and status light state | ✅ (read-only + limited edit) |
| Edit Schedule | ❌ (exclusive to the Area Manager — RR-C-01) |
| Correct own punch | ❌ (exclusive to the Area Manager) |
| Generate QR | ❌ (exclusive to the Area Manager / General Manager) |
| View other collaborators' data | ❌ (RR-C-01) |
| Accept / reject assignments | ❌ (passive model) |
| Request reassignment directly | ❌ (passive model) |
| Clock in via QR from web | ❌ — mobile only (RR-C-04); requires device camera |
| View Extended Lunch Indicator | ❌ (exclusive to Inspection and Recruitment) |
