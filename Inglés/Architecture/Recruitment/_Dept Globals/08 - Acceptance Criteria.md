---
tags:
  - arquitectura
  - departamento/reclutamiento
aliases:
  - Recruitment Acceptance Criteria
---

# ✅ ACCEPTANCE CRITERIA — RECRUITMENT DEPARTMENT

---

| #         | Criterion                                                                                                          |
| --------- | ----------------------------------------------------------------------------------------------------------------- |
| **AC-01** | The collaborator creation form cannot be submitted if there are mandatory fields empty.                     |
| **AC-02** | The identity document must be unique in the system.                                                           |
| **AC-03** | The phone must have a valid format (10 digits).                                                               |
| **AC-04** | On submitting the form, the candidate appears with status 'Pending validation' in the list.                    |
| **AC-05** | The system blocks the registration if the candidate appears on the Blacklist.                                               |
| **AC-06** | The authorized requisition appears in the Authorized inbox in less than 30 seconds after hotel approval. |
| **AC-07** | When the FIRST recruiter takes a requisition (Collaborative Self-Pick), the status light automatically turns Yellow; subsequent takes do not trigger it again. |
| **AC-08** | The Pool search returns results in less than 2 seconds.                                                 |
| **AC-09** | The Pool allows combining at least 4 filters simultaneously.                                                      |
| **AC-10** | A requisition can only be marked as "Covered" if all positions are at 100%.                       |
| **AC-11** | The system blocks the assignment if the collaborator is on the Blacklist and shows a visible alert.                    |
| **AC-12** | On assigning a collaborator, the requisition updates its coverage percentage in real time.                    |
| **AC-13** | On assigning a collaborator, an entry is automatically generated in the hotel's Schedule.                            |
| **AC-14** | The Manager's exceptional actions require a mandatory comment before being executed.                      |
| **AC-15** | The system notifies the corresponding role in less than 1 minute after a relevant event.                         |
| **AC-16** | The encryption of sensitive data complies with the current data protection policy.                              |
| **AC-17** | The interface is responsive from 7 inches (tablet/desktop).                                                      |
| **AC-18** | The monthly availability of the module is 99.5%.                                                                |
| **AC-19** | Each status change in a requisition or collaborator is recorded in the journal with date, author and reason.  |
| **AC-20** | The numbering of requisitions and cards follows the format `YYYYMMDDHHMM + Homoclave`.                            |
| **AC-21** | An already-taken requisition can be taken by another recruiter who is added without displacing the existing ones or rolling back the status light. |
| **AC-22** | The requisition card lists all the active recruiters.                                               |
| **AC-23** | If two recruiters assign the same position, the first wins and the second sees "position already covered".          |
| **AC-24** | The History shows chronologically who took/left and who assigned/unassigned each collaborator, with date and author. |
