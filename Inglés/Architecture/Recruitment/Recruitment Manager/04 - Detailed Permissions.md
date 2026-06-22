---
tags:
  - arquitectura
  - rol/manager-reclutamiento
aliases:
  - Manager Detailed Permissions
---

# DETAILED PERMISSIONS BY ROLE

## ROL-03 · 🧑‍💼 Recruitment Manager

---

| Module        | Functionality                     | Permission     | Description                                      |
| ------------- | --------------------------------- | -------------- | ------------------------------------------------ |
| Requisition   | View global requisition view      | 👁️ View       | All in the department                            |
| Requisition   | Take personal requisition         | ➕ Create      | Special case (exceptional)                       |
| Requisition   | Assign manually to Recruiter      | ✓ Approve      | VIP case, balancing, absence (with justification) |
| Requisition   | Reassign requisition              | 📝 Edit        | Exceptional                                      |
| Requisition   | Force status light change         | 📝 Edit        | With auditable log                               |
| Recruitment   | View Collaborator Pool            | 👁️ View       | Full consultation                                |
| Recruitment   | Create collaborator (support)     | ➕ Create      | Operational backup                               |
| Recruitment   | Edit collaborator                 | 📝 Edit        | Data capture/adjustment                          |
| Recruitment   | Assign to hotel (support)         | ➕ Create      | When intervening exceptionally                   |
| **Blacklist** | Consult Blacklist                 | 👁️ View       | Full view                                        |
| **Blacklist** | Add to Blacklist                  | ➕ Create      | Same as any department role                      |
| **Blacklist** | Resolve dispute                   | 🔍 Investigate | Final decision — Manager exclusive               |
| **Blacklist** | Remove from Blacklist             | 📝 Edit        | With justification — Manager exclusive           |
| **My Team**   | View Group Leaders                | 👁️ View       | Nested view                                      |
| **My Team**   | View Recruiters                   | 👁️ View       | Filter by Leader                                 |
| **My Team**   | Create Leader                     | ➕ Create      | Creation modal                                   |
| **My Team**   | Create Recruiter                  | ➕ Create      | Assign to Leader                                 |
| **My Team**   | Edit user                         | 📝 Edit        | Change role/zone/group                           |
| **My Team**   | Move Recruiter                    | 📝 Edit        | Organizational reassignment                      |
| **My Team**   | Mark inactive / removal           | 📝 Edit        | Logical deletion                                 |
| Incidents     | View open case                    | 👁️ View       | List of escalations                              |
| Incidents     | Investigate case                  | 🔍 Investigate | Collects evidence                                |
| Incidents     | Resolve case                      | ✓ Approve      | Final decision with comment                      |
| Incidents     | Escalate to Management            | 📝 Edit        | Critical cases                                   |
| Reports       | View received reports             | 👁️ View       | From Leaders                                     |
| Reports       | Generate global report            | ➕ Create      | For Management                                   |
| Reports       | Export                            | 👁️ View       | CSV/PDF/Excel                                    |
| Dashboard     | View global KPIs                  | 👁️ View       | Department coverage                              |
| System        | Receive notification              | 👁️ View       | Critical alerts                                  |
