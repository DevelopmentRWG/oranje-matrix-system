---
tags:
  - arquitectura
  - rol/supervisor-hotel
aliases:
  - Supervisor System Responses
---

# 7. SYSTEM RESPONSES — SUPERVISOR

---

| Event                                                 | System Response                                                                                                |
| ----------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Supervisor creates requisition                        | Assigns auto number (AAAAMMDDHHMM + Homoclave) · Draft status (Apple Green) · Allows free editing            |
| Supervisor sends requisition for authorization        | Status switches to Apple Green — pending authorization · Notifies the Area Manager · Visible in their inbox      |
| Area Manager authorizes                            | Notifies the Supervisor: *"Your requisition was authorized and sent to Recruitment"* · Status changes to Authorized     |
| Area Manager rejects with observations             | Notifies the Supervisor: *"Your requisition was rejected"* · Observations visible in the detail · Status returns to In progress |
| Supervisor edits draft or rejected requisition        | Changes persist · Status is kept                                                                                |
| Supervisor deletes draft                              | Automatic physical deletion without journal · No confirmation needed                                                |
| System physically deletes empty requisition           | No journal · Automatic on exiting the editor                                                                          |
| Recruitment takes a requisition                       | Notifies the Supervisor: *"Your requisition was taken by [Recruiter]"* · Status switches to In process                    |
| Recruitment assigns a collaborator                    | Notifies the Supervisor · Collaborator appears in the Schedule · Updates % coverage                                  |
| Requisition is 100% covered                           | Notifies the Supervisor: *"Your requisition was 100% covered"* · Status to Covered                                  |
| Supervisor reports accident — Scenario A              | Card created with on-site capture · Notifies the zone Inspector · Collaborator status to Gray (RR-H-20)      |
| Supervisor reports accident — Scenario B              | Card created · Notifies the Inspector · Collaborator status to Gray                                                |
| Inspector starts the accident investigation           | Notifies the Supervisor of the case's progress                                                                            |
| Accident case closed                                  | Notifies the Supervisor with the resolution                                                                                  |
| Supervisor puts collaborator on Stand-by (Pink)       | Status to Pink · No Schedule or Timesheet · Notifies the collaborator and the Area Manager                            |
| Supervisor suggests staffing reinforcement            | New requisition modal pre-filled with the vacant position's data                                              |
| Supervisor consults Schedule                          | Weekly calendar view with the department's assignments                                                                    |
| Supervisor consults Timesheet                         | Weekly table with the department's clock-ins                                                                                    |
| Session started                                       | Redirects to Dashboard with a prioritized "needs action" inbox                                                       |
| Expired session                                       | Redirects to login                                                                                                       |
| Form validation error                                 | Shows clear error messages next to each invalid field                                                          |
