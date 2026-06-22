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

## Dispute resolution form

| Field | Input Type | Required | Validation | Description |
|---|---|---|---|---|
| Case | Auto | YES | Open case | Dispute to resolve |
| Decision | Select | YES | Maintain ban / Remove from Blacklist | Final resolution |
| Comment | Textarea | YES | Min. 30 characters | Justification |
| Notify the parties | Checkbox | YES | Default: YES | Notification delivery |

---

## Global report generation form

| Field | Input Type | Required | Validation | Description |
|---|---|---|---|---|
| Report type | Select | YES | Global coverage / Leaders comparison / Zones comparison / Times / Escalated cases | Metric type |
| Date range | DatePicker | YES | Start < end | Period |
| Filter by zone | Select multi | NO | Catalog | Zones to include |
| Filter by Leader | Select multi | NO | Active Leaders | Leaders to include |
| Export format | Select | NO | CSV / PDF / Excel | Export format |
| Recipient | Select | NO | Management Email / Others | Whom to send to |
