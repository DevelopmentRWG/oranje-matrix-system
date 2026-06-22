---
tags:
  - arquitectura
  - rol/bdc
aliases:
  - BDC Form Fields
---

# 3. FORM FIELDS — BDC

> [!info]
> The BDC does not fill out operational prospect forms (that belongs to the BD). Its forms are for **validation, special-case management, conversion and executive reports**.

---

## A) Validate T&C Document — RF-V-10

| Field            | Input Type | Mandatory                     | Validation                    | Description              |
| ---------------- | ---------- | ----------------------------- | ----------------------------- | ------------------------ |
| Decision         | Select     | YES                           | Approve / Reject              | BDC's decision           |
| Comment to the BD | Textarea  | NO if approves / YES if rejects | Min. 30 characters if rejects | Observations for the BD |
| Attachments      | File       | NO                            | PDF, max. 10 MB               | Supporting documents     |

---

## B) Create Hotel User — RF-V-11

| Field             | Input Type | Mandatory   | Validation                                    | Description                     |
| ----------------- | ---------- | ----------- | --------------------------------------------- | ------------------------------- |
| Hotel             | Auto       | YES         | Pre-filled from the prospect                  | Destination hotel               |
| User email        | Email      | YES         | Valid format and unique in the system         | Email of the hotel's manager    |
| Full name         | Text       | YES         | Min. 3 characters                             | Person at the hotel             |
| Assigned role     | Select     | YES         | Catalog: Area Manager / General Manager       | Role they will have in the platform |
| Phone             | Text       | NO          | Valid format                                  | Contact                         |
| Notes             | Textarea   | NO          | Max. 500 characters                           | Observations                    |

---

## C) Approve Conversion — RF-V-12

| Field                          | Input Type | Mandatory   | Validation                           | Description                                                  |
| ------------------------------ | ---------- | ----------- | ------------------------------------ | ------------------------------------------------------------ |
| Hotel                          | Auto       | YES         | Pre-filled                           | Hotel to convert                                            |
| Hotel User confirmation        | Auto       | YES         | System validates that the User exists | Blocked if not yet created (RR-V-02)                       |
| Validated T&C                  | Auto       | YES         | System validates that it is approved | Blocked if not                                              |
| Notes for the close            | Textarea   | NO          | Max. 500 characters                  | BDC's observations                                          |
| Final confirmation             | Checkbox   | YES         | Must be checked                      | "I confirm that the hotel meets the requirements to be activated" |

---

## D) Unblock Brown — RF-V-18

| Field             | Input Type | Mandatory   | Validation                                                      | Description                       |
| ----------------- | ---------- | ----------- | --------------------------------------------------------------- | --------------------------------- |
| Diagnosis         | Textarea   | YES         | Min. 50 characters                                              | Detected cause of the stagnation  |
| Agreed solution   | Textarea   | YES         | Min. 50 characters                                              | Action plan                       |
| Decision          | Select     | YES         | Reactivate to Light Blue / Reassign to another BD / Close as Red | Final result                     |

---

## E) Mark Client Black — RF-V-20

| Field          | Input Type | Mandatory   | Validation                                                                     | Description           |
| -------------- | ---------- | ----------- | ------------------------------------------------------------------------------ | --------------------- |
| Reason         | Select     | YES         | Catalog: Hotel closure / Change of administration / Pause / Dispute / Other    | Reason for the Black  |
| Comment        | Textarea   | YES         | Min. 30 characters                                                             | Detail                |
| Pause date     | Date       | NO          | Current or past date                                                           | When it stopped operating |

---

## F) Generate Report — RF-V-26

| Field                        | Input Type   | Mandatory   | Validation                                                             | Description                |
| ---------------------------- | ------------ | ----------- | --------------------------------------------------------------------- | -------------------------- |
| Report type                  | Select       | YES         | Pipeline / Conversion / Performance / Brown / Black / Quality / Executive | Template to use         |
| Date range                   | Date Range   | YES         | —                                                                     | Period                     |
| Included BDs                 | Multi-select | NO          | Catalog of BDs in charge                                              | If omitted, includes all   |
| Routes / Zones               | Multi-select | NO          | Catalog                                                               | Additional filters         |
| Output format                | Select       | YES         | PDF / CSV / Excel                                                     | —                          |
| Previous-period comparison   | Checkbox     | NO          | —                                                                     | Include vs previous month  |

---

## G) Send Report to Management — RF-V-27

| Field                      | Input Type           | Mandatory   | Validation                           | Description                  |
| -------------------------- | -------------------- | ----------- | ------------------------------------ | ---------------------------- |
| Recipients                 | Multi-select / Email | YES         | List of executives / valid emails    | To whom to send              |
| Subject                    | Text                 | YES         | Min. 10 characters                   | Email subject                |
| Message                    | Textarea             | NO          | Max. 1000 characters                 | Context                      |
| Attached report            | Auto                 | YES         | Pre-filled                           | Previously generated report  |
| Schedule recurring sending | Checkbox             | NO          | —                                    | If checked, opens options    |
| Frequency                  | Select               | NO          | Weekly / Monthly / Quarterly         | Only if recurring            |
