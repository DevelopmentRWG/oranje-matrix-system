---
tags:
  - arquitectura
  - rol/supervisor-hotel
aliases:
  - Supervisor Form Fields
---

# 3. FORM FIELDS — SUPERVISOR

---

## A) "New Requisition" Form (RF-H-01)

| Field                  | Input Type    | Required    | Validation                                                                | Description                                  |
| ---------------------- | ------------- | ----------- | ------------------------------------------------------------------------- | -------------------------------------------- |
| Position               | Select        | YES         | [[Posiciones|Positions]] catalog (Housekeeper, Hoseman, Chef, Laundry)    | Position to cover                            |
| Quantity               | Number        | YES         | Integer >0                                                                | People to cover this position                |
| Start date             | Date          | YES         | Date in the future                                                        | When the staff is needed                     |
| Clock-in time          | Time          | YES         | HH:MM format (24h)                                                        | Workday start time                           |
| Clock-out time         | Time          | YES         | HH:MM format (24h) · Greater than clock-in                                | Workday end time                             |
| Modality               | Select        | YES         | [[Employment Types|Hiring Modalities]] catalog (FT / PT / Temporary / OR)     | Hiring type                         |
| English level          | Select        | YES         | [[English Levels|English Levels]] catalog (Basic / Intermediate / Advanced / Conv.) | Level preference                |
| Additional notes       | Textarea      | NO          | Max. 500 characters                                                       | Context, special requirements              |
| Attachments            | File          | NO          | PDF/JPG/PNG, max. 5 MB                                                    | Supporting documents                       |

> [!note]
> A requisition can have multiple positions. The form allows adding several "Position + Quantity" rows before sending for authorization.

---

## B) Accident Report Form — Scenario A and B (RF-H-20, RF-H-21)

| Field                              | Input Type    | Required    | Validation                              | Description                                                |
| ---------------------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Affected collaborator              | Select        | YES         | List of assigned collaborators          | Who suffered the accident                                  |
| Accident date                      | Date          | YES         | Current or past date (not future)       | When it occurred                                           |
| Accident time                      | Time          | YES         | HH:MM format                            | At what time it occurred                                   |
| Exact location                     | Text          | YES         | Min. 10 characters                      | Specific place on the property                            |
| Circumstances                      | Textarea      | YES         | Min. 50 characters                      | Detailed description of how it occurred                   |
| Immediate care provided            | Textarea      | YES         | Min. 20 characters                      | What was done at the moment (first aid, etc.)             |
| Witnesses                          | Text          | NO          | Min. 3 characters if filled in          | Witness names                                              |
| Evidence (photos/video)            | File          | NO          | JPG/PNG/MP4, max. 10 MB                 | On-site capture                                            |
| Geolocation (mobile)               | Auto          | NO          | Auto from the device                    | Coordinates of the place (if applicable)                  |
| Scenario                           | Select        | YES         | A (collaborator reported first) / B (Supervisor detected) | Flow type                              |

---

## C) Stand-by (Pink) Form — RF-H-17

| Field            | Input Type    | Required    | Validation                              | Description                                                |
| ---------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Collaborator     | Select        | YES         | List of assigned collaborators          | Collaborator to put on Stand-by                           |
| Reason           | Select        | YES         | Catalog: Vacation / Low season / Hotel decision / Other | Reason                                       |
| Notes            | Textarea      | NO          | Max. 500 characters                     | Additional context                                         |

---

## D) Suggest Reinforcement Form (RF-H-19)

| Field                  | Input Type    | Required    | Validation                              | Description                                                |
| ---------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Missing position       | Auto          | YES         | Pre-filled from the Schedule            | Detected vacant position                                  |
| Vacant days            | Auto          | YES         | Pre-filled from the Schedule            | Days without an assigned collaborator                     |
| Justification          | Textarea      | YES         | Min. 20 characters                      | Why reinforcement is needed                               |
| Continue to New Requisition | Action   | YES         | —                                       | Takes you to form A pre-filled                            |

---

## E) My Requisitions Filters

| Field                | Input Type    | Required    | Description                                                |
| -------------------- | ------------- | ----------- | ---------------------------------------------------------- |
| Status               | Multi-select  | NO          | Drafts / Pending / Rejected / Authorized / etc.            |
| Position             | Select        | NO          | Positions catalog                                          |
| Creation date        | Date Range    | NO          | Range                                                      |
| Search by ID/number  | Text          | NO          | Free search                                                |
