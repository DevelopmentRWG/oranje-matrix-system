---
tags:
  - arquitectura
  - rol/manager-de-area
aliases:
  - Area Manager Validations
---

# 4. VALIDATIONS — AREA MANAGER

---

| Case                                                       | System Behavior                                                                                                          |
| ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Attempting to authorize a requisition without positions    | Blocks the action; shows: *"It has no registered positions, register at least one position and try again"*                |
| Another role tries to authorize (Supervisor)               | Blocks the action; shows: *"Only the hotel manager can authorize the requisition"*                                        |
| Rejecting without observations                             | Blocks the action; shows: *"Observations are mandatory when rejecting"*                                                    |
| Deleting a requisition with positions without justification| Blocks the action; shows: *"Justification is mandatory when deleting a requisition with positions"*                        |
| Physical deletion confirmation not checked                 | Blocks the button; shows: *"You must confirm that the positions will be physically deleted"*                               |
| Generating a QR without the role's permissions             | Blocks the action; shows: *"Only the hotel manager can generate the Timesheet QR code"*                                   |
| Correcting a punch without justification                   | Blocks the action; shows: *"Justification is mandatory to correct punches"*                                                |
| Correcting a punch with a time outside the shift range     | Shows a warning; allows continuing with additional confirmation                                                           |
| Reporting a collaborator with a description <50 characters | Blocks submission; shows: *"The description must be at least 50 characters to start the investigation"*                    |
| Reporting a collaborator not assigned to the dept          | Blocks the action; shows: *"You can only report collaborators assigned to your department"*                               |
| Putting on Stand-by a collaborator already on Stand-by     | Blocks the action; shows: *"The collaborator is already on Stand-by"*                                                      |
| Stand-by without a reason selected                         | Blocks submission; shows: *"Select the reason for the Stand-by"*                                                          |
| Editing Schedule with crossed positions (same collaborator in 2 shifts) | Blocks saving; shows: *"The collaborator is already assigned at this time in another position"*             |
| Accessing the Extended Lunch Indicator                     | No visible access; the module does not appear in the interface                                                            |
| Attachment >5 MB in forms                                  | Rejects the file; shows: *"Maximum size: 5 MB"*                                                                           |
| Report evidence >10 MB                                     | Rejects the file; shows: *"Maximum evidence size: 10 MB"*                                                                 |
| Expired session                                            | Redirects to login; shows: *"Your session has expired, please log in again"*                                              |
