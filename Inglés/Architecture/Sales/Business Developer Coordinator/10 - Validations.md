---
tags:
  - arquitectura
  - rol/bdc
aliases:
  - BDC Validations
---

# 4. VALIDATIONS — BUSINESS DEVELOPER COORDINATOR

---

| Case                                                        | System Behavior                                                                                      |
| ----------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Reject T&C without observations                             | Blocks submission; shows: *"Observations are mandatory when rejecting"*                              |
| Reject T&C with observations <30 characters                 | Blocks submission; shows: *"Observations must be at least 30 characters"*                            |
| Create Hotel User with duplicate email                      | Blocks submission; shows: *"This email is already registered in the system"*                         |
| Create Hotel User without assigned role                     | Blocks submission; shows: *"Select the assigned role"*                                               |
| Approve conversion without Hotel User previously created    | Blocks button; shows: *"You must create the Hotel User before approving the conversion"* (RR-V-02)   |
| Approve conversion without validated T&C                    | Blocks button; shows: *"The T&C Document must be validated before approving the conversion"*         |
| Approve conversion without checking final confirmation      | Blocks button; shows: *"Confirm that the hotel meets the requirements to be activated"*              |
| Unblock Brown without diagnosis or solution                 | Blocks submission; shows: *"Diagnosis and solution are mandatory"*                                   |
| Unblock Brown with fields <50 characters                    | Blocks submission; shows: *"Each field must be at least 50 characters"*                              |
| Mark Black without reason                                   | Blocks submission; shows: *"Select the reason for the Black"*                                        |
| Mark Black with comment <30 characters                      | Blocks submission; shows: *"The comment must be at least 30 characters"*                             |
| Reactivate Black outside my territory                       | Blocks action; shows: *"You do not have permission to manage this client"*                           |
| Reassign prospect to a BD not in my territory               | Blocks selection; shows: *"You can only reassign to BDs in your territory"*                          |
| Generate report without type                                | Blocks submission; shows: *"Select the report type"*                                                |
| Send report without recipients                              | Blocks submission; shows: *"Select at least one recipient"*                                          |
| Send recurring report without frequency                     | Blocks submission; shows: *"Select the frequency of the recurring sending"*                          |
| Attachment >10 MB                                           | Rejects file; shows: *"Maximum size: 10 MB"*                                                         |
| Try to mark Red                                             | Action not available (RR-V-06 — exclusive BD)                                                        |
| Try to access post-Orange operation                         | Action not available (RR-V-12 — commercial reference without operation)                              |
| Expired session                                             | Redirects to login                                                                                  |
