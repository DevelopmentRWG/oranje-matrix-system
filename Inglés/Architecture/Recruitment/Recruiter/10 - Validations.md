---
tags:
  - arquitectura
  - rol/reclutadora
aliases:
  - Recruiter Validations
---

# 4. VALIDATIONS — RECRUITER

---

| Case                                            | System Behavior                                                             |
| ----------------------------------------------- | --------------------------------------------------------------------------- |
| Required fields empty on form submit            | Blocks submission and shows an error message next to each invalid field     |
| Identity document already exists in the system  | Blocks creation; shows the message "This document is already registered"     |
| Phone with invalid format                       | Blocks submission; shows "Invalid phone format (10 digits)"                 |
| ID card larger than 5 MB                        | Rejects the file; shows "Maximum size: 5 MB"                               |
| Candidate appears on the Blacklist              | Blocks creation/assignment; shows a visible alert with the ban reason       |
| Age outside the allowed range (<18 or >65)      | Blocks submission; shows "Age must be between 18 and 65 years"             |
| Assign an unvalidated collaborator              | Blocks assignment; shows "The collaborator must be validated first"        |
| Assign a collaborator already active in another hotel | Blocks assignment; shows "The collaborator is already assigned to another hotel" |
| Mark requisition as covered without 100%        | Blocks the action; shows "Coverage must be 100% to close as covered"       |
| Take a requisition already taken by another     | Collaborative flow (does not block); shows "There is/are already N recruiter(s); you will join as a participant" and adds you as an additional recruiter (RR-15) |
| Join a requisition you already participate in   | Blocks the action; shows "You are already a participating recruiter of this requisition" |
| Assign the same collaborator to the same position another recruiter already covered | Blocks at the slot level; the first assignment wins and shows "Position already covered" to the second |
| Join a closed requisition (covered/partial)     | Blocks the action; shows "The requisition is closed; it is not possible to join" |
| Leave the requisition without justification     | Requires a mandatory reason before leaving                                  |
