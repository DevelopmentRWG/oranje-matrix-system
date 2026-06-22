---
tags:
  - arquitectura
  - rol/business-developer
aliases:
  - Business Developer Form Fields
---

# 3. FORM FIELDS — BUSINESS DEVELOPER

---

## A) Identify Prospect (Gray) — RF-V-01

| Field            | Input Type    | Required | Validation                          | Description                          |
| ---------------- | ------------- | -------- | ----------------------------------- | ------------------------------------ |
| Hotel name       | Text          | YES      | Min. 3 characters                   | Name of the prospect                 |
| City             | Text          | YES      | Min. 3 characters                   | City of location                     |
| Zone / Route     | Select        | YES      | Catalog of Zones assigned to the BD | Zone of the prospect                 |
| Geolocation      | Auto / Manual | NO       | GPS coordinates                     | Auto from mobile, manual on desktop  |
| Lead source      | Select        | NO       | Referral / Visit / Web / Other      | Where the prospect came from         |
| Initial notes    | Textarea      | NO       | Max. 500 characters                 | BD's observations                    |

---

## B) Create Hotel Profile (Light Blue) — RF-V-02

| Field                         | Input Type    | Required | Validation                        | Description                |
| ----------------------------- | ------------- | -------- | --------------------------------- | -------------------------- |
| Main email                    | Email         | YES      | Valid email format                | Hotel contact              |
| Phone                         | Text          | YES      | Valid format                      | Main contact               |
| Contact name                  | Text          | YES      | Min. 3 characters                 | Person being dealt with    |
| Contact position              | Text          | YES      | Min. 3 characters                 | Position at the hotel      |
| Business need                 | Textarea      | YES      | Min. 30 characters                | What the hotel needs       |
| Hotel size                    | Select        | NO       | Small / Medium / Large / Luxury   | Commercial category        |
| Estimated personnel count     | Number        | NO       | Integer >0                        | Initial estimate           |

---

## C) Register Cold Visit — RF-V-03

| Field               | Input Type    | Required | Validation                                                     | Description               |
| ------------------- | ------------- | -------- | -------------------------------------------------------------- | ------------------------- |
| Visit date          | Date          | YES      | Current or past date                                           | When the visit was made   |
| Time                | Time          | YES      | —                                                              | Approx. time              |
| Person contacted    | Text          | YES      | Min. 3 characters                                              | Who attended              |
| Result              | Select        | YES      | Interested / Not available / Rejection / Pending new attempt   | Result of the visit       |
| Observations        | Textarea      | NO       | Max. 500 characters                                            | Details                   |
| Next follow-up      | Date          | NO       | Future date                                                    | When to contact again     |

---

## D) Register Contact Attempt — RF-V-06

| Field        | Input Type    | Required | Validation                                     | Description       |
| ------------ | ------------- | -------- | ---------------------------------------------- | ----------------- |
| Type         | Select        | YES      | Call / Email / Visit / WhatsApp                | Contact medium    |
| Date and time | Datetime     | YES      | Current or past                                | When it was made  |
| Result       | Select        | YES      | No response / Responded / Reschedules / Rejection | —              |
| Notes        | Textarea      | NO       | Max. 500 characters                            | Details           |

---

## E) Prepare Personalized Proposal — RF-V-04

| Field                    | Input Type    | Required | Validation                     | Description                  |
| ------------------------ | ------------- | -------- | ------------------------------ | ---------------------------- |
| Destination hotel        | Auto          | YES      | Pre-filled from the prospect   | Hotel it is prepared for     |
| Proposed services        | Multi-select  | YES      | Services catalog               | What is offered              |
| Prices                   | Number/Table  | YES      | Per service                    | Proposed rates               |
| General conditions       | Textarea      | YES      | Min. 100 characters            | Commercial terms             |
| Proposal validity        | Date          | YES      | Future date                    | Until when it is valid       |
| Attachments              | File          | NO       | PDF / DOCX, max. 10 MB         | Supporting documents         |

---

## F) Create T&C Document — RF-V-08

> [!important]
> Mandatory fields defined by RR-V-10. Without these fields, negotiation (Pink) cannot be initiated.

| Field          | Input Type    | Required | Validation           | Description                    |
| -------------- | ------------- | -------- | -------------------- | ------------------------------ |
| **Pay rate**   | Number        | YES      | >0                   | Payment rate to the collaborator |
| **Bill rate**  | Number        | YES      | >0                   | Billing rate to the hotel      |
| **Overtime**   | Number / %    | YES      | >0                   | Overtime rules                 |
| **Holidays**   | Multi-select  | YES      | Holidays catalog     | Paid holidays                  |
| **Calendar**   | Date Range    | YES      | Valid range          | Start and end of the week      |
| Validity       | Date Range    | NO       | Future range         | Validity period                |
| Renewal        | Select        | NO       | Auto / Manual / Fixed | Renewal terms                 |
| Attachments    | File          | NO       | PDF, max. 10 MB      | Supporting documents           |

---

## G) Mark Rejection (Red) — RF-V-15

| Field                    | Input Type    | Required | Validation                                                            | Description                                  |
| ------------------------ | ------------- | -------- | --------------------------------------------------------------------- | -------------------------------------------- |
| Reason                   | Select        | YES      | Catalog: Not interested / No budget / Another company / Other         | Reason for the rejection                     |
| Comment                  | Textarea      | YES      | Min. 30 characters                                                    | Details of the rejection                     |
| Reactivate later?        | Checkbox      | NO       | —                                                                     | If checked, remains as a "candidate to reactivate" |

---

## H) Mark Brown (Stagnation) — RF-V-17

| Field                    | Input Type    | Required | Validation                                                       | Description                         |
| ------------------------ | ------------- | -------- | ---------------------------------------------------------------- | ----------------------------------- |
| Stagnation reason        | Select        | YES      | Catalog: No response / Change of contact / Undefined / Other     | Reason                              |
| Notes for the BDC        | Textarea      | YES      | Min. 30 characters                                               | Context for the BDC to unblock      |

---

## I) Pipeline / My Territory Filters

| Field                      | Input Type    | Required | Description                                |
| -------------------------- | ------------- | -------- | ------------------------------------------ |
| Status                     | Multi-select  | NO       | Catalog of Onboarding Status Light statuses |
| Route / Zone               | Select        | NO       | Catalog of my assigned routes              |
| Days without contact       | Slider        | NO       | 1-3 / 4-7 / >7                             |
| Search by name / city      | Text          | NO       | Free search                                |
