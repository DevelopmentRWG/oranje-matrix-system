---
tags:
  - arquitectura
  - departamento/hotel
aliases:
  - Hotel Business Rules
---

# 8. BUSINESS RULES — HOTEL DEPARTMENT

---

| ID         | Rule                                             | Description                                                                                                                                                                                                                       |
| ---------- | ------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **RR-H-01** | Hotel enablement                                | The hotel **can only generate requisitions** when it reaches **Orange** status in the [[Core/Modules/Status Lights/Onboarding Status Light\|Onboarding Status Light]]. Before that it is a commercial prospect managed by Sales.            |
| **RR-H-02** | Security layer — shared authorization            | The **Area Manager** or the **General Manager** can authorize a requisition. If the Supervisor tries to do it, the system blocks with: *"Only the hotel manager can authorize the requisition"*.                                  |
| **RR-H-03** | Minimum position to authorize                    | A requisition must have **at least 1 registered position** to be authorized. Without positions, the system blocks with: *"It has no registered positions, register at least one position and try again"*.                          |
| **RR-H-04** | Automatic requisition numbering                  | Format `YYYYMMDDHHMM + Check code (2 alphanumeric)`. Example: `202604081632V1`. Same format for workplace accident cards.                                                                                                          |
| **RR-H-05** | Automatic urgency calculation upon authorization | Per position, according to the [[Requisition Urgency Status Light\|Requisition Urgency Status Light]]: `>120h` → Strong Green (Normal), `72-120h` → Yellow (Medium), `<72h` → Red (Urgent).                                      |
| **RR-H-06** | Automatic Inspector assignment by zone           | When a requisition is authorized, the system automatically assigns the corresponding [[Inspector]] according to the hotel's zone.                                                                                                 |
| **RR-H-07** | Physical deletion of requisition without positions | If a requisition has no positions upon leaving the editor, an **automatic physical deletion** is executed without journal.                                                                                                       |
| **RR-H-08** | Cross-cutting Purple state on deletion           | When deleting a requisition with positions, the **Purple** state is reached in the Requisition Status Light from any previous state. Each position also changes to Purple with an individual journal.                             |
| **RR-H-09** | QR generation (Area Manager + General Manager)   | Both the Area Manager and the General Manager can generate / renew the Timesheet **QR** code so collaborators can punch.                                                                                                          |
| **RR-H-10** | Shared collaborator report (Red)                 | The **3 Hotel roles** (Supervisor, Area Manager, General Manager) can report a collaborator (**Red - Reported** state in [[Collaborator Status Light\|Collaborator Status Light]]). This action starts the [[Inspector]]'s investigation. |
| **RR-H-11** | Shared Stand-by (Pink)                           | The **3 Hotel roles** can put a collaborator on **Stand-by (Pink)**. The collaborator remains without Schedule or Timesheet and cannot punch until the state is changed.                                                          |
| **RR-H-12** | Restricted access to the requisitions module     | The **General Manager**, the **Area Manager** and the **Supervisor** have access to the requisitions module. Users without access receive the message: *"You do not have access"*.                                              |
| **RR-H-13** | Support for simple and extended hierarchy        | The system supports two models: **Simple** (General Manager also operates as Area Manager → SUP → Collaborators) and **Extended** (General Manager → Area Manager per department → Supervisor → Collaborators).                    |
| **RR-H-14** | General Manager always exists                    | The General Manager **always exists**, in both hierarchies. In simple, it also operates as Area Manager (same person, two roles). In extended, it supervises the Area Managers of each department.                                |
| **RR-H-15** | Extended Lunch Indicator restricted              | The 3 Hotel roles **do NOT have access** to the Extended Lunch Indicator. It is exclusive to Oranje internal roles ([[Inspector]], [[Inspection/Coordinator\|Coordinator]], [[Recruitment Manager\|Recruitment Manager]]).    |
| **RR-H-16** | Lunch deduction (minimum 30 min)                 | Applies to all collaborators on each workday. Lunch <30 min → 30 min (mandatory minimum); Lunch ≥30 min → actual time; no Lunch punch → 30 min (auto-deduction). After 6h continuous they must take Lunch.                          |
| **RR-H-17** | Workday and work week                            | Daily workday: **8 hours**. Week: 5 working days + 2 rest days. Weekly gross: 40 hours. Payable net: **37.5 hours** (40 − 30 min of Lunch × 5 workdays).                                                                            |
| **RR-H-18** | Position lifecycle                               | Each position has a start date but **no defined end date**. The position ends when any of the 3 Hotel roles puts the collaborator on **Stand-by (Pink)**.                                                                        |
| **RR-H-19** | Accident reporting — shared                      | The **3 Hotel roles** (Supervisor, Area Manager, General Manager) can report workplace accidents. **Scenario A** (collaborator reports from the app → simultaneous signal to the 3 + Inspector → the closest one arrives and captures on site); **Scenario B** (any Hotel role detects first → creates card → signal to the Inspector). |
| **RR-H-20** | Gray state on accident                           | In both accident scenarios, the collaborator changes to **Gray (In Accident)** state in the [[Collaborator Status Light\|Collaborator Status Light]], which protects them from the 3-absences rule while it is investigated.        |

---

## Cross-references

- [[Hotel/Hotel Rules|Hotel Rules]] — operational source of truth
- [[Business Rules|Business Rules]] — general system summary
- [[Core/Modules/Requisition/Requisition|Requisition]]
- [[Core/Modules/Schedule|Schedule]]
- [[Timesheet]]
- [[Core/Modules/Workplace Accident/Workplace Accident Flow|Workplace Accident Flow]]
- [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]]
- [[Requisition Status Light|Requisition Status Light]]
- [[Collaborator Status Light|Collaborator Status Light]]
