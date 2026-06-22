---
tags:
  - arquitectura
  - rol/reclutadora
aliases:
  - Recruiter System Responses
---

# 7. SYSTEM RESPONSES — RECRUITER

---

| Event                                         | System Response                                                                                          |
| --------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Recruiter takes requisition                   | Changes status to "In progress"; adds it to "My Requisitions"; status light to Yellow; registers her as a participating recruiter in the History (does not block the others) |
| Recruiter joins a requisition already taken   | Adds her as an additional participating recruiter without displacing anyone or rolling back the status light; records the event in the History with author; notifies the other participants |
| Successful submission of new collaborator     | Show a confirmation message and redirect to the candidate list                                          |
| Form validation error                         | Show clear error messages next to each invalid field                                                    |
| Recruiter validates sign-up in app            | Notifies the system that the collaborator is enabled; propagates access automatically                    |
| Access enablement                             | Creates a log record; sends credentials to the collaborator by email/SMS                                |
| Candidate on Blacklist                        | Blocks submission and records the attempt in the history                                                |
| Successful assignment of collaborator to hotel | Updates the requisition's shared coverage %; reflects it in the hotel's Schedule; notifies the Area Manager; records in the History which collaborator was assigned to which position, with author and date |
| Mark requisition as covered                   | Notifies the **Group Leader** to validate closure; records the closure in the History with author        |
| Leave the requisition                         | Removes only the recruiter who leaves; the requisition stays In progress if other recruiters remain and does not reset what was assigned; returns to Authorized only when the last recruiter leaves; records the event in the History with author |
| Recruiter reports a problem                   | Escalates to the Group Leader with case context                                                         |
| Assigned collaborator moves to Stand-by (Pink) | Notifies the responsible Recruiter                                                                       |
| Assigned collaborator enters Red (reported)   | Notifies the Recruiter; escalates to the Inspector                                                       |
| Assigned collaborator has a work accident     | Notifies the Recruiter; status moves to Gray (Injured)                                                  |
