---
tags:
  - arquitectura
  - rol/reclutadora
aliases:
  - Recruiter Detailed Permissions
---

# DETAILED PERMISSIONS BY ROLE

## ROL-01 · 👤 Recruiter

---

| Module        | Functionality                 | Permission | Description                                                              |
| ------------- | ----------------------------- | --------- | ------------------------------------------------------------------------ |
| Requisition   | View Authorized queue         | 👁️ View   | Queue of requisitions available to take                                  |
| Requisition   | Take / Join requisition (collaborative Self-Pick) | ➕ Create | Freely takes the requisition; if others are already there, she joins as an additional participating recruiter (RR-15) |
| Requisition   | View active recruiters        | 👁️ View   | List of the participating recruiters working the requisition             |
| Requisition   | View requisition history      | 👁️ View   | Immutable chronological timeline with actor (RR-16)                      |
| Requisition   | Leave the requisition         | 📝 Edit   | Removes only herself; returns to Authorized only when the last recruiter leaves |
| Requisition   | Mark as in process            | 📝 Edit   | Changes status to "in process"                                          |
| Requisition   | Mark as covered               | 📝 Edit   | Requests closure from the **Group Leader** when positions are at 100%    |
| Recruitment   | Search candidates in Pool     | 👁️ View   | Filters by position, zone, modality, English                            |
| Recruitment   | Create collaborator (Phase 1) | ➕ Create | Sign-up after initial interview                                          |
| Recruitment   | Edit collaborator data        | 📝 Edit   | Captures basic data                                                     |
| Recruitment   | Validate sign-up in app (Phase 2) | 📝 Edit | Approves collaborator after self-sign-up                                |
| Recruitment   | Enable access                 | ➕ Create | Activates the collaborator's panels                                      |
| Recruitment   | Record interview              | ➕ Create | Documents the result                                                    |
| Recruitment   | Assign collaborator to hotel  | ➕ Create | Covers the requisition                                                  |
| Recruitment   | Assign to Schedule            | ➕ Create | Generates an entry in the hotel's weekly Schedule                        |
| Recruitment   | Reassign collaborator         | 📝 Edit   | Rotation between hotels                                                  |
| Recruitment   | Unassign collaborator         | 📝 Edit   | Removal due to end/problem                                              |
| Blacklist     | Check Blacklist               | 👁️ View   | Mandatory lookup before assigning                                       |
| Blacklist     | Add to Blacklist              | ➕ Create | Any department role can send to the Blacklist with reason and evidence   |
| Reports       | View individual coverage      | 👁️ View   | Own KPIs                                                                |
| Dashboard     | View personal KPIs            | 👁️ View   | Dashboard view                                                          |
| System        | Receive notification          | 👁️ View   | Automatic alerts                                                        |
