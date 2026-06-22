---
tags:
  - departamento/qa
aliases:
  - Metrics and KPIs by Department
  - QA KPIs
  - QA Metrics
---

# Metrics and KPIs by Department

Definition of the concrete metrics that each [[QA Operator|QA Operator]] monitors in their assigned department. The [[QA Manager|QA Manager]] is responsible for keeping these definitions up to date and adjusting the thresholds after calibration periods.

> [!info]
> All metrics are derived from data already tracked in the system: status lights, timesheets, requisitions, journals and catalogs. QA does not generate new data; it observes existing data.

## General threshold rule

Each KPI has three evaluation levels:

| Level         | Meaning                                                                 |
| ------------- | --------------------------------------------------------------------------- |
| **On Target** | Expected performance; the department operates within parameters             |
| **At Risk**   | Performance below expected; requires attention and formal observation       |
| **Critical**  | Unacceptable performance; requires immediate corrective action              |

These levels feed the existing [[Quality Indicator|Quality Indicator]]:

- If **any KPI** reaches Critical level → the [[QA Operator|QA Operator]] must propose that the department's [[Quality Indicator|Quality Indicator]] move at least to **Yellow**.
- If **2 or more KPIs** are at Critical level, or the situation persists without improvement → propose escalating the Indicator to **Red**.
- The [[QA Manager|QA Manager]] validates and approves every update of the [[Quality Indicator|Quality Indicator]].

> [!note]
> The thresholds documented here are initial values. The [[QA Manager|QA Manager]] adjusts them after a calibration period based on real operating data.

## Inspection

Assigned operator: Operator 1. Supervised department: [[Inspection/Inspection|Inspection]].

| # | KPI | Formula / calculation | Data source | On Target | At Risk | Critical |
|---|-----|-------------------|-----------------|------|-----------|---------|
| 1 | **Day 1 verification rate** | (Verifications performed on Day 1 / Total collaborators assigned in the period) × 100 | Strong Green → Apple Green transition in [[Collaborator Status Light|Collaborator Status Light]] | ≥ 95% | 85–94% | < 85% |
| 2 | **Day 3 uniform delivery rate** | (Uniforms delivered on Day 3 / Total collaborators that reached Day 3) × 100 | Apple Green → Light Blue transition in [[Collaborator Status Light|Collaborator Status Light]] | ≥ 95% | 85–94% | < 85% |
| 3 | **Average report resolution time** | Average days from when the collaborator enters Red until the [[Inspector]] resolves (to Black or Strong Green) | [[Collaborator Status Light|Collaborator Status Light]] journal | ≤ 3 days | 4–5 days | > 5 days |
| 4 | **Average accident closure time** | Average days from Gray state to card closure (Gray → Strong Green) | [[Core/Modules/Workplace Accident/Workplace Accident\|Workplace Accident]] cards | ≤ 7 days | 8–14 days | > 14 days |
| 5 | **Zone coverage** | Zones with an assigned and active [[Inspector]] / Total [[Core/Catalogs/Zones\|zones]] (6) | Zone assignment by the [[Inspection/Coordinator\|Coordinator]] | 6/6 (100%) | 5/6 (83%) | ≤ 4/6 (67%) |

**Why these KPIs:**
- KPIs 1–2 measure the Inspector's core operational obligations (Day 1 and Day 3).
- KPI 3 measures the response capacity against disputes — the Inspector's investigative role.
- KPI 4 measures the workplace accident life cycle — the Inspector's final responsibility.
- KPI 5 measures structural coverage — without an Inspector in a zone, the other metrics degrade.

## Hotel

Assigned operator: Operator 2. Supervised department: [[Hotel/Hotel|Hotel]].

| # | KPI | Formula / calculation | Data source | On Target | At Risk | Critical |
|---|-----|-------------------|-----------------|------|-----------|---------|
| 1 | **Timely requisition authorization** | (Requisitions authorized within ≤ 24h from creation / Total requisitions created) × 100 | Timestamps of the [[Core/Modules/Status Lights/Requisition Status Light\|Requisition Status Light]] | ≥ 90% | 75–89% | < 75% |
| 2 | **Requisition rejection rate** | (Rejected requisitions / Total requisitions sent for authorization) × 100 | [[Core/Modules/Requisition/Requisition\|Requisition]] journal | ≤ 10% | 11–25% | > 25% |
| 3 | **Punch-in compliance** | (Timesheets with 6 complete punches / Total timesheets in the period) × 100 | [[Timesheet]] | ≥ 90% | 75–89% | < 75% |
| 4 | **Timely QR generation** | (Collaborators with QR generated before Day 1 / Total collaborators assigned) × 100 | QR system, [[Core/Modules/Schedule\|Schedule]] | ≥ 95% | 85–94% | < 85% |
| 5 | **Prolonged Stand-by rate** | (Collaborators in Pink for > 30 days / Total collaborators in Pink) × 100 | [[Collaborator Status Light|Collaborator Status Light]], Pink state timestamps | ≤ 10% | 11–25% | > 25% |

