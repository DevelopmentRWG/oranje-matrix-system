---
tags:
  - arquitectura
  - rol/reclutadora
aliases:
  - Recruiter Actions
---

# 6. USER ACTIONS — RECRUITER

---

| Action                                    | Result                                                                                          |
| ----------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Take requisition from the inbox           | I join as a participating recruiter; the requisition appears in My Requisitions; status light to Yellow (In progress). It does not block the others (collaborative Self-Pick) |
| Join a requisition already taken          | I add myself as an additional participating recruiter without displacing the existing ones or rolling back the status light; coverage progress is shared. Recorded in the History |
| View active recruiters                    | Shows the list of participating recruiters working the requisition right now (role + name) |
| View requisition history                  | Shows the immutable chronological timeline with actor: who took/left and who assigned/unassigned each collaborator, with date and author |
| Leave the requisition                     | Removes only me; the requisition stays In progress if other recruiters remain; does not reset what was assigned; returns to Authorized only when the last recruiter leaves |
| Search candidate in Pool                  | Results in a filtered list of available collaborators                                           |
| Complete new collaborator form            | The candidate's data is loaded into the system with status 'Pending validation'                 |
| Save collaborator draft                   | The record is saved with status 'Draft'                                                         |
| Send candidate to validation             | The record changes to status 'Pending validation'                                              |
| Validate sign-up in App                   | The collaborator is approved and enters the Pool with Strong Green status (Available)           |
| Enable collaborator access                | System propagates access to the collaborator's panels                                           |
| Register interview                        | The result is linked to the candidate's profile                                                 |
| Check Blacklist                           | System shows whether the candidate is banned                                                    |
| Assign collaborator to position          | The requisition's coverage % is updated                                                         |
| Assign to Schedule                        | An entry is created in the hotel's weekly Schedule                                              |
| Reassign collaborator to another hotel    | Assignment history is updated                                                                    |
| Unassign collaborator                     | Releases the position; notifies the hotel                                                        |
| Mark requisition as covered               | Requests closure from the Manager (only if coverage = 100%)                                      |
| Mark requisition as partial               | Closes the requisition with shortfalls                                                           |
| Cancel action                             | Changes are not saved; returns to the previous view                                             |
