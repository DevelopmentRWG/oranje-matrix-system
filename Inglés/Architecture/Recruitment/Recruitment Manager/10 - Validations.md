---
tags:
  - arquitectura
  - rol/manager-reclutamiento
aliases:
  - Manager Validations
---

# 4. VALIDATIONS — RECRUITMENT MANAGER

---

| Case                                    | System Behavior                                                           |
| --------------------------------------- | ------------------------------------------------------------------------- |
| Take requisition without justification  | Requests mandatory comment (it is exceptional)                            |
| Assign manually without comment         | Blocks action; shows "Manual assignment requires justification"           |
| Force status light change without reason | Blocks change; requests mandatory comment                                |
| Add a recruiter who is already a participant | Blocks; shows "The recruiter is already a participant of this requisition" |
| Two recruiters assign the same collaborator to the same position | First assignment wins; the second is shown "Position already covered" (lock at position/slot level) |
| Close requisition with several active participants | Requests confirmation; on closing, records the closure in the History with author |
| Leave (last recruiter) with incomplete coverage | Allows leaving; the requisition returns to "Authorized" (does not reset what was already assigned) |
| Approve Blacklist without attached evidence | Blocks creation; shows "You must attach at least one piece of evidence"  |
| Approve Blacklist without description    | Blocks creation; shows "You must describe the reason (min. 30 characters)" |
| Remove from Blacklist without justification | Blocks action; requests comment                                        |
| Resolve dispute without comment          | Blocks closure; requests justification                                   |
| Create Leader with duplicate email       | Blocks creation; shows "Email already exists in the system"              |
| Create Recruiter without assigned Leader | Blocks creation; shows "You must assign a Leader"                        |
| Edit own role                            | Blocks action; shows "You cannot edit your own role"                     |
| Delete Leader with active Recruiters     | Blocks removal; shows "Reassign the group's Recruiters first"            |
| Generate report without date range       | Blocks generation                                                        |
| Generate report with empty period        | Shows "The report contains no data for the period"                      |
| Escalate to Management without context    | Blocks escalation; requests summary                                     |