**Why these KPIs:**
- KPI 1 prevents the hotel from becoming a bottleneck in the requisition flow.
- KPI 2 is an inverse quality indicator — high rejection rates suggest poor preparation by the [[Hotel/Supervisor|Supervisor]].
- KPI 3 measures the hotel's operational discipline in attendance recording.
- KPI 4 is a basic enabler — without a QR, collaborators cannot punch in.
- KPI 5 detects collaborators forgotten or abandoned in a waiting state.

## Collaborator

Assigned operator: Operator 3. Supervised scope: [[Collaborator/Collaborator|Collaborator]].

> [!note]
> Collaborator is not a traditional department. The assigned QA Operator monitors aggregate pool metrics and the workforce life cycle, not the performance of an internal team.

| #   | KPI                         | Formula / calculation                                                                                              | Data source                                                           | On Target  | At Risk | Critical |
| --- | --------------------------- | -------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ----- | --------- | ------- |
| 1   | **Absence rate**    | (Total transitions to Purple in the period / Total scheduled shifts) × 100                           | [[Collaborator Status Light|Collaborator Status Light]], [[Core/Modules/Schedule\|Schedule]]         | ≤ 5%  | 6–10%     | > 10%   |
| 2   | **Blacklist rate**       | (Collaborators that moved to Black in the period / Total active collaborators at the start of the period) × 100 | [[Collaborator Status Light|Collaborator Status Light]]                                              | ≤ 2%  | 3–5%      | > 5%    |
| 3   | **Pool health**          | (Collaborators in Strong Green + Yellow / Total collaborators in the [[Collaborator Pool|Collaborator Pool]]) × 100      | [[Collaborator Pool|Collaborator Pool]], [[Collaborator Status Light|Collaborator Status Light]]                   | ≥ 60% | 40–59%    | < 40%   |
| 4   | **Extended Lunch rate** | (Shifts with lunch > 30 min / Total shifts in the period) × 100                                            | Extended Lunch Indicator in [[Timesheet]]                             | ≤ 10% | 11–20%    | > 20%   |
| 5   | **Data completeness**    | (Collaborators with the 3 capture phases complete / Total active collaborators) × 100                        | [[Collaborator/Collaborator\|Collaborator]] capture data (Phases 1–3) | ≥ 95% | 85–94%    | < 85%   |

**Why these KPIs:**
- KPI 1 is the fundamental workforce reliability metric.
- KPI 2 tracks the most severe outcome; a growing rate signals systemic problems.
- KPI 3 measures whether there are enough deployable collaborators to cover demand.
- KPI 4 leverages the Extended Lunch Indicator already existing in the system.
- KPI 5 ensures data integrity — incomplete profiles generate operational gaps.

## Sales

Assigned operator: Operator 4. Supervised department: [[Sales/Sales|Sales]].

| # | KPI | Formula / calculation | Data source | On Target | At Risk | Critical |
|---|-----|-------------------|-----------------|------|-----------|---------|
| 1 | **Conversion rate** | (Hotels that reached Orange / Total hotels prospected in the period) × 100 | [[Core/Modules/Status Lights/Onboarding Status Light\|Onboarding Status Light]] | ≥ 25% | 15–24% | < 15% |
| 2 | **Average onboarding cycle** | Average days from Gray to Orange for converted hotels | Timestamps of the [[Core/Modules/Status Lights/Onboarding Status Light\|Onboarding Status Light]] | ≤ 45 days | 46–75 days | > 75 days |
| 3 | **Stagnation rate** | (Hotels in Brown / Total active hotels in pipeline) × 100 | [[Core/Modules/Status Lights/Onboarding Status Light\|Onboarding Status Light]] | ≤ 10% | 11–20% | > 20% |
| 4 | **Loss rate** | (Hotels in Red or Black without reactivation / Total hotels managed in the period) × 100 | [[Core/Modules/Status Lights/Onboarding Status Light\|Onboarding Status Light]] | ≤ 20% | 21–35% | > 35% |
| 5 | **Successful reactivation rate** | (Hotels reactivated from Red/Black/Brown that advanced at least to Green / Total reactivated hotels) × 100 | [[Core/Modules/Status Lights/Onboarding Status Light\|Onboarding Status Light]] journal | ≥ 40% | 25–39% | < 25% |

