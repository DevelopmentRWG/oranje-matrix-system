---
tags:
  - arquitectura
  - rol/manager-general
aliases:
  - Form Fields General Manager
---

# 3. FORM FIELDS — GENERAL MANAGER

> [!info]
> The General Manager does not fill out operational forms. Their forms are for **comments, escalations and generation of executive reports**.

---

## A) Comment on File Form (RF-H-26)

| Field            | Input Type    | Required    | Validation                              | Description                                                |
| ---------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Comment          | Textarea      | YES         | Min. 20 characters                      | Comment that the Department Manager will see               |
| Notify           | Multi-select  | NO          | List of involved parties                | Who to notify (Manager, Supervisor, etc.)                  |
| Attachments      | File          | NO          | PDF/JPG/PNG, max. 5 MB                  | Evidence or supporting document                            |

---

## B) Escalate Delayed Requisition Form (RF-H-27)

| Field                | Input Type    | Required    | Validation                              | Description                                                |
| -------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Requisition          | Auto          | YES         | Pre-filled from the requisition         | ID and number                                              |
| Escalation reason    | Select        | YES         | Catalog: Excessive time in queue / Red Urgency / VIP Hotel / Other | Main reason                                            |
| Message to the Recruitment Manager | Textarea | YES      | Min. 30 characters                       | Context and specific request                               |

---

## C) Request Report from Manager Form (RF-H-28)

| Field                | Input Type    | Required    | Validation                              | Description                                                |
| -------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Recipient Manager    | Select        | YES         | List of Department Managers             | To whom the request is made                                |
| Report type          | Select        | YES         | Template catalog                        | Coverage / Performance / Cases / Other                     |
| Date range           | Date Range    | YES         | —                                       | Period to report                                           |
| Message              | Textarea      | NO          | Max. 500 characters                     | Context of the request                                     |
| Deadline             | Date          | NO          | Future date                              | When it is needed                                          |

---

## D) Generate Executive Report Form (RF-H-24)

| Field                | Input Type    | Required    | Validation                              | Description                                                |
| -------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Report type          | Select        | YES         | Catalog: Coverage / Performance / Compliance / Quality / Accidents / Executive indicators | Template to use                                          |
| Date range           | Date Range    | YES         | —                                       | Period                                                     |
| Departments          | Multi-select  | NO          | Department catalog                      | If omitted, includes all                                  |
| Additional filters   | Multi-select  | NO          | Position / Hotel / Manager              | Extra filters                                             |
| Output format        | Select        | YES         | PDF / CSV / Excel                       | Export format                                             |
| Comparison vs previous period | Checkbox | NO     | —                                       | Includes vs previous month                                |

---

## E) Send Report to Direction Form (RF-H-25)

| Field                | Input Type    | Required    | Validation                              | Description                                                |
| -------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Recipients           | Multi-select / Email | YES      | List of executives / valid emails       | To whom to send                                           |
| Subject              | Text          | YES         | Min. 10 characters                       | Subject of the email / link                                |
| Message              | Textarea      | NO          | Max. 1000 characters                     | Context of the send                                        |
| Attached report      | Auto          | YES         | Pre-filled                              | Previously generated report                                |
| Schedule recurring send | Checkbox  | NO         | —                                       | If checked, opens recurrence options                       |
| Frequency            | Select        | NO          | Weekly / Monthly / Quarterly            | Only if recurring                                          |
