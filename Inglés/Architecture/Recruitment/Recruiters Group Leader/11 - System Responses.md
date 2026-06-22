---
tags:
  - arquitectura
  - rol/lider-de-grupo
aliases:
  - System Responses Group Leader
---

# 7. SYSTEM RESPONSES — GROUP LEADER

---

## Operational responses (inherited from Recruiter)

| Event                      | System Response                                                         |
| -------------------------- | ----------------------------------------------------------------------- |
| Leader takes requisition   | Moves to "My Requisitions"; status light to Yellow (In progress); records in the History who took it (author + date) |
| Leader joins an already-taken requisition (RF-39) | Adds them as a participating recruiter; tag "Shared · N recruiters"; records in the History who joined (author + date); does NOT displace existing ones |
| Leader views active recruiters (RF-40) | Lists the participating recruiters working it now (role + name) |
| Leader views requisition history (RF-41) | Shows the immutable chronological timeline with the actor and timestamp of each event |
| Creates new collaborator   | Confirmation message; redirects to list                                 |
| Validates sign-up in App   | Enables access automatically; notifies the collaborator                 |
| Assigns collaborator to hotel | Updates coverage (shared); reflects in Schedule; notifies the Area Manager; records in the History who assigned which collaborator to which position (author + date) |
| Two recruiters assign the same position | The first assignment wins; the second is shown "Position already covered" (lock at position/slot level) |
| Leader leaves the requisition | Removes only them; stays In progress if other recruiters remain and does NOT reset what was assigned; returns to Authorized when the last one leaves; records in the History who left (author + date) |
| Marks requisition as covered | System closes it (Light Blue); the hotel's status light notifies the closure; records in the History who closed it (author + date) |
| Group Recruiter marks as covered | A request reaches the Leader to approve the closure              |

---

## Leader-exclusive responses

| Event                                            | System Response                                                      |
| ------------------------------------------------ | -------------------------------------------------------------------- |
| Group Recruiter covered requisition at 100%      | Notifies the Leader with congratulations and updated metric          |
| Group Recruiter reported a problem               | Notifies the Leader with case context for 1st-level handling         |
| Leader generates report                          | Compiles period data and shows a preview                             |
| Leader sends report to the Manager               | Creates a record in history; notifies the Manager with a link to the report |
| Leader exports report                            | Downloads file (CSV/PDF)                                             |
| Leader handles incident                          | Records in the log with resolution and comment                       |
| Leader escalates incident to the Manager         | Notifies the Manager with all context and evidence                   |
| Manager requests a report from the Leader        | A request notification appears in the Leader's action inbox          |
| Group Recruiter changes availability             | Notifies the Leader (vacation, leave, return)                        |
| Group Recruiter goes into overload               | Automatic alert to the Leader when exceeding N simultaneous requisitions |
