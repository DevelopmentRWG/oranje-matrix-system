---
tags:
  - arquitectura
  - rol/supervisor-hotel
aliases:
  - Supervisor Validations
---

# 4. VALIDATIONS — SUPERVISOR

---

| Case                                                       | System Behavior                                                                                                |
| ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Create requisition without positions                       | Allows saving as a draft, but when trying to send for authorization: blocks with *"Has no registered positions, register at least one position and try again"* (RR-H-03) |
| Number of people <1                                        | Blocks sending; shows: *"The quantity must be at least 1 person"*                                                        |
| Start date in the past                                      | Blocks sending; shows: *"The start date must be in the future"*                                                              |
| Clock-out time less than or equal to clock-in               | Blocks sending; shows: *"The clock-out time must be greater than the clock-in time"*                                              |
| Position not selected                                       | Blocks sending; shows: *"Select a position"*                                                                         |
| Modality or English level not selected                     | Blocks sending; shows: *"Complete the required fields"*                                                                 |
| Attachment >5 MB                                            | Rejects file; shows: *"Maximum size: 5 MB"*                                                                            |
| Try to authorize requisition                               | Blocks action; shows: *"Only the hotel manager can authorize the requisition"* (RR-H-02)                            |
| Report accident without selecting a collaborator           | Blocks sending; shows: *"Select the affected collaborator"*                                                              |
| Report accident with description <50 characters            | Blocks sending; shows: *"The circumstances must have at least 50 characters"*                                            |
| Report accident without immediate care                     | Blocks sending; shows: *"State what immediate care was provided"*                                                         |
| Report accident with future date                           | Blocks sending; shows: *"The accident date cannot be in the future"*                                                      |
| Evidence >10 MB                                            | Rejects file; shows: *"Maximum evidence size: 10 MB"*                                                              |
| Stand-by without a selected reason                         | Blocks sending; shows: *"Select the Stand-by reason"*                                                                |
| Stand-by on a collaborator already on Stand-by             | Blocks action; shows: *"The collaborator is already on Stand-by"*                                                     |
| Try to report a collaborator (Red)                         | Action not available (only Area Manager); the button does not appear                                                          |
| Try to generate the Timesheet QR                           | Action not available; the button does not appear                                                                    |
| Try to edit the Schedule                                    | Read-only access; edit buttons do not appear                                                                     |
| Access the Extended Lunch Indicator                        | No access; the module does not appear in the interface (RR-H-15)                                                                    |
| Expired session                                            | Redirects to login; shows: *"Your session has expired, please log in again"*                                    |
