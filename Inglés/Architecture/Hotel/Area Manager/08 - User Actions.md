---
tags:
  - arquitectura
  - rol/manager-de-area
aliases:
  - Area Manager Actions
---

# 6. USER ACTIONS — AREA MANAGER

---

| Action                                              | Result                                                                                               |
| --------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Authorize requisition                               | State changes to Authorized · Automatic urgency calculation · Inspector assignment · Reflection in Schedule · Reaches the Recruitment inbox |
| Reject requisition with observations                | State returns to In preparation with observations · Notifies the Supervisor                           |
| Delete requisition with positions                   | Each position moves to Purple with an individual journal · Confirmation message                       |
| Delete draft / empty requisition                    | Automatic physical deletion without journal                                                          |
| Generate / Renew Timesheet QR code                  | QR valid immediately · Notifies assigned collaborators                                               |
| Edit weekly Schedule                                | Changes persist · Notifies the affected collaborator                                                 |
| Move collaborator between days/shifts               | Schedule updated · Notification to the collaborator                                                  |
| Mark collaborator's day off                         | Schedule shows the day as "Day off"                                                                  |
| Export weekly Schedule                              | Download PDF/CSV                                                                                       |
| Correct Timesheet punch                             | Change applied · Mandatory justification · Auditable log with author and date                       |
| Export weekly Timesheet                             | Download PDF/CSV                                                                                       |
| Put collaborator on Stand-by (Pink)                 | State in Collaborator Status Light changes to Pink · No Schedule or Timesheet until state change      |
| Remove Stand-by (returns to previous state)         | Reactivates the collaborator in Schedule and Timesheet                                               |
| Report collaborator (Red)                           | State changes to Red · Notifies the Inspector · Starts investigation                                 |
| Request staff reinforcement                         | Suggestion of a new prefilled requisition (the Supervisor creates it)                                |
| Cancel action                                       | Changes are not saved                                                                                |
