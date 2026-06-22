---
tags:
  - arquitectura
  - rol/lider-de-grupo
aliases:
  - Validations Group Leader
---

# 4. VALIDATIONS — RECRUITERS GROUP LEADER

---

## Operational validations (inherited from Recruiter)

| Case                                                    | System Behavior                                             |
| ------------------------------------------------------- | ----------------------------------------------------------- |
| Required fields empty in collaborator form              | Blocks submission and shows a message next to each invalid field |
| Identity document already exists                        | Blocks creation                                             |
| Candidate on Blacklist                                  | Blocks assignment with a visible alert                      |
| Assign an unvalidated collaborator                      | Blocks assignment                                           |
| Assign a collaborator already active in another hotel   | Blocks (exclusivity rule RR-05)                             |
| Mark requisition as covered without 100%                | Blocks the action                                           |
| Take an already-taken requisition                       | Does not block; asks "This requisition is already being worked by N recruiters. Join as a participant?" (RR-15) |
| Assign a collaborator to a position another recruiter already covered | Blocks only that slot; shows "Position already covered" (the first assignment wins; AC-23) |
| Join / assign in an already-closed requisition (covered or partial) | Blocks the action; shows "The requisition is closed"        |

---

## Leader-exclusive validations

| Case                                      | System Behavior                                                              |
| ----------------------------------------- | ---------------------------------------------------------------------------- |
| Generate report without a date range      | Blocks generation; shows "You must select a date range"                      |
| Send report without valid metrics         | Shows "The report contains no data for the selected period"                  |
| Reassign requisition to a Recruiter outside the group | Blocks the action; shows "You can only reassign among Recruiters in your group" |
| Handle incident without justification      | Blocks closure; requires a mandatory comment                                 |
| Access another group's metrics            | Blocks access; shows "You can only view metrics for your group"              |
| Export an empty report                    | Blocks export                                                                |
