---
tags:
  - arquitectura
  - rol/manager-de-area
aliases:
  - Area Manager System Responses
---

# 7. SYSTEM RESPONSES — AREA MANAGER

---

| Event                                                 | System Response                                                                                                      |
| ----------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Manager authorizes requisition                        | Changes state to Authorized · Calculates urgency · Assigns Inspector by zone · Reflects positions in Schedule · Sends to the Recruitment inbox (Self-Pick) · Notifies the Supervisor |
| Manager rejects requisition                           | Changes state to In preparation · Notifies the Supervisor with observations · Stays in the Supervisor's inbox for correction |
| Manager deletes requisition with positions            | Each position moves to Purple with an individual journal · Requisition state to Purple · Message: *"Upon confirming the deletion of the requisition, the registered positions and the requisition will be physically deleted"* |
| System physically deletes empty requisition           | No journal · No notification (automatic)                                                                             |
| Manager generates / renews QR                         | QR valid immediately · Notifies assigned collaborators · Recorded in the log with generation date                   |
| Manager corrects punch                                | Change applied · Auditable log with author, date, reason · Notifies the collaborator of the change                  |
| Manager edits Schedule                                | Changes persist · Notifies the affected collaborator · Recalculates the Compliance Indicator                        |
| Manager puts collaborator on Stand-by (Pink)          | State in Collaborator Status Light to Pink · No Schedule or Timesheet · Notifies the collaborator and the Supervisor |
| Manager removes Stand-by                               | State returns to the previous state · Reactivation in Schedule and Timesheet                                        |
| Manager reports collaborator (Red)                    | State to Red · Notifies the zone Inspector · Starts investigation · Recorded in the auditable log                   |
| System assigns Inspector by zone automatically        | Notifies the Inspector with the hotel and requisition data · Visible in the requisition detail                      |
| Recruitment takes an authorized requisition           | Notifies the Area Manager: *"Your requisition was taken by [Recruiter]"* · Changes state to In process              |
| Recruitment assigns collaborator                      | Notifies the Area Manager · Collaborator appears in the weekly Schedule · Updates coverage %                        |
| Requisition becomes 100% covered                      | Notifies the Area Manager: *"Your requisition was 100% covered"* · Changes state to Covered                         |
| Collaborator completes their shift with Red compliance| Visible alert on the Dashboard · Notifies the Area Manager · Correction suggestion                                  |
| Dept Compliance Indicator drops to Red                | Notifies the Area Manager and the General Manager (extended hierarchy)                                              |
| Session started                                       | Redirects to the Dashboard with KPIs loaded                                                                          |
| Session expired                                       | Redirects to login                                                                                                   |
| Form validation error                                 | Shows clear error messages next to each invalid field                                                                |
