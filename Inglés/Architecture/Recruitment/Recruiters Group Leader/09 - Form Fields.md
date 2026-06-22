---
tags:
  - arquitectura
  - rol/lider-de-grupo
aliases:
  - Form Fields Group Leader
---

# 3. FORM FIELDS — GROUP LEADER

> [!info]
> The Group Leader operates with the same forms as a Recruiter (see `Recruiter/09 - Form Fields.md`) **plus** the exclusive supervision and reporting forms detailed below.

---

## Report generation form (Leader-exclusive)

| Field                  | Input Type   | Required | Validation                                                                           | Description               |
| ---------------------- | ------------ | -------- | ------------------------------------------------------------------------------------ | ------------------------- |
| Report type            | Select       | YES      | Group coverage / Individual performance / Escalated cases / Workload distribution    | Type of metric to generate |
| Date range             | DatePicker   | YES      | Start date < end date                                                                | Report period             |
| Filter by zone         | Multi select | NO       | Must select an option from the catalog                                               | Zones to include          |
| Filter by Recruiter    | Multi select | NO       | Group Recruiters only                                                                | Recruiters to include     |
| Filter by position     | Multi select | NO       | Positions from the catalog                                                           | Positions to include      |
| Comments               | Textarea     | NO       | Max. 1000 characters                                                                 | Additional notes          |
| Recipient              | Select       | YES      | Recruitment Manager (auto)                                                           | Whom to send to           |

---

## Recruiter communication form (chat/note)

| Field     | Input Type | Required | Validation                    | Description              |
| --------- | ---------- | -------- | ----------------------------- | ------------------------ |
| Recruiter | Auto       | YES      | Group Recruiters only         | Message recipient        |
| Subject   | Text       | YES      | Min. 5 characters             | Message summary          |
| Message   | Textarea   | YES      | Min. 10 characters, max. 2000 | Message content          |
| Attachments | File     | NO       | PDF/JPG/PNG, max. 10 MB each  | Related files            |

---

## Incident handling form (1st level)

| Field                      | Input Type | Required | Validation                     | Description                 |
| -------------------------- | ---------- | -------- | ------------------------------ | --------------------------- |
| Source Recruiter           | Auto       | YES      | Group Recruiter                | Who reported the incident   |
| Case type                  | Select     | YES      | Catalog options                | Case category               |
| Description                | Textarea   | YES      | Min. 20 characters             | Case detail                 |
| Action taken               | Select     | YES      | Resolved / Escalated to Manager | Leader's decision          |
| Comment / Justification    | Textarea   | YES      | Min. 10 characters             | Reasoning behind the action |
