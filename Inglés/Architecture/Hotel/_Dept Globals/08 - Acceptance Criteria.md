---
tags:
  - arquitectura
  - departamento/hotel
aliases:
  - Hotel Acceptance Criteria
---

# ✅ ACCEPTANCE CRITERIA — HOTEL DEPARTMENT

---

| #          | Criterion                                                                                                                                       |
| ---------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| **AC-H-01** | The hotel can only create requisitions when it reaches Orange status in the Onboarding Status Light (RR-H-01).                                 |
| **AC-H-02** | The requisition creation form cannot be sent to authorization without at least 1 registered position (RR-H-03).                                |
| **AC-H-03** | The system blocks authorization if the role is not Area Manager, showing: *"Only the hotel manager can authorize the requisition"* (RR-H-02). |
| **AC-H-04** | The requisition number follows the format `YYYYMMDDHHMM + Check code` and is generated automatically upon creation (RR-H-04).                  |
| **AC-H-05** | When authorizing the requisition, the system automatically calculates urgency per position (>120h Green, 72-120h Yellow, <72h Red) (RR-H-05). |
| **AC-H-06** | When authorizing the requisition, the system automatically assigns the Inspector according to the hotel's zone in under 30s (RR-H-06).         |
| **AC-H-07** | When authorizing the requisition, the positions appear in the hotel's weekly Schedule in under 30s (RI-H-02).                                  |
| **AC-H-08** | The authorized requisition reaches the Recruitment inbox (Self-Pick) in under 30s (RI-H-01).                                                   |
| **AC-H-09** | If the requisition has no positions upon leaving the editor, it is physically deleted without journal (RR-H-07).                               |
| **AC-H-10** | When deleting a requisition with positions, each position changes to Purple state with an individual journal (RR-H-08).                        |
| **AC-H-11** | Only the Area Manager can generate / renew the Timesheet QR (RR-H-09).                                                                        |
| **AC-H-12** | The generated QR is valid immediately; collaborators can punch instantly.                                                                      |
| **AC-H-13** | Only the Area Manager can report a collaborator (Red); the action notifies the Inspector and starts the investigation (RR-H-10).             |
| **AC-H-14** | Area Manager and Supervisor can put on Stand-by (Pink); the collaborator remains without Schedule or Timesheet (RR-H-11).                     |
| **AC-H-15** | The Extended Lunch Indicator is NOT visible to Hotel roles (RR-H-15).                                                                          |
| **AC-H-16** | The Lunch deduction applies to all collaborators: Lunch <30 min → 30 min minimum; no punch → 30 min auto-deduction (RR-H-16).                  |
| **AC-H-17** | The Timesheet Compliance Indicator is calculated per collaborator and per workday (Green / Yellow / Red).                                      |
| **AC-H-18** | The Supervisor can report accidents in scenarios A and B; the collaborator changes to Gray in the Collaborator Status Light (RR-H-19, RR-H-20). |
| **AC-H-19** | Every punch correction by the Area Manager is kept in an auditable log with author, date and mandatory reason (RNF-H-03).                     |
| **AC-H-20** | The General Manager cannot authorize requisitions; only comment and escalate (RR-H-14).                                                        |
| **AC-H-21** | The system notifies the corresponding role in under 1 minute after a relevant event (Notifications).                                           |
| **AC-H-22** | The interface is responsive: Area Manager and General Manager from 7"; Supervisor from 5" (mobile, RNF-H-04).                                |
| **AC-H-23** | The module's monthly availability is 99.5% (RNF-H-02).                                                                                         |
| **AC-H-24** | Every state change in a requisition or collaborator is recorded in the journal with date, author and reason.                                  |
| **AC-H-25** | When rejecting a requisition, the Area Manager's remarks are visible to the Supervisor in the detail.                                         |