**Why these KPIs:**
- KPI 1 is the main effectiveness metric of the commercial team.
- KPI 2 ensures deals do not drag on indefinitely.
- KPI 3 detects blockages in the pipeline that the [[Sales/Roles/Business Developer Coordinator|BDC]] must resolve.
- KPI 4 tracks losses — a growing rate may indicate market misalignment or poor prospect selection.
- KPI 5 measures the team's capacity to recover stalled opportunities.

## Recruitment

Assigned operator: Operator 5. Supervised department: [[Recruitment/Recruitment|Recruitment]].

| #   | KPI                                        | Formula / calculation                                                                                                                                   | Data source                                                                                         | On Target  | At Risk | Critical |
| --- | ------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- | ----- | --------- | ------- |
| 1   | **Total requisition coverage**       | (Requisitions that ended in Light Blue / Total requisitions closed in the period) × 100                                                  | [[Core/Modules/Status Lights/Requisition Status Light\|Requisition Status Light]]                             | ≥ 85% | 70–84%    | < 70%   |
| 2   | **Average requisition take-up time** | Average hours from authorization to take-up by the [[Recruiter|Recruiter]]                                                                                 | Timestamps of the [[Core/Modules/Status Lights/Requisition Status Light\|Requisition Status Light]]              | ≤ 8h  | 9–24h     | > 24h   |
| 3   | **Timeout auto-assignment rate**    | (Requisitions auto-assigned at 24h / Total authorized requisitions) × 100                                                                 | Auto-assignment system                                                                              | ≤ 5%  | 6–15%     | > 15%   |
| 4   | **Timeout escalation rate**         | (Requisitions escalated to the [[Recruitment/Recruiters Group Leader\|Group Leader]] by timeout / Total requisitions in process) × 100 | Escalations according to the [[Core/Modules/Status Lights/Requisition Urgency Status Light\|Urgency Status Light]] | ≤ 10% | 11–20%    | > 20%   |
| 5   | **Blacklist check compliance**  | (Recruitments with a recorded [[Core/Modules/Blacklist\|Blacklist]] check / Total recruitments in the period) × 100                       | [[Core/Modules/Blacklist\|Blacklist]] check log                                               | 100%  | 95–99%    | < 95%   |
| 6   | **Pool intake rate**                | (Collaborators approved and added to the [[Collaborator Pool|Collaborator Pool]] / Total candidates interviewed) × 100                                       | [[Core/Modules/Collaborator Pool\|Collaborator Pool]], interview data                     | ≥ 60% | 45–59%    | < 45%   |

**Why these KPIs:**
- KPI 1 is the department's core deliverable — covering requisitions completely.
- KPIs 2–3 measure the proactivity in requisition take-up of the Self-Pick model.
- KPI 4 detects cases where the [[Recruiter|Recruiter]] could not find a match within the urgency window.
- KPI 5 is a compliance metric — the Blacklist check is a documented obligation.
- KPI 6 measures the health of the recruitment funnel — very low values indicate poor source selection or excessive filtering.

## Customer Service

Assigned operator: Operator 6. Supervised department: [[Customer Service/Customer Service|Customer Service]].

> [!note]
> The Customer Service specific KPIs will be defined after an initial operating period. The [[QA Manager|QA Manager]] will establish the thresholds once real data on case volume, resolution times and hotel satisfaction exists.

## Related

- [[QA/QA|QA]]
- [[QA Manager|QA Manager]]
- [[QA Operator|QA Operator]]
- [[QA/QA Dashboard|QA Dashboard]]
- [[Core/Modules/Status Lights/Quality Indicator|Quality Indicator]]
- [[Collaborator Status Light|Collaborator Status Light]]
- [[Core/Modules/Status Lights/Requisition Status Light|Requisition Status Light]]
- [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]]
- [[Core/Modules/Status Lights/Requisition Urgency Status Light|Requisition Urgency Status Light]]
- [[Core/Modules/Status Lights/Requisition Positions Status Light|Requisition Positions Status Light]]
- [[Business Rules|Business Rules]]
