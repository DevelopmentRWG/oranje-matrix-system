---
tags:
  - arquitectura
  - rol/manager-reclutamiento
aliases:
  - Manager System Responses
---

# 7. SYSTEM RESPONSES — MANAGER

---

| Event                                         | System Response                                                                 |
| --------------------------------------------- | ------------------------------------------------------------------------------- |
| Manager takes personal requisition            | Records exceptional intervention in log; moves to "My Requisitions"             |
| Manager assigns manually to Recruiter         | Notifies the Recruiter with context; kept in log with reason                    |
| Manager forces status light change            | Applies change with auditable log; notifies those involved                      |
| Manager adds recruiter to requisition         | Adds them as a participant without displacing others; notifies the active participants; records the event in the History |
| Participating recruiter assigns collaborator to a position | Marks the position as covered (position/slot lock); records the assignment as a timeline event with author and date |
| Participating recruiter unassigns collaborator | Frees the position for reassignment; records the unassignment as a timeline event with author and date |
| Recruiter leaves the requisition              | Removes only them; remains "In process" if other recruiters remain; returns to "Authorized" only when the last one leaves; records the event in the History |
| Manager adds to Blacklist                     | Collaborator moves to Black (permanent); notifies the collaborator; blocks future assignments |
| Manager creates Leader                        | Creates account; sends credentials by email; appears in My Team                 |
| Manager creates Recruiter                     | Creates account and assigns to the Leader; notifies the assigned Leader         |
| Manager moves Recruiter to another Leader     | Notifies both Leaders; updates the relationship                                 |
| Manager marks user as inactive                | Blocks the user's access; preserves history                                     |
| Manager resolves incident                     | Closes case; notifies the parties involved                                      |
| Manager escalates to Management               | Sends the full case to the Director; record is kept                             |
| Manager generates global report              | Compiles data; shows preview                                                    |
| Manager exports report                        | Downloads the requested file                                                    |
| Manager receives alert of stalled requisition | Appears in the Dashboard's Action Inbox                                          |
| Manager receives escalation from Leader       | Notifies with context and opens the case in Incidents                           |
| Manager receives escalation from Inspector    | Notifies with attached investigation                                            |
| System detects urgent requisition untaken     | Automatic alert to the Manager after N configured hours                          |
| System detects Recruiter overload             | Alerts the Manager and the corresponding Leader                                 |
