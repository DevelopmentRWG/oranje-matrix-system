---
tags:
  - arquitectura
  - rol/manager-reclutamiento
aliases:
  - Manager Actions
---

# 6. USER ACTIONS — RECRUITMENT MANAGER

---

| Action                                           | Result                                                               |
| ------------------------------------------------ | -------------------------------------------------------------------- |
| Take personal requisition (special case)         | System records intervention with reason in log; status light to Yellow |
| Assign manually to Recruiter                     | System notifies the Recruiter; kept in log with justification        |
| Reassign requisition                             | Original Recruiter loses access; new one receives it with notification |
| Force status light change                        | Change applied with auditable log; notifies those involved           |
| Approve inclusion in Blacklist                   | Collaborator is banned; notifies the collaborator and Recruiter      |
| Resolve Blacklist dispute                        | Final decision applied; closes case with comment                     |
| Remove from Blacklist                            | Collaborator reactivated in Pool; record of the removal is kept      |
| Create Group Leader                              | System creates account with assigned role; sends credentials         |
| Create Recruiter                                 | System creates account and assigns to the selected Leader            |
| Edit user                                        | System applies changes; record is kept                               |
| Move Recruiter to another Leader                 | Recruiter changes group; notifies both Leaders                       |
| Mark user as inactive / vacation / removal       | System deactivates access; record is kept                            |
| Investigate incident case                        | Access to evidence, comments and recommendations                     |
| Resolve incident                                 | Closure with final decision and mandatory comment                    |
| Escalate to Management                           | Notifies the Director with full context                              |
| Generate global report                           | System compiles data for the period                                  |
| Export report                                    | Downloads file (CSV/PDF/Excel)                                       |
| Schedule report delivery                         | Configures recurrence (weekly/monthly)                               |
| Cancel action                                    | Changes are not saved                                                |
