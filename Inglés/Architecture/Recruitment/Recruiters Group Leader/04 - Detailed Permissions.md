---
tags:
  - arquitectura
  - rol/lider-de-grupo
aliases:
  - Group Leader Detailed Permissions
---

# DETAILED PERMISSIONS BY ROLE

## ROL-02 · 🧑‍🏫 Recruiters Group Leader

---

| Module        | Functionality                   | Permission | Description                                                |
| ------------- | ------------------------------- | --------- | ---------------------------------------------------------- |
| Requisition   | View Authorized queue           | 👁️ View   | Queue of available requisitions                            |
| Requisition   | Take requisition (Collaborative Self-Pick) | ➕ Create | Takes freely just like a Recruiter; does not block others (RR-15) |
| Requisition   | Join requisition (RF-39)        | ➕ Create   | Joins as a participating recruiter on one already taken (RR-15) |
| Requisition   | View active recruiters (RF-40)  | 👁️ View   | List of participating recruiters working on it now         |
| Requisition   | View requisition history (RF-41) | 👁️ View  | Immutable timeline with the actor of each event (RR-16)    |
| Requisition   | Leave the requisition (RF-03)   | 📝 Edit   | Removes only you; it stays active if other recruiters remain |
| Requisition   | Mark as in progress             | 📝 Edit   | Changes status to "in progress"                            |
| Requisition   | Mark as covered                 | 📝 Edit   | When they took the requisition and positions are at 100%   |
| Requisition   | **Approve coverage closure**    | ✓ Approve | **Approves closures marked by their Recruiters** (Light Blue status light) |
| Recruitment   | Search candidates in Pool       | 👁️ View   | Filters by position, zone, modality, English               |
| Recruitment   | Create collaborator (Phase 1)   | ➕ Create   | Sign-up after interview                                    |
| Recruitment   | Edit collaborator               | 📝 Edit   | Captures basic data                                        |
| Recruitment   | Validate sign-up in App (Phase 2) | 📝 Edit | Approves collaborator                                      |
| Recruitment   | Enable access                   | ➕ Create   | Activates the collaborator's panels                        |
| Recruitment   | Register interview              | ➕ Create   | Documents the result                                       |
| Recruitment   | Assign collaborator to hotel    | ➕ Create   | Covers the requisition                                     |
| Recruitment   | Assign to the Schedule          | ➕ Create   | Generates an entry in the hotel's weekly Schedule          |
| Recruitment   | Reassign collaborator           | 📝 Edit   | Rotation between hotels                                     |
| Recruitment   | Unassign collaborator           | 📝 Edit   | Removal due to end/problem                                  |
| Blacklist     | Check Blacklist                 | 👁️ View   | Mandatory check before assigning                           |
| Blacklist     | Add to Blacklist                | ➕ Create   | Any role in the department can ban with reason and evidence |
| **My Group**  | View group's Recruiters         | 👁️ View   | List with metrics                                          |
| **My Group**  | View individual metrics         | 👁️ View   | Performance detail per Recruiter                           |
| **My Group**  | View detailed workload (RF-36)  | 👁️ View   | Recruiter's requisitions in progress                       |
| **My Group**  | Reassign requisition (RF-37)    | 📝 Edit   | Passes a requisition to another Recruiter in the group     |
| **My Group**  | Mark availability (RF-38)       | 📝 Edit   | Toggle Active ↔ Vacation for the Recruiter                 |
| **Reports**   | Generate group report           | ➕ Create   | Coverage, performance, escalated cases                     |
| **Reports**   | Send report to the Manager      | ✓ Approve | Formal submission with notification                         |
| **Reports**   | Export report                   | 👁️ View   | CSV / PDF                                                  |
| Reports       | View individual coverage        | 👁️ View   | Own KPIs                                                   |
| Reports       | View group coverage             | 👁️ View   | Group KPIs                                                 |
| Reports       | View coverage by zone           | 👁️ View   | Filters by zone                                           |
| Dashboard     | View personal and group KPIs    | 👁️ View   | Dashboard view                                            |
| System        | Receive notification            | 👁️ View   | Automatic alerts                                          |
