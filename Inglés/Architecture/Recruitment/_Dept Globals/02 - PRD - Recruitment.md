---
tags:
  - arquitectura
  - departamento/reclutamiento
aliases:
  - Recruitment Dept PRD
---

# PRODUCT REQUIREMENTS DOCUMENT
## PRD – RECRUITMENT

**Personnel Management System · Recruitment Department**

---

| Field | Content |
|---|---|
| **PRD ID** | PRD-RECL-01 |
| **User Story** | HU-RECL-01 |
| **Department** | Recruitment |
| **Functionality** | Manage the full recruitment cycle under a collaborative Self-Pick model |
| **Primary Actor** | Recruiter · Recruiters Group Leader |
| **Device** | Web – Desktop |
| **Status** | In definition |
| **Version** | 1.0 |

---

## Objective

Enable the Recruitment team to capture, validate and enable collaborators to integrate them into the Collaborator Pool, and to cover the requisitions authorized by the hotels under a **collaborative Self-Pick model** where Recruiters and Group Leaders freely take requisitions from the inbox according to their capacity. Taking a requisition that is already taken does not block or transfer it: the recruiter joins as an additional participant, so several participating recruiters can work the same requisition at once with shared coverage.

---

## Scope

**Includes:**
- Receiving requisitions authorized by the hotels.
- Free, collaborative taking of requisitions by Recruiters and Group Leaders (collaborative Self-Pick): several participating recruiters per requisition, with shared coverage.
- Requisition history/traceability: immutable chronological timeline with actor (who took/joined/left and who assigned/unassigned each collaborator, with date and author).
- Searching candidates in the Collaborator Pool.
- Sign-up of new collaborators in 3 phases (interview, app, emergency data).
- Validation of collaborators after sign-up in the app.
- Assignment of collaborators to requisitions and to the hotel's Schedule.
- Querying and managing the Blacklist.
- Team supervision (Group Leader and Manager).
- Coverage and performance reports.

**Out of scope:**
- On-site operational inspection (Inspection module).
- Quality auditing (QA module).
- Pre-client commercial cycle (Hotel-Onboarding module).

---

## General Flow

**Hotel authorizes requisition → Arrives in Inbox → Recruiter/Leader takes → Searches in Pool → Assigns → Covers**

---

## Actors

| Actor                     | Type           | Main responsibility                            |
| ------------------------- | -------------- | ---------------------------------------------- |
| Recruiter                 | Operational    | Takes requisitions and covers them with collaborators |
| Recruiters Group Leader   | Intermediate   | Takes + supervises the group                   |
| Recruitment Manager       | Supervisor     | Department management + special cases          |
| System                    | Automation     | Automatic calculations, notifications, journals |
| Administrator             | Configuration  | Users, catalogs, permissions                   |
