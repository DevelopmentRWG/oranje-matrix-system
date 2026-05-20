---
tags:
  - department/qa
aliases:
  - Metrics and KPIs by Department
  - QA KPIs
  - QA Metrics
---

# Metrics and KPIs by Department

Definition of the specific metrics that each [[Operador de QA]] monitors in their assigned department. The [[Manager de QA]] is responsible for keeping these definitions up to date and adjusting thresholds after calibration periods.

> [!info]
> All metrics are derived from data already tracked in the system: status indicators, timesheets, requisitions, journals, and catalogs. QA does not generate new data; it observes existing data.

## General Threshold Rule

Each KPI has three evaluation levels:

| Level | Meaning |
| --- | --- |
| **Target** | Expected performance; the department operates within parameters |
| **At Risk** | Performance below expected; requires attention and a formal observation |
| **Critical** | Unacceptable performance; requires immediate corrective action |

These levels feed the existing [[Indicador de Calidad]]:

- If **any KPI** reaches the Critical level → the [[Operador de QA]] must propose that the department's [[Indicador de Calidad]] move to at least **Yellow**.
- If **2 or more KPIs** are at the Critical level, or the situation persists without improvement → propose escalating the Indicator to **Red**.
- The [[Manager de QA]] validates and approves all updates to the [[Indicador de Calidad]].

> [!note]
> The thresholds documented here are initial values. The [[Manager de QA]] adjusts them after a calibration period based on real operational data.

## Inspection

Assigned operator: Operator 1. Supervised department: [[Inspección/Inspección|Inspection]].

| # | KPI | Formula / Calculation | Data Source | Target | At Risk | Critical |
|---|-----|-------------------|-----------------|------|-----------|---------|
| 1 | **Day 1 verification rate** | (Verifications performed on Day 1 / Total associates assigned in the period) × 100 | White → Apple Green transition in [[Semáforo del Colaborador]] | ≥ 95% | 85–94% | < 85% |
| 2 | **Day 3 uniform delivery rate** | (Uniforms delivered on Day 3 / Total associates who reached Day 3) × 100 | Apple Green → Light Blue transition in [[Semáforo del Colaborador]] | ≥ 95% | 85–94% | < 85% |
| 3 | **Average report resolution time** | Average days from when the associate enters Red until the [[Inspector]] resolves (to Black or Dark Green) | Journal of [[Semáforo del Colaborador]] | ≤ 3 days | 4–5 days | > 5 days |
| 4 | **Average accident closure time** | Average days from Gray status until card closure (Gray → Dark Green) | [[Core/Módulos/Accidente Laboral/Accidente Laboral\|Workplace Accident]] cards | ≤ 7 days | 8–14 days | > 14 days |
| 5 | **Zone coverage** | Zones with an assigned and active [[Inspector]] / Total [[Core/Catálogos/Zonas\|zones]] (6) | Zone assignments by the [[Inspección/Coordinador\|Coordinator]] | 6/6 (100%) | 5/6 (83%) | ≤ 4/6 (67%) |

**Why these KPIs:**
- KPIs 1–2 measure the Inspector's core operational obligations (Day 1 and Day 3).
- KPI 3 measures responsiveness to disputes — the Inspector's investigative role.
- KPI 4 measures the workplace accident lifecycle — the Inspector's final responsibility.
- KPI 5 measures structural coverage — without an Inspector in the zone, all other metrics degrade.

## Hotel

Assigned operator: Operator 2. Supervised department: [[Hotel/Hotel|Hotel]].

| # | KPI | Formula / Calculation | Data Source | Target | At Risk | Critical |
|---|-----|-------------------|-----------------|------|-----------|---------|
| 1 | **Timely requisition authorization** | (Requisitions authorized in ≤ 24h from creation / Total requisitions created) × 100 | Timestamps of [[Core/Módulos/Semáforos/Semáforo de Requisición\|Requisition Status Indicator]] | ≥ 90% | 75–89% | < 75% |
| 2 | **Requisition rejection rate** | (Rejected requisitions / Total requisitions sent for authorization) × 100 | Journal of [[Core/Módulos/Requisicion/Requisición\|Requisition]] | ≤ 10% | 11–25% | > 25% |
| 3 | **Punch compliance** | (Timesheets with 6 complete punches / Total timesheets in the period) × 100 | [[Timesheet]] | ≥ 90% | 75–89% | < 75% |
| 4 | **Timely QR generation** | (Associates with QR generated before Day 1 / Total assigned associates) × 100 | QR system, [[Core/Módulos/Schedule\|Schedule]] | ≥ 95% | 85–94% | < 85% |
| 5 | **Extended Stand-by rate** | (Associates in Pink for > 30 days / Total associates in Pink) × 100 | [[Semáforo del Colaborador]], Pink status timestamps | ≤ 10% | 11–25% | > 25% |

