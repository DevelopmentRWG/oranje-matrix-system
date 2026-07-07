---
tags:
  - arquitectura
  - rol/lider-de-grupo
aliases:
  - Group Leader PRD
---

# PRODUCT REQUIREMENTS DOCUMENT
## PRD – RECRUITERS GROUP LEADER

**Personnel Management System · Group Leader Role**

---

| Field                | Content                                                          |
| -------------------- | ---------------------------------------------------------------- |
| **PRD ID**           | PRD-RECL-03                                                      |
| **User Story**       | HU-RECL-03                                                       |
| **Department**       | Recruitment                                                      |
| **Functionality**    | Operate as a Recruiter + supervise group + report to the Manager |
| **Main Actor**       | Recruiters Group Leader                                          |
| **Device**           | Web – Desktop / Tablet                                           |
| **Status**           | In definition                                                   |
| **Version**          | 1.0                                                              |

---

## Objective

Allow the Group Leader to cover requisitions (just like a Recruiter) and simultaneously supervise the performance of the Recruiters under their charge, monitor their workload, handle first-level incidents and send formal reports to the Manager.

---

## General Flow

**Take requisition → Cover as a Recruiter → Supervise group → Generate report → Send to the Manager**

---

## Scope

### What this role includes

- Taking requisitions from the tray through the collaborative Self-Pick model (RR-01 / RR-15).
- Joining a requisition already taken by another Recruiter without displacing her (RF-39).
- Executing the full operational Recruiter flow: interviewing candidates, creating a collaborator (Phase 1), validating the app registration (Phase 2), assigning to hotel and assigning to the Schedule.
- Consulting the Blacklist before assigning (RF-11) and adding to Blacklist when applicable (RF-12).
- Approving the coverage closure of a requisition when it reaches 100% (RF-05).
- Viewing the Recruiters in the group with individual metrics (RF-22 / RF-23).
- Viewing the detailed workload of each Recruiter in the group (RF-36).
- Reassigning a requisition from one Recruiter in the group to another (RF-37).
- Marking the availability of Recruiters in the group (active / on leave) (RF-38).
- Viewing individual coverage (RF-26) and coverage by zone (RF-27).
- Viewing active recruiters on a requisition (RF-40) and the requisition history / timeline (RF-41).
- Generating the group report (RF-24) and formally sending it to the Manager (RF-25).
- Handling first-level incidents for the group and escalating to the Manager when beyond scope.

### What this role does NOT include

- Does not supervise the entire department — only the group of Recruiters assigned to the Leader.
- Does not resolve Blacklist disputes — that is the responsibility of the Blacklist Inspector.
- Does not remove collaborators from the Blacklist — that action requires Manager authorization.
- Does not generate global department reports — reports only on the assigned group to the Manager.
- Does not escalate cases directly to Management — the escalation channel is always the Manager.
- Does not assign or reassign Recruiters between groups — that is the Manager's authority.
- There is no chat or direct messaging functionality in the platform — communication is handled through notifications, structured requests, and the requisition log.

---

## Restrictions

| Restriction | Description |
| ----------- | ----------- |
| **Blacklist — consult and add only** | The Leader may consult the Blacklist and add collaborators, but cannot remove entries or resolve disputes. Disputes are handled by the Blacklist Inspector; removals, by the Manager. |
| **Permanent veto** | A collaborator on the Blacklist with a permanent veto cannot be assigned under any circumstance, regardless of requisition urgency. |
| **No "Released" status** | The collaborative model does not use a "Released" status. The flow is: join the requisition / leave it. If all recruiters leave, the requisition returns to "Authorized". |
| **Closure approval only at 100%** | The RF-05 action (mark as covered) is only available when the requisition reaches exactly 100% coverage. |
| **Reassignment within group only** | RF-37 allows reassigning a requisition only among the Recruiters in the Leader's own group. Moving requisitions between groups requires Manager intervention. |
| **Report directed to the Manager** | The only recipient of the formal report (RF-25) is the Recruitment Manager. The Leader does not send reports directly to Management. |
| **No chat in the platform** | There is no direct messaging functionality. Incidents and escalations are recorded through notifications and notes in the requisition log. |
| **Device** | Desktop / Tablet. No mobile operation interface in this phase. |

---

## Success Criteria / Metrics

