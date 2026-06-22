---
tags:
  - arquitectura
  - rol/reclutadora
aliases:
  - Recruiter Feature Map
---

# FEATURE MAP — RECRUITER

---

## Feature map by module

```
RECRUITER
├── 📊 Dashboard
│   ├── Personal KPIs
│   ├── Pool by position (summary)
│   ├── My Requisitions (summary)
│   ├── Authorized Queue (short view)
│   └── Quick actions
│
├── 📋 Requisition (Self-Pick + Status Lights)
│   ├── Authorized Queue (all available)
│   ├── My Requisitions (taken)
│   ├── Take requisition
│   ├── Mark as covered / partial
│   ├── Release requisition
│   ├── Urgency Status Light (read)
│   └── Positions Status Light (read)
│
├── 🧑‍🤝‍🧑 Recruitment (Pool + Create + Assignment)
│   ├── Collaborator Pool (list, filters, detail)
│   ├── Create collaborator (Phase 1 — Interview)
│   ├── Validate sign-up in App (Phase 2)
│   ├── Enable access
│   ├── Register interview
│   ├── Assign collaborator to hotel
│   ├── Assign to Schedule
│   ├── Reassign collaborator
│   └── Unassign collaborator
│
└── ⚫ Blacklist
    ├── Banned lookup
    └── Add to Blacklist (with reason and evidence)
```

---

## Recruiter features

| Feature | Allowed |
|---|---|
| Take requisitions freely (Self-Pick) | ✅ |
| Create collaborators (Phase 1) | ✅ |
| Validate sign-up in App | ✅ |
| Assign to Schedule | ✅ |
| Add collaborator to Blacklist | ✅ (with reason and evidence) |
| Distribute requisitions to others | ❌ (Self-Pick model does not apply) |
| Resolve disputes / Remove from Blacklist | ❌ (Manager exclusive) |
| Supervise others | ❌ (has no team) |
