---
tags:
  - arquitectura
  - rol/business-developer
aliases:
  - Business Developer Detailed Permissions
---

# DETAILED PERMISSIONS BY ROLE

## ROL-V-01 · 🤝 Business Developer (BD)

---

| Module                | Functionality                       | Permission | Description                               |
| --------------------- | ----------------------------------- | -------- | ----------------------------------------- |
| **Pipeline**          | View Pipeline (my territory)        | 👁️ View  | Only prospects in my assigned territory   |
| Pipeline              | View global Pipeline                | —        | No access (BDC only)                      |
| Pipeline              | Identify prospect (Gray)            | ➕ Create | Initial action of the role                |
| Pipeline              | Create hotel profile (Light Blue)   | 📝 C · E | Basic data                                |
| Pipeline              | Register cold visit                 | ➕ Create | Documents in-person interaction           |
| Pipeline              | Register contact attempts           | ➕ Create | Calls / emails / visits                   |
| Pipeline              | Advance to Yellow (interest)        | 📝 C · E | Status change with reason                 |
| Pipeline              | Initiate negotiation (Pink)         | 📝 C · E | Alongside the BDC                         |
| Pipeline              | Mark rejection (Red)                | 📝 C · E | With mandatory reason                     |
| Pipeline              | Reactivate from Red                 | 📝 C · E | Returns to Light Blue                     |
| Pipeline              | Mark stagnation (Brown)             | 📝 C · E | The BDC handles the unblocking            |
| Pipeline              | Unblock Brown / Reactivate Brown    | —        | No access (RR-V-04 — BDC exclusive)       |
| Pipeline              | Mark / Reactivate Black             | —        | No access (RR-V-05 — BDC exclusive)       |
| Pipeline              | Approve conversion                  | —        | No access (RR-V-01 — BDC exclusive)       |
| **Proposals**         | View proposals                      | 👁️ View  | My proposals                              |
| Proposals             | Prepare Personalized Proposal       | ➕ Create | In Green status (RR-V-09)                 |
| Proposals             | Edit proposal draft                 | 📝 C · E | Before sending                            |
| Proposals             | Send proposal to hotel              | ➕ Create | Change to "Sent" state                    |
| Proposals             | Duplicate proposal as template      | ➕ Create | To use on another prospect                |
| **T&C Documents**     | View T&C Documents                  | 👁️ View  | My T&C                                    |
| T&C Documents         | Create T&C Document                 | ➕ Create | In Yellow status (RR-V-10)                |
| T&C Documents         | Edit T&C draft                      | 📝 C · E | Before sending to the BDC                 |
| T&C Documents         | Send T&C to the BDC for validation  | ➕ Create | Requests final validation                 |
| T&C Documents         | Validate T&C                        | —        | No access (BDC exclusive)                 |
| **Conversion**        | Create Hotel User                   | —        | No access (BDC exclusive)                 |
| Conversion            | Approve conversion                  | —        | No access (BDC exclusive)                 |
| **My Territory**      | View my routes and zones            | 👁️ View  | Map with prospects                        |
| My Territory          | Plan route of the day               | 📝 C · E | Mark prospects to visit                   |
| **Active Clients**    | View active clients (reference)     | 👁️ View  | Read-only — no operation (RR-V-12)        |
| Active Clients        | Register commercial contact         | ➕ Create | Courtesy visit / follow-up                |
| **Dashboard**         | View personal KPIs                  | 👁️ View  | My prospects, proposals, conversions      |
| **System** (cross-cut.)| Receive notification               | 👁️ View  | Alerts and notifications                  |