| Metric | Description |
| ------ | ----------- |
| **Group coverage** | Percentage of requisitions assigned to the group that reached 100% coverage in the period. |
| **Average coverage time** | Average time from when a requisition moves to "In progress" to when its closure is approved (RF-05). |
| **Workload per Recruiter** | Number of active requisitions per Recruiter in the group. Should remain balanced. |
| **Cases escalated to Manager** | Number of incidents the Leader could not resolve at first level and escalated to the Manager. Goal: minimize unnecessary escalations. |
| **Reports sent to Manager** | Frequency and timeliness of group report submissions (RF-25). |
| **Individual metrics** | Requisitions covered, average time, and successful assignment rate per Recruiter in the group (RF-23). |
| **Reassignments performed** | Number of reassigned requisitions (RF-37) as an indicator of active workload management. |

---

## User Stories

### HU-LG-01 — Approve coverage closure (RF-05)

**As** a Group Leader,  
**I want** to mark a requisition as covered when its percentage reaches 100%,  
**so that** I can formally approve the closure and notify the Manager without requiring their direct intervention.

**Acceptance criteria:**
- The action is only available when coverage is exactly 100%.
- Upon confirmation, the requisition status changes to "Covered" and a notification is sent to the Manager.
- The event is recorded in the requisition history / timeline with date and actor.

---

### HU-LG-02 — View and manage the Recruiters group (RF-22 / RF-36 / RF-38)

**As** a Group Leader,  
**I want** to view the list of Recruiters in my group with their current status and workload, access each one's detail, and mark their availability,  
**so that** I have consolidated visibility of the team and can redistribute work when necessary.

**Acceptance criteria:**
- List view with name, status (Active / On Leave) and number of active requisitions per Recruiter.
- Clicking a Recruiter opens the detail view: KPIs, workload, and history.
- RF-36: modal with the Recruiter's requisitions currently in progress.
- RF-38: action to change the Recruiter's status (Active ↔ On Leave).

---

### HU-LG-03 — Individual metrics per Recruiter (RF-23)

**As** a Group Leader,  
**I want** to view individual performance metrics for each Recruiter in my group,  
**so that** I can identify who needs support, who is overloaded, and prepare the report for the Manager.

**Acceptance criteria:**
- Visible metrics: requisitions covered, average coverage time, successful assignment rate.
- Data corresponds to the period defined by the active filter.
- The view is read-only; it does not allow editing the Recruiter's records.

---

### HU-LG-04 — Reassign requisition to another Recruiter (RF-37)

**As** a Group Leader,  
**I want** to move a requisition from one Recruiter in my group to another,  
**so that** I can balance the team's workload when a Recruiter is overloaded or unavailable.

**Acceptance criteria:**
- Reassignment is only possible among Recruiters in the Leader's own group.
- The reassignment event is recorded in the requisition history with actor and date.
- The source Recruiter loses the requisition and the target Recruiter receives it in her tray.
- The requisition's traffic light status does not go back.

---

### HU-LG-05 — Join a requisition already taken (RR-15 / RF-39)

**As** a Group Leader,  
**I want** to join as a participating recruiter in a requisition that another Recruiter has already taken,  
**so that** I can support collaborative coverage without displacing existing recruiters or restarting the process.

**Acceptance criteria:**
- Upon joining, I am registered as a participant in the requisition.
- No existing recruiter is displaced and the traffic light does not go back.
- I can leave the requisition at any time; if I am the last one to leave, it returns to "Authorized".
- The event is recorded in the requisition timeline.

---

### HU-LG-06 — View coverage by zone (RF-27)

**As** a Group Leader,  
**I want** to view the coverage status of requisitions grouped by zone or hotel,  
**so that** I can identify zones with low coverage and prioritize Recruiter assignment where it is most needed.

**Acceptance criteria:**
- Coverage view broken down by zone / hotel for the group's active requisitions.
- Visual indicator of the coverage percentage per zone.
- Accessible from the group dashboard.

---

### HU-LG-07 — Generate and send report to Manager (RF-24 / RF-25)

**As** a Group Leader,  
**I want** to generate a consolidated performance report for my group and formally send it to the Manager,  
**so that** I fulfill the reporting chain and give visibility of the team's status without requiring the Manager to consult it manually.

**Acceptance criteria:**
- RF-24: report preview with group metrics and charts before sending.
- RF-25: formal send action that generates a Manager notification with the report attached.
- The report is exportable in CSV or PDF format.
- Only the Recruitment Manager is the recipient of the formal submission.
