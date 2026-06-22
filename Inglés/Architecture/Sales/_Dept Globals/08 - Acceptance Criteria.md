---
tags:
  - arquitectura
  - departamento/ventas
aliases:
  - Sales Acceptance Criteria
---

# ✅ ACCEPTANCE CRITERIA — SALES DEPARTMENT

---

| #           | Criterion                                                                                                                                                                                |
| ----------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **AC-V-01** | Only the BDC can approve the conversion of a prospect into a client (RR-V-01).                                                                                                           |
| **AC-V-02** | The system blocks the "Approve conversion" button if the previously created Hotel User does not exist (RR-V-02).                                                                        |
| **AC-V-03** | Upon approving the conversion, the system executes automatically and in parallel: welcome email + notification to the BD + removal of the prospect from the Pipeline, in under 1 min (RR-V-03). |
| **AC-V-04** | The prospect's status automatically moves to Orange after a successful conversion (RR-V-08).                                                                                            |
| **AC-V-05** | The hotel can only generate requisitions when it reaches Orange in the Onboarding Status Light (RR-V-08).                                                                               |
| **AC-V-06** | Only the BDC can unblock a stall (Brown) and reactivate the prospect (RR-V-04).                                                                                                         |
| **AC-V-07** | Only the BDC can manage paused clients (Black) (RR-V-05).                                                                                                                               |
| **AC-V-08** | The BD manages rejections (Red) and can reactivate the prospect.                                                                                                                        |
| **AC-V-09** | Every reactivation (from Red, Black or Brown) returns the prospect to Light Blue, never to Gray (RR-V-07).                                                                              |
| **AC-V-10** | The T&C Document must contain: Pay rate, Bill rate, Overtime, Holidays, Calendar. Without these fields, Pink cannot be started (RR-V-10).                                               |
| **AC-V-11** | The Personalized Proposal is drafted and sent exclusively in Green status (RR-V-09).                                                                                                    |
| **AC-V-12** | Every status change is recorded with date, owner and comment (RR-V-11). There are no silent changes.                                                                                    |
| **AC-V-13** | Post-Orange, BD and BDC can view the active client but can NOT modify the hotel or its requisitions (RR-V-12).                                                                          |
| **AC-V-14** | The welcome email uses the configured template and reaches the hotel in under 1 min (RI-V-05).                                                                                          |
| **AC-V-15** | The assigned BD receives a push notification in under 1 min after the conversion.                                                                                                       |
| **AC-V-16** | The system notifies the corresponding role in under 1 min after a relevant event (status changes, etc.).                                                                               |
| **AC-V-17** | The interface is responsive: BDC from 7" (Desktop / Tablet); BD from 5" (mobile-first, RNF-V-04).                                                                                       |
| **AC-V-18** | The monthly availability of the module is 99.5% (RNF-V-02).                                                                                                                             |
| **AC-V-19** | Each status change includes a reason selector + mandatory comment.                                                                                                                      |
| **AC-V-20** | The Contract is generated automatically upon a successful Pink closing, using the T&C validated by the BDC as input (RR-V-15).                                                          |
| **AC-V-21** | The BDC can view ALL prospects in their zone / routes; the BD only sees those in their assigned territory.                                                                              |
