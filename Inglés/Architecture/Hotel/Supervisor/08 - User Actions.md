---
tags:
  - arquitectura
  - rol/supervisor-hotel
aliases:
  - Supervisor Actions
---

# 6. USER ACTIONS — SUPERVISOR

---

| Action                                                  | Result                                                                                                |
| ------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Create new requisition                                   | System assigns auto number (AAAAMMDDHHMM + Homoclave) · Status Apple Green — In progress (draft) |
| Edit draft / rejected requisition                        | Changes persist · Status is kept                                                                    |
| Send requisition for authorization                       | Sent to the Area Manager · Status switches to Apple Green — pending authorization · Notification      |
| Delete draft                                             | Automatic physical deletion without journal (RR-H-07)                                                      |
| Suggest staffing reinforcement                           | New requisition modal pre-filled with the vacant position's data                                  |
| Report accident — Scenario A                             | On-site capture · Card with data, witnesses, care · Notifies the Inspector                       |
| Report accident — Scenario B                             | Creates card with the accident data · Collaborator status to Gray · Notifies the Inspector             |
| Attach on-site evidence to the accident                  | Uploads photo / video / note · Stays associated with the card                                                  |
| Put collaborator on Stand-by (Pink)                      | Collaborator Status Light state to Pink · No Schedule or Timesheet · Notifies the collaborator         |
| Remove Stand-by                                          | Reactivates the collaborator in Schedule and Timesheet                                                          |
| Consult department Schedule                              | Weekly calendar view with assignments                                                                |
| Consult department Timesheet                             | Weekly table × collaborator with clock-ins and net hours                                                    |
| Cancel action                                            | Changes are not saved                                                                                     |
