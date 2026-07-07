---
tags:
  - arquitectura
  - rol/lider-de-grupo
aliases:
  - Feature Map Group Leader
---

# FEATURE MAP — RECRUITERS GROUP LEADER

---

## Feature map (Primary / Secondary)

```
RECRUITMENT — RECRUITERS GROUP LEADER
│
├── PRIMARY
│   │
│   ├── Requisition (Self-Pick + Status Lights)
│   │   ├── Authorized queue
│   │   ├── My Requisitions (taken)
│   │   ├── Take requisition
│   │   ├── Mark covered / partial
│   │   ├── Leave the requisition
│   │   ├── Urgency Status Light (read)
│   │   └── Positions Status Light (read)
│   │
│   ├── Recruitment (Pool + Create + Assignment)
│   │   ├── Collaborator Pool (list, filters, detail)
│   │   ├── Create collaborator (Phase 1)
│   │   ├── Validate App sign-up (Phase 2)
│   │   ├── Enable access
│   │   ├── Register interview
│   │   ├── Assign collaborator to hotel
│   │   ├── Assign to Schedule
│   │   ├── Reassign / Unassign
│   │   └── Handle 1st-level incident (escalates to Manager if exceeded)
│   │
│   ├── Blacklist
│   │   ├── Check banned list
│   │   └── Add to Blacklist (with reason and evidence)
│   │
│   └── My Group (Leader EXCLUSIVE)
│       ├── List of group Recruiters
│       ├── Detail per Recruiter
│       ├── Individual metrics
│       ├── Current workload per person
│       ├── Reassign requisition to another Recruiter
│       └── Mark availability (vacation / return)
│
└── SECONDARY
    │
    ├── Analytics
    │   ├── Dashboard — Personal KPIs (as Recruiter)
    │   ├── Dashboard — Group KPIs (Leader extra)
    │   ├── Dashboard — Pool by position
    │   ├── Dashboard — My Requisitions
    │   ├── Dashboard — Authorized queue (short view)
    │   └── Reports — Preview with metrics (coverage, performance, escalated cases)
    │
    └── Utilities
        ├── Dashboard — Quick actions
        ├── Reports — Generate group report (Leader EXCLUSIVE)
        ├── Reports — Filters (zone, date, position)
        ├── Reports — Send to Manager
        └── Reports — Export (CSV / PDF)
```

---

## Features — comparison with other roles

| Feature | Recruiter | Leader | Manager |
|---|---|---|---|
| Take requisitions (Self-Pick) | ✅ | ✅ | ⚠️ exceptional |
| Create collaborators | ✅ | ✅ | ✅ |
| Add to Blacklist | ✅ | ✅ | ✅ |
| Resolve Blacklist dispute (Inspector) | ❌ | ❌ | ❌ |
| My Group | ❌ | ✅ exclusive | ❌ |
| Formal reports | ❌ | ✅ sends to Manager | ✅ receives + generates |
| My Team (user management) | ❌ | ❌ | ✅ exclusive |
