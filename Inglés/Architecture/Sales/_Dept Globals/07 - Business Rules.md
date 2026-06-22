---
tags:
  - arquitectura
  - departamento/ventas
aliases:
  - Sales Business Rules
---

# 8. BUSINESS RULES — SALES DEPARTMENT

---

| ID          | Rule                                                 | Description                                                                                                                                                                                                                                            |
| ----------- | ---------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **RR-V-01** | Conversion exclusive to the BDC                      | Only the [[Sales/Roles/Business Developer Coordinator\|BDC]] can approve the conversion of a prospect into a client (status Pink → Orange). The BD can never approve.                                                                                |
| **RR-V-02** | Conversion precondition — Hotel User                 | Before approving the conversion, the BDC must create the [[Sales/Hotel Onboarding/Concepts/Hotel User\|Hotel User]] in the system. Without this step, the system blocks the "Approve conversion" button.                                     |
| **RR-V-03** | Automatic Conversion Trigger                         | Upon approving the conversion, the system executes **automatically and in parallel** 3 actions: (1) welcome email to the hotel, (2) notification to the assigned BD, (3) the hotel disappears from the prospects list.                                |
| **RR-V-04** | Stall unblock (Brown) exclusive to the BDC           | The **Brown** status is an unblocking bridge. Only the BDC investigates the cause of the stall, provides a solution and reactivates.                                                                                                                  |
| **RR-V-05** | Paused client management (Black) exclusive to the BDC | When an active client stops operating (closure, change of management, pause, dispute), it moves to **Black**. Management and possible reactivation are exclusive to the BDC.                                                                          |
| **RR-V-06** | Rejection (Red) management by the BD                 | When a prospect rejects the proposal, it moves to **Red**. The BD manages the reactivation if applicable.                                                                                                                                            |
| **RR-V-07** | Reactivations always return to Light Blue            | Reactivating from **Red, Black or Brown** always returns the hotel to **Light Blue** (data already captured, active contact) — never to Gray.                                                                                                         |
| **RR-V-08** | Orange enables requisition generation                | The **Orange** status is the **only** one that enables the hotel to generate requisitions in the Hotel module. Before Orange, the hotel is only a prospect.                                                                                          |
| **RR-V-09** | Personalized Proposal in Green                       | The [[Sales/Hotel Onboarding/Concepts/Personalized Proposal\|Personalized Proposal]] is drafted and sent exclusively in **Green** status. It is adjusted or resumed from **Brown** (with the BDC's unblock).                                     |
| **RR-V-10** | T&C — mandatory content                              | The [[Sales/Hotel Onboarding/Concepts/Terms and Conditions Document\|Terms and Conditions Document]] must contain: **Pay rate, Bill rate, Overtime, Holidays, Calendar**. Without these fields, Pink cannot be started.                       |
| **RR-V-11** | Status change traceability                           | Every status change in the [[Core/Modules/Status Lights/Onboarding Status Light\|Onboarding Status Light]] is recorded with: **date, owner and comment**. There are no silent changes.                                                                       |
| **RR-V-12** | Post-Orange: BD and BDC as commercial contacts       | When the hotel reaches Orange, BD and BDC stop operating and remain as **commercial contacts** (they do not edit the hotel or its requisitions). The hotel moves to [[Recruitment/Recruitment\|Recruitment]] and [[Inspection/Inspection\|Inspection]]. |
| **RR-V-13** | QA observes but does not operate                     | A [[QA/QA Operator\|QA Operator]] is assigned to the Sales department to measure and report. It does NOT carry out operation.                                                                                                                      |
| **RR-V-14** | Quality escalation to management                     | If the department's [[Core/Modules/Status Lights/Quality Indicator\|Quality Indicator]] enters **Red** without improvement after notification, the QA Manager escalates to management.                                                                 |
| **RR-V-15** | Contract results from a successful Pink closing      | The [[Core/Modules/Contrato\|Contract]] is generated upon approval of the conversion. Mandatory input: the T&C Document validated by the BDC.                                                                                                         |

---

## Cross-references

- [[Sales/Sales Rules|Sales Rules]] — operational source of truth
- [[Business Rules|Business Rules]] — general system summary
- [[Sales/Hotel Onboarding/Hotel Onboarding|Hotel Onboarding]]
- [[Sales/Hotel Onboarding/Onboarding Flow|Onboarding Flow]]
- [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]]
- [[Core/Modules/Contrato|Contract]]
