---
tags:
  - arquitectura
  - rol/manager-reclutamiento
aliases:
  - Manager Form Fields
---

# 3. FORM FIELDS — MANAGER

---

## Group Leader creation form

| Field            | Input Type | Required | Validation             | Description              |
| ---------------- | ---------- | -------- | ---------------------- | ------------------------ |
| Full name        | Text       | YES      | Min. 3 characters      | Legal name               |
| Document         | Text       | YES      | Unique in the system   | Official identification  |
| Email            | Email      | YES      | Valid and unique format | System access           |
| Phone            | Text       | YES      | 10 digits              | Contact                  |
| Assigned zone    | Select     | YES      | Zone catalog           | Main zone of the group   |
| Group name       | Text       | YES      | Min. 5 characters      | Group identifier         |
| Photo            | File       | NO       | JPG/PNG, max. 2 MB     | Profile photo            |

---

## Recruiter creation form

| Field           | Input Type | Required | Validation             | Description            |
| --------------- | ---------- | -------- | ---------------------- | --------------------- |
| Full name       | Text       | YES      | Min. 3 characters      | Legal name            |
| Document        | Text       | YES      | Unique in the system   | Official identification |
| Email           | Email      | YES      | Valid and unique format | System access        |
| Phone           | Text       | YES      | 10 digits              | Contact               |
| Assigned zone   | Select     | YES      | Zone catalog           | Operation zone        |
| Group Leader    | Select     | YES      | Active Leaders         | Leader they belong to |
| Photo           | File       | NO       | JPG/PNG, max. 2 MB     | Profile photo         |

---

## Blacklist inclusion form

| Field                 | Input Type | Required | Validation                                         | Description         |
| --------------------- | ---------- | -------- | -------------------------------------------------- | ------------------- |
| Collaborator          | Search     | YES      | Must exist in Pool                                 | Collaborator to ban |
| Ban reason            | Select     | YES      | Catalog (3 no-shows / Dispute / Serious offense)   | Category            |
| Detailed description  | Textarea   | YES      | Min. 30 characters                                 | Case detail         |
| Evidence              | File       | YES      | Min. 1 file, max. 10 MB each                       | Documents / photos  |
| Incident date         | DatePicker | YES      | Past date                                          | When it occurred    |

---

## Global report generation form

| Field | Input Type | Required | Validation | Description |
|---|---|---|---|---|
| Report type | Select | YES | Global coverage / Leaders comparison / Zones comparison / Times / Escalated cases | Metric type |
| Date range | DatePicker | YES | Start < end | Period |
| Filter by zone | Select multi | NO | Catalog | Zones to include |
| Filter by Leader | Select multi | NO | Active Leaders | Leaders to include |
| Export format | Select | NO | CSV / PDF / Excel | Export format |
| Recipient | Select | NO | My tracking / Sales / Only me | Whom to send to |

---

## Incident case (case data)

| Field | Input Type | Required | Validation | Description |
|---|---|---|---|---|
| Case ID | Auto | — | — | System-generated identifier (INC-XX) |
| Incident type | Select | YES | Catalog | Recruiter overload / Candidate-hotel conflict / Commercial coverage dispute / SLA breach, etc. |
| Origin | Auto | YES | Leader / Inspector / System | Who escalated the case |
| Zone | Auto | YES | Zone catalog | Zone of the case |
| Affected hotel | Search | NO (if applicable) | Hotel catalog | Hotel involved in the case |
| Description | Textarea | YES | Min. 30 characters | Problem detail |
| Evidence | File | NO | Files from the escalating party | Attachments (Inspector's investigation, reports, etc.) |
| Involved parties | Auto | — | — | Leader, Recruiter, Inspector, hotel (RF-30) |
| Priority | Select | NO | Critical / High / Medium / Low | **Mockup UI affordance; pending confirmation as an official field** |
| Date | Auto | — | — | Escalation date |
| Status | Auto | — | See [[13 - Incident States]] | Current case status |

---

## Incident resolution form (RF-30)

| Field | Input Type | Required | Validation | Description |
|---|---|---|---|---|
| Case | Auto | YES | Case under investigation | Case to resolve |
| Decision | Select | YES | Resolve / Escalate to sales / Request more information | Final decision (RF-30) |
| Comment | Textarea | YES | Mandatory (min. 30 characters) | Justification of the decision |
| (on confirm) Notifies involved parties | Auto | YES | — | Leader, Recruiter, Inspector, hotel (RF-30) |

---

## Escalation to sales form (RF-31)

| Field | Input Type | Required | Validation | Description |
|---|---|---|---|---|
| Recipient | Select | YES | BD / BDC of the affected hotel | Whom to escalate to |
| Context | Textarea | YES | Mandatory | Escalation context |
| Evidence | File | NO | Files | Attachments for sales |