**Why these KPIs:**
- KPI 1 prevents the hotel from being a bottleneck in the requisition flow.
- KPI 2 is an inverse quality indicator — high rejection rates suggest poor preparation by the [[Hotel/Supervisor|Supervisor]].
- KPI 3 measures the hotel's operational discipline in attendance recording.
- KPI 4 is a basic enabler — without a QR code, associates cannot punch in.
- KPI 5 detects forgotten or abandoned associates in a waiting status.

## Associate

Assigned operator: Operator 3. Supervised scope: [[Colaborador/Colaborador|Associate]].

> [!note]
> Associate is not a traditional department. The assigned QA Operator monitors aggregate pool metrics and workforce lifecycle, not the performance of an internal team.

| # | KPI | Formula / Calculation | Data Source | Target | At Risk | Critical |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | **Absence rate** | (Total transitions to Purple in the period / Total scheduled shifts) × 100 | [[Semáforo del Colaborador]], [[Core/Módulos/Schedule\|Schedule]] | ≤ 5% | 6–10% | > 10% |
| 2 | **Blacklist rate** | (Associates who moved to Black in the period / Total active associates at the start of the period) × 100 | [[Semáforo del Colaborador]] | ≤ 2% | 3–5% | > 5% |
| 3 | **Pool Health** | (Associates in Dark Green + Yellow / Total associates in the [[Pool de Colaboradores]]) × 100 | [[Pool de Colaboradores]], [[Semáforo del Colaborador]] | ≥ 60% | 40–59% | < 40% |
| 4 | **Extended Lunch rate** | (Shifts with lunch > 30 min / Total shifts in the period) × 100 | Extended Lunch Indicator in [[Timesheet]] | ≤ 10% | 11–20% | > 20% |
| 5 | **Data completeness** | (Associates with all 3 capture phases complete / Total active associates) × 100 | Capture data of [[Colaborador/Colaborador\|Associate]] (Phases 1–3) | ≥ 95% | 85–94% | < 85% |

**Why these KPIs:**
- KPI 1 is the fundamental metric for workforce reliability.
- KPI 2 tracks the most severe outcome; a rising rate signals systemic problems.
- KPI 3 measures whether there are enough deployable associates to meet demand.
- KPI 4 leverages the Extended Lunch Indicator already existing in the system.
- KPI 5 ensures data integrity — incomplete profiles create operational gaps.

## Sales

Assigned operator: Operator 4. Supervised department: [[Ventas/Ventas|Sales]].

| # | KPI | Formula / Calculation | Data Source | Target | At Risk | Critical |
|---|-----|-------------------|-----------------|------|-----------|---------|
| 1 | **Conversion rate** | (Hotels that reached Orange / Total hotels prospected in the period) × 100 | [[Core/Módulos/Semáforos/Semáforo Onboarding\|Onboarding Status Indicator]] | ≥ 25% | 15–24% | < 15% |
| 2 | **Average onboarding cycle** | Average days from Gray to Orange for converted hotels | Timestamps of [[Core/Módulos/Semáforos/Semáforo Onboarding\|Onboarding Status Indicator]] | ≤ 45 days | 46–75 days | > 75 days |
| 3 | **Stagnation rate** | (Hotels in Brown / Total active hotels in pipeline) × 100 | [[Core/Módulos/Semáforos/Semáforo Onboarding\|Onboarding Status Indicator]] | ≤ 10% | 11–20% | > 20% |
| 4 | **Loss rate** | (Hotels in Red or Black without reactivation / Total hotels managed in the period) × 100 | [[Core/Módulos/Semáforos/Semáforo Onboarding\|Onboarding Status Indicator]] | ≤ 20% | 21–35% | > 35% |
| 5 | **Successful reactivation rate** | (Hotels reactivated from Red/Black/Brown that advanced at least to Green / Total reactivated hotels) × 100 | Journal of [[Core/Módulos/Semáforos/Semáforo Onboarding\|Onboarding Status Indicator]] | ≥ 40% | 25–39% | < 25% |

