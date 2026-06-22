---
tags:
  - arquitectura
  - departamento/reclutamiento
aliases:
  - Recruitment Dependencies
---

# 9. DEPENDENCIES — RECRUITMENT DEPARTMENT

---

## Internal dependencies (other modules of the Oranje system)

| Dependency                      | Description                                                                                                                                        |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Hotel Module**                 | The Recruitment dept receives the requisitions authorized by the Area Manager. Without approved requisitions there is no coverage flow.       |
| **Schedule Module**              | On assigning a collaborator, the entry in the hotel's Schedule is automatically generated. Bidirectional: Recruitment writes, Schedule queries. |
| **Timesheet Module**             | The Timesheet reads the assigned collaborators. The Recruitment Manager sees the Extended Lunch indicator.                                    |
| **Collaborator Pool Module** | It is the central repository where Recruitment feeds new collaborators and from where it consumes to cover requisitions.                       |
| **Blacklist Module**             | Mandatory check before each assignment. Only the Manager can manage (CRUD).                                                             |
| **Inspection Module**            | The Inspector investigates Blacklist disputes and Red cases of the Collaborator Status Light. Receives escalations from the Manager.                          |
| **Onboarding-Hotel Module**      | Receives escalations from the Manager when an incident affects the commercial relationship with the hotel.                                                  |
| **QA Module**                    | Supervises the Recruitment department through the Quality Indicator. The QA Operator issues formal observations.                       |

---

## External dependencies (systems or apps outside the module)

| Dependency                     | Description                                                                                                                                  |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **Collaborator App**         | The collaborator completes their Phase 2 (app registration) and Phase 3 (emergency data). The system receives the registration confirmation via webhook or API. |
| **Notifications System**   | Sends automatic notifications to the dept roles on relevant events.                                                              |
| **Audit / Logs System** | Records journals of requisitions and positions; traceability of exceptional changes.                                                      |

---

## Catalog dependencies (system configuration)

| Catalog                        | Description                                                                              |
| ------------------------------- | ---------------------------------------------------------------------------------------- |
| **Positions**                  | Housekeeper, Hoseman, Chef, Laundry, etc. Maintained by the Administrator.                |
| **Zones**                       | Centro, Sur, Este, Oeste, Noroeste, Sureste. Inspector assignment is based on zones. |
| **Hiring Modalities** | Full time, Part time, Temporary, On request.                                            |
| **English Levels**           | Basic, Intermediate, Advanced, Conversational.                                            |

---

## External role dependencies

| External role                                              | When they intervene                                            |
| -------------------------------------------------------- | ------------------------------------------------------------ |
| **Area Manager**                                    | Authorizes the requisitions that arrive at the dept.              |
| **Hotel Manager Collaborator (GHC)**              | Creates the requisitions in the Hotel module.                   |
| **Inspector** *(Inspection module)*                      | Investigates Blacklist disputes and Red cases.                |
| **Business Developer / BDC** *(Onboarding-Hotel module)* | Receives commercial escalations from the Manager.                |
| **QA Operator** *(QA module)*                         | Issues quality observations on the dept's performance. |
