---
tags:
  - arquitectura
  - rol/bdc
aliases:
  - BDC Detailed Permissions
---

# DETAILED PERMISSIONS BY ROLE

## ROL-V-02 · 🧑‍💼 Business Developer Coordinator (BDC)

---

| Module                | Functionality                      | Permission    | Description                                                    |
| --------------------- | ---------------------------------- | ------------- | -------------------------------------------------------------- |
| **Pipeline**          | View global territory Pipeline     | 👁️ View      | All supervised BDs                                            |
| Pipeline              | Identify prospect                  | ➕ Create      | Occasional (not its main action)                              |
| Pipeline              | Create hotel profile               | 📝 C · E      | Occasional                                                    |
| Pipeline              | Advance to Yellow                  | 📝 C · E      | Alongside the BD                                              |
| Pipeline              | Start negotiation (Pink)           | 📝 C · E      | Alongside the BD                                              |
| Pipeline              | Mark Red                           | —             | No access (RR-V-06 — exclusive BD)                            |
| Pipeline              | Mark Brown                         | 📝 C · E      | Shared with BD                                                |
| Pipeline              | Unblock Brown                      | 🔍 Investigate | Exclusive (RR-V-04)                                          |
| Pipeline              | Reactivate from Brown              | 📝 C · E      | Returns to Light Blue (RR-V-07)                              |
| Pipeline              | Comment on the file                | 📝 C · E      | Visible to the BD                                            |
| Pipeline              | Reassign prospect to another BD    | 📝 C · E      | Exceptional                                                  |
| **T&C Documents**     | View T&C Documents                 | 👁️ View      | All of the territory                                         |
| T&C Documents         | Create T&C Document                | ➕ Create      | Shared with BD                                               |
| T&C Documents         | Edit T&C Document                  | 📝 C · E      | —                                                            |
| T&C Documents         | ✓ Validate T&C                     | ✓ Approve     | **Exclusive action — final yes** (RR-V-15)                  |
| T&C Documents         | ✗ Reject T&C with observations     | ✗ Reject      | Returns to the BD                                            |
| **Conversion**        | Create Hotel User                  | ➕ Create      | **Exclusive precondition** (RR-V-02)                        |
| Conversion            | ✓ Approve conversion               | ✓ Approve     | **Exclusive final yes** (RR-V-01)                           |
| **My Team**           | View BDs in charge                 | 👁️ View      | List with metrics                                           |
| My Team               | View individual metrics per BD     | 👁️ View      | Performance detail                                          |
| My Team               | Communicate with BD                | 📝 C · E      | Chat / internal note                                        |
| My Team               | Request specific report            | ➕ Create      | —                                                            |
| **Active Clients**    | View active clients                | 👁️ View      | Commercial read-only (RR-V-12)                              |
| Active Clients        | Mark client Black                  | 📝 C · E      | **Exclusive** (RR-V-05)                                     |
| Active Clients        | Reactivate from Black              | 📝 C · E      | **Exclusive** — returns to Light Blue (RR-V-07)             |
| **Reports**           | Generate Sales report              | ➕ Create      | Pipeline / conversion / performance / Brown / Black templates |
| Reports               | Export (CSV / PDF / Excel)         | 👁️ View      | —                                                            |
| Reports               | Send to management                 | ➕ Create      | Email / internal link                                       |
| Reports               | Schedule recurring sending         | 📝 C · E      | Weekly / monthly                                            |
| Reports               | View report history                | 👁️ View      | —                                                            |
| **Dashboard**         | View personal KPIs                 | 👁️ View      | My metrics                                                  |
| Dashboard             | View global territory KPIs         | 👁️ View      | Funnel, heatmap, BD ranking                                 |
| **System** (cross.)   | Receive notification               | 👁️ View      | Critical alerts                                             |
