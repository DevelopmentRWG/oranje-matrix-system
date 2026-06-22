---
tags:
  - arquitectura
  - departamento/hotel
aliases:
  - Hotel Dept PRD
---

# PRODUCT REQUIREMENTS DOCUMENT
## PRD – HOTEL

**Staff Management System · Hotel Department**

---

| Field | Content |
|---|---|
| **PRD ID** | PRD-HOTEL-01 |
| **User Story** | HU-HOTEL-01 |
| **Department** | Hotel |
| **Functionality** | Manage the hotel lifecycle as a client: staffing request, approval, weekly Schedule management, Timesheet recording and incident reporting |
| **Primary Actor** | Area Manager · Supervisor · General Manager (extended hierarchy) |
| **Device** | Web – Desktop / Tablet / Mobile (Supervisor app) |
| **Status** | In definition |
| **Version** | 1.0 |

---

## Objective

Allow the hotel to **request staff from Oranje** via requisitions, **manage the weekly Schedule** and the **Timesheet** of assigned collaborators, and **report incidents** (workplace accidents, collaborators with issues). The Hotel dept acts as the counterpart of the Recruitment dept under the security-layer model: **the Supervisor creates, the Area Manager authorizes, Recruitment takes via Self-Pick**.

---

## Scope

**Includes:**
- Hotel enablement post-onboarding (Orange status in the Onboarding Status Light).
- Creation of requisitions by the Supervisor.
- Authorization / rejection by the Area Manager (security layer).
- Weekly Schedule management.
- Generation of the Timesheet QR (Area Manager).
- Punch recording and calculation of the Timesheet Compliance Indicator.
- Stand-by (Pink) and reporting (Red) of collaborators.
- Workplace accident reporting by the Supervisor (scenarios A and B).
- Global visibility and executive reports by the General Manager (extended hierarchy).
- Support for simple and extended hierarchy.

**Out of scope:**
- Recruitment, validation and assignment of collaborators (Recruitment module).
- On-site operational inspection (Inspection module).
- Quality auditing (QA module).
- Pre-client commercial onboarding (Sales / Onboarding-Hotel module).
- System configuration (Administrator module — on hold).

---

## General Flow

**Supervisor creates requisition → Area Manager authorizes → Recruitment takes it (Self-Pick) → Assigned collaborators appear in the hotel's Schedule → Area Manager generates QR → Collaborators punch into Timesheet → Compliance Indicator calculation → Weekly payment**

```
HOTEL                                          ORANJE                          
─────                                          ──────
Supervisor creates requisition
        │
        ▼
Area Manager authorizes ──────────────────►  Inbox of Authorized
                                                       │
                                                       ▼
                                               Recruiter/Leader takes (Self-Pick)
                                                       │
                                                       ▼
                                               Assigns collaborators
        ┌───────────────────────────────────────────────┘
        ▼
Hotel Schedule ←── assigned collaborators
        │
        ▼
Area Manager generates QR
        │
        ▼
Timesheet (daily punches) ───────────────────► Compliance Indicator
        │
        ▼
Stand-by (Pink) / Report (Red) / Accident (Gray) ──► Inspector / Investigation
```

---

## Actors

| Actor                      | Type           | Main responsibility                                        |
| -------------------------- | -------------- | ---------------------------------------------------------------- |
| Supervisor (SUP)           | Operational    | Creates requisitions · Reports workplace accidents                |
| Area Manager             | Supervisor     | Authorizes requisitions · Manages Schedule and Timesheet · Generates QR |
| General Manager (GM)       | Executive      | Global visibility · Manager supervision · Executive reports |
| System                     | Automation     | Numbering, status lights, Inspector assignment, journals, notifications |
| Administrator *(on hold)*  | Configuration  | Users, catalogs, permissions                                    |

---

## Constraints / Applicable business rules

See [[07 - Business Rules|07 - Business Rules]] for details. The most important:

- **RR-H-01:** The hotel only operates after reaching Orange status in the Onboarding Status Light.
- **RR-H-02:** Only the Area Manager authorizes requisitions (security layer).
- **RR-H-09:** Only the Area Manager generates the Timesheet QR.
- **RR-H-10:** Only the Area Manager reports a collaborator (Red).
- **RR-H-11:** Stand-by (Pink) shared between Area Manager and Supervisor.
- **RR-H-13:** System supports simple and extended hierarchy.

---

## Integrations (RI)

| ID       | Integration                            | Description                                                                       |
| -------- | -------------------------------------- | --------------------------------------------------------------------------------- |
| RI-H-01  | Hotel ↔ Recruitment                    | Authorized requisitions move to the Recruitment inbox (Self-Pick).                |
| RI-H-02  | Hotel ↔ Schedule                       | Authorized positions are automatically reflected in the weekly Schedule.          |
| RI-H-03  | Hotel ↔ Timesheet                      | The Timesheet is built on top of the Schedule. Punches are recorded via QR.       |
| RI-H-04  | Hotel ↔ Inspection                     | Automatic Inspector assignment by zone upon authorization. Investigation of Red and Gray. |
| RI-H-05  | Hotel ↔ QA                             | Fixed QA operator assigned to the Hotel dept. Metrics and Quality Indicator.      |
| RI-H-06  | Hotel ↔ Onboarding-Hotel               | Hotel enablement upon reaching Orange status in the Onboarding Status Light.       |
---

## Dependencies

See [[09 - Dependencies|09 - Dependencies]] for details.

- Depends on [[Recruitment/Recruitment|Recruitment]] to fill requisitions.
- Depends on [[Inspection/Inspection|Inspection]] to investigate reports and accidents.
- Depends on [[Sales/Hotel Onboarding|Onboarding-Hotel]] for hotel enablement.
- Depends on [[QA/QA|QA]] for quality auditing.
- Depends on the [[Core/Catalogs/Hotel Departments|Hotel Departments catalog]] and [[Posiciones|Positions]].
