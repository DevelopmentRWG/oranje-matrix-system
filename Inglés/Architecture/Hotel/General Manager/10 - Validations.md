---
tags:
  - arquitectura
  - rol/manager-general
aliases:
  - Validations General Manager
---

# 4. VALIDATIONS — GENERAL MANAGER

---

| Case                                                       | System Behavior                                                                                                          |
| ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Comment on file with <20 characters                        | Blocks send; shows: *"The comment must be at least 20 characters"*                                                         |
| Escalate requisition without reason                        | Blocks send; shows: *"Select the escalation reason"*                                                                       |
| Escalate requisition with message <30 characters           | Blocks send; shows: *"The message to the Recruitment Manager must be at least 30 characters"*                              |
| Request report without type                                | Blocks send; shows: *"Select the report type"*                                                                            |
| Request report without date range                          | Blocks send; shows: *"Indicate the date range to report"*                                                                 |
| Request report with past deadline                          | Blocks send; shows: *"The deadline must be in the future"*                                                                 |
| Generate report without type                               | Blocks send; shows: *"Select the report type"*                                                                            |
| Send report without recipients                             | Blocks send; shows: *"Select at least one recipient"*                                                                      |
| Send report without subject                                | Blocks send; shows: *"The subject is mandatory"*                                                                           |
| Send recurring report without frequency                    | Blocks send; shows: *"Select the frequency of the recurring send"*                                                        |
| Attachment >5 MB                                           | Rejects file; shows: *"Maximum size: 5 MB"*                                                                                |
| Attempt to authorize requisition                           | Action not available; the button does not appear (RR-H-14)                                                                 |
| Attempt to generate QR / correct punch                     | Action not available; the corresponding modules are read-only                                                             |
| Attempt to edit Schedule                                   | Action not available; read-only view                                                                                       |
| Attempt to add user                                        | Action not available (that is the Administrator's)                                                                         |
| Access Extended Lunch Indicator                            | No access; the indicator does not appear in the interface (RR-H-15)                                                        |
| Expired session                                            | Redirects to login                                                                                                         |
| Access hotel with simple hierarchy                         | No access to the General Manager role; message: *"This role only applies in hotels with extended hierarchy"*               |
