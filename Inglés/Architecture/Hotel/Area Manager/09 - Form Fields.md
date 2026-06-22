---
tags:
  - arquitectura
  - rol/manager-de-area
aliases:
  - Area Manager Form Fields
---

# 3. FORM FIELDS — AREA MANAGER

> [!info]
> The Area Manager **does not fill out creation forms**, but does complete several action forms (rejection, deletion with positions, punch correction, collaborator report, etc.). Below are the fields required per action.

---

## A) Requisition Rejection Form (RF-H-06)

| Field            | Input Type    | Required    | Validation                              | Description                                                |
| ---------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Reason           | Select        | YES         | Catalog: Wrong positions / Incorrect modality / Incomplete data / Missing justification / Other | Rejection category                                        |
| Observations     | Textarea      | YES         | Min. 20 characters                      | Detail of what the Supervisor must correct                 |
| Attachments      | File          | NO          | PDF/JPG/PNG, max. 5 MB                  | Supporting evidence or document (optional)                 |

---

## B) Requisition with Positions Deletion Form (RF-H-07)

| Field            | Input Type    | Required    | Validation                              | Description                                                |
| ---------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Justification    | Textarea      | YES         | Min. 20 characters                      | Why the requisition with positions is being deleted        |
| Confirmation     | Checkbox      | YES         | Must be checked                         | "I confirm that the positions will be physically deleted"  |

---

## C) Punch Correction Form (RF-H-14)

| Field                  | Input Type    | Required    | Validation                              | Description                                                |
| ---------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Collaborator           | Select        | YES         | List of assigned collaborators          | Collaborator to correct                                    |
| Day                    | Date          | YES         | Day within the current week             | Date of the punch to correct                               |
| Punch type             | Select        | YES         | Catalog: Clock-in / Lunch-out / Lunch-in / Break-out / Break-in / Clock-out | Which of the 6 punches                                     |
| Corrected time         | Time          | YES         | Format HH:MM (24h)                      | New punch time                                             |
| Correction reason      | Textarea      | YES         | Min. 20 characters                      | Mandatory justification — recorded in an auditable log     |
| Attachments            | File          | NO          | PDF/JPG/PNG, max. 5 MB                  | Evidence (optional)                                        |

---

## D) Stand-by (Pink) Form — RF-H-17

| Field            | Input Type    | Required    | Validation                              | Description                                                |
| ---------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Collaborator     | Select        | YES         | List of assigned collaborators          | Collaborator to put on Stand-by                           |
| Reason           | Select        | YES         | Catalog: Collaborator's vacation / Low season / Hotel decision / Other | Reason for the Stand-by                                    |
| Notes            | Textarea      | NO          | Max. 500 characters                     | Additional context                                         |

---

## E) Collaborator Report (Red) Form — RF-H-18

| Field            | Input Type    | Required    | Validation                              | Description                                                |
| ---------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Collaborator     | Select        | YES         | List of assigned collaborators          | Collaborator to report                                    |
| Reason           | Select        | YES         | Catalog: Serious misconduct / Bad behavior / Theft / Conflict / Other | Reason for the report                                      |
| Description      | Textarea      | YES         | Min. 50 characters                      | Detail of the incident for the Inspector's investigation  |
| Evidence         | File          | NO          | PDF/JPG/PNG, max. 10 MB                 | Photos, videos or documents                                |
| Witnesses        | Text          | NO          | Min. 3 characters if filled in          | Witness names                                              |

---

## F) Schedule / Timesheet Filters

| Field                    | Input Type    | Required    | Description                                                |
| ------------------------ | ------------- | ----------- | ---------------------------------------------------------- |
| Department               | Select        | NO          | Only in extended hierarchy (Manager's scope)               |
| Position                 | Select        | NO          | Positions catalog                                          |
| Coverage status          | Select        | NO          | Covered / Partial / Vacant                                 |
| Week                     | Date Range    | YES         | Week selector                                              |
| Search (name/position)   | Text          | NO          | Free search                                                |
