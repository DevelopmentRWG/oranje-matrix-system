---
tags:
  - arquitectura
  - departamento/ventas
aliases:
  - Sales Dependencies
---

# 9. DEPENDENCIES — SALES DEPARTMENT

---

## Internal dependencies (other modules of the Oranje system)

| Dependency                | Description                                                                                                            |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| **Hotel Module**          | Destination of the onboarding. Upon reaching Orange, the hotel is enabled to generate requisitions from the Hotel module. |
| **Recruitment Module**    | Receives the active client hotel (post-Orange) to start the operational cycle of covering requisitions.               |
| **Inspection Module**     | When the hotel is activated, the system automatically assigns an Inspector according to the hotel's zone.             |
| **Contract Module**       | Artifact generated upon a successful Pink closing. Mandatory input: T&C Document validated by the BDC.                |
| **Schedule Module**       | Indirectly — the Contract configures the structure of the hotel's weekly Schedule (start and end of week, holidays). |
| **QA Module**             | Fixed QA operator assigned to the department. Metrics and Quality Indicator. QA observes, measures and provides feedback without operating. |
| **Collaborator Pool**     | Indirect — only becomes relevant post-Orange when Recruitment starts to cover.                                       |

---

## External dependencies (systems or apps outside the module)

| Dependency                                     | Description                                                                                                   |
| ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| **BD App (Mobile)**                            | The BD operates from mobile during cold visits and field follow-ups (RNF-V-04).                              |
| **Email Marketing / Transactional System**     | Sends an automatic welcome email to the hotel after the conversion (Trigger — RI-V-05).                       |
| **Notification System**                        | Sends automatic notifications to BD and BDC upon relevant events (status changes, conversion, alerts).        |
| **Audit / Logs System**                        | Records mandatory traceability of all status changes (RR-V-11, RNF-V-03).                                     |

---

## Catalog dependencies (system configuration)

| Catalog                             | Description                                                                                            |
| ----------------------------------- | ----------------------------------------------------------------------------------------------------- |
| **Commercial Zones / Routes**       | Defines each BD's territory and the BDC's scope. Maintained by the Administrator.                     |
| **Proposal Templates**              | Base templates the BD can customize when drafting a Personalized Proposal.                            |
| **T&C Templates**                   | Base structure of the T&C Document with mandatory fields (Pay/Bill/Overtime/Holidays/Calendar).       |
| **Onboarding Status Light States**  | Status catalog: Gray, Light Blue, Green, Yellow, Pink, Orange, Red, Black, Brown.                     |
| **Status change reasons**           | Catalog for the reason selector when changing status (rejection, stall, pause, etc.).                 |

---

## External role dependencies

| External role                                      | When it intervenes                                                                       |
| -------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| **[[Hotel/Area Manager\|Area Manager]]**        | Receives the active system post-Orange; creates requisitions.                            |
| **[[Hotel/Supervisor\|Hotel Supervisor]]**         | Receives the active system post-Orange; creates requisitions.                            |
| **[[Recruiter\|Recruiter]]**                     | Receives the active hotel to start covering requisitions.                                |
| **[[Inspector\|Inspector]]**                       | Automatically assigned to the hotel upon activation (by zone).                           |
| **[[QA/QA Operator\|QA Operator]]**             | Measures and provides feedback on the Sales department's performance.                    |
| **Hotel client**                                   | Receives a welcome email upon activation; platform user via Hotel User.                  |

---

## Status-light dependencies

| Status Light                                                              | Use in the Sales department                                                  |
| ------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| **[[Core/Modules/Status Lights/Onboarding Status Light\|Onboarding Status Light]]** | Backbone of the department. Defines each stage of the process (Gray → Orange). |
| **[[Core/Modules/Status Lights/Quality Indicator\|Quality Indicator]]**    | Visibility for BDC and QA. If it enters persistent Red, it escalates to management. |