**Why these KPIs:**
- KPI 1 is the primary effectiveness metric for the commercial team.
- KPI 2 ensures deals are not dragged on indefinitely.
- KPI 3 detects pipeline blockages that the [[Ventas/Roles/Business Developer Coordinator|BDC]] must resolve.
- KPI 4 tracks losses — a rising rate may indicate market misalignment or poor prospect selection.
- KPI 5 measures the team's ability to recover stalled opportunities.

## Recruitment

Assigned operator: Operator 5. Supervised department: [[Reclutamiento/Reclutamiento|Recruitment]].

| # | KPI | Formula / Calculation | Data Source | Target | At Risk | Critical |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | **Total requisition coverage** | (Requisitions that ended in Light Blue / Total closed requisitions in the period) × 100 | [[Core/Módulos/Semáforos/Semáforo de Requisición\|Requisition Status Indicator]] | ≥ 85% | 70–84% | < 70% |
| 2 | **Average requisition pickup time** | Average hours from authorization to pickup by [[Reclutadora]] | Timestamps of [[Core/Módulos/Semáforos/Semáforo de Requisición\|Requisition Status Indicator]] | ≤ 8h | 9–24h | > 24h |
| 3 | **Auto-assignment by timeout rate** | (Requisitions auto-assigned at 24h / Total authorized requisitions) × 100 | Auto-assignment system | ≤ 5% | 6–15% | > 15% |
| 4 | **Timeout escalation rate** | (Requisitions escalated to the [[Reclutamiento/Líder de Grupo de Reclutadoras\|Team Lead]] by timeout / Total requisitions in process) × 100 | Escalations per [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición\|Urgency Status Indicator]] | ≤ 10% | 11–20% | > 20% |
| 5 | **Blacklist check compliance** | (Recruitments with a recorded [[Core/Módulos/Blacklist\|Blacklist]] check / Total recruitments in the period) × 100 | [[Core/Módulos/Blacklist\|Blacklist]] check log | 100% | 95–99% | < 95% |
| 6 | **Pool entry rate** | (Approved associates admitted to the [[Pool de Colaboradores]] / Total interviewed candidates) × 100 | [[Core/Módulos/Pool de Colaboradores\|Associate Pool]], interview data | ≥ 60% | 45–59% | < 45% |

**Why these KPIs:**
- KPI 1 is the department's central deliverable — covering requisitions completely.
- KPIs 2–3 measure proactiveness in the Self-Pick model requisition pickup.
- KPI 4 detects cases where the [[Reclutadora]] could not find a match within the urgency window.
- KPI 5 is a compliance metric — the Blacklist check is a documented obligation.
- KPI 6 measures the health of the recruitment funnel — very low values indicate poor source selection or excessive filtering.

## Customer Service

Assigned operator: Operator 6. Supervised department: [[Customer Service/Customer Service|Customer Service]].

> [!note]
> The specific KPIs for Customer Service will be defined after an initial period of operation. The [[Manager de QA]] will establish the thresholds once real data on case volume, resolution times, and hotel satisfaction is available.

## Related

- [[QA/QA|QA]]
- [[Manager de QA]]
- [[Operador de QA]]
- [[QA/Dashboard de QA|QA Dashboard]]
- [[Core/Módulos/Semáforos/Indicador de Calidad|Quality Indicator]]
- [[Semáforo del Colaborador]]
- [[Core/Módulos/Semáforos/Semáforo de Requisición|Requisition Status Indicator]]
- [[Core/Módulos/Semáforos/Semáforo Onboarding|Onboarding Status Indicator]]
- [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición|Requisition Urgency Status Indicator]]
- [[Core/Módulos/Semáforos/Semáforo de Posiciones de la Requisición|Requisition Positions Status Indicator]]
- [[Reglas de Negocio]]
