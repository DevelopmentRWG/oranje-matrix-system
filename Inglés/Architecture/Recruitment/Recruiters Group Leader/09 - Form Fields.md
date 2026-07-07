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

## Action request / Log note (Recruiter communication)

> [!info]
> This form is NOT a chat. It generates a structured request or a note that is recorded in the **auditable log** of the requisition or collaborator. There is no two-way conversation: the Leader issues the action/note and the system logs it.

| Field                        | Input Type | Required | Validation                                                                                        | Description                                          |
| ---------------------------- | ---------- | -------- | ------------------------------------------------------------------------------------------------- | ---------------------------------------------------- |
| Recruiter                    | Auto       | YES      | Group Recruiters only                                                                             | Request recipient                                    |
| Request type / action        | Select     | YES      | Reassign requisition / Review collaborator / Update status / Escalate incident / Other            | Nature of the action (not free-form chat text)       |
| Context / justification      | Textarea   | YES      | Min. 10 characters, max. 1000                                                                     | Note recorded in the auditable log                   |
| Attachment                   | File       | NO       | PDF/JPG/PNG, max. 10 MB each                                                                      | Supporting file (optional)                           |

---

## Incident handling form (1st level)

| Field                      | Input Type | Required | Validation                     | Description                 |
| -------------------------- | ---------- | -------- | ------------------------------ | --------------------------- |
| Source Recruiter           | Auto       | YES      | Group Recruiter                | Who reported the incident   |
| Case type                  | Select     | YES      | Catalog options                | Case category               |
| Description                | Textarea   | YES      | Min. 20 characters             | Case detail                 |
| Action taken               | Select     | YES      | Resolved / Escalated to Manager | Leader's decision          |
| Comment / Justification    | Textarea   | YES      | Min. 10 characters             | Reasoning behind the action |
