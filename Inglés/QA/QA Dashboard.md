---
tags:
  - departamento/qa
aliases:
  - QA Dashboard
  - Dashboard de QA
  - Dashboard QA
---

# QA Dashboard

Specification of the visualizations and charts that the application must provide to the [[QA/QA|QA]] team to monitor the operational quality of each department. This document is a **functional requirement** for development.

> [!info]
> All the data that feeds these charts is already tracked by the system (status lights, timesheets, journals, requisitions). The dashboard presents it visually to facilitate analysis by the QA team.

## Access by role

| Role | Visible panels |
|---|---|
| [[QA Manager|QA Manager]] | Global panel + the 6 panels by department |
| [[QA Operator|QA Operator]] | Only the panel of their assigned department |

## Global panel — QA Manager

Consolidated view of the 6 supervised departments. It allows the [[QA Manager|QA Manager]] to quickly identify which departments require attention.

### Global panel charts

| # | Chart | Visualization type | Data | Update |
|---|---------|----------------------|-------|---------------|
| 1 | **Current state of the 6 departments** | Summary cards (1 per department) | [[Quality Indicator|Quality Indicator]] of each department + count of KPIs in On Target / At Risk / Critical | Real time |
| 2 | **Quality Indicator trend** | Line chart (1 line per department) | Change history of the [[Quality Indicator|Quality Indicator]] by department. X axis = weeks | Weekly |
| 3 | **KPIs in Critical state** | Table with alerts | List of KPIs that are at Critical level in any department, with KPI name, department and current value | Real time |

## Panel by department — QA Operator

Each of the 6 departments has a detailed panel with the following standard charts, fed by the KPIs defined in [[QA/Metrics and KPIs by Department|Metrics and KPIs by Department]].

### Standard charts (apply to all 6 departments)

| # | Chart | Visualization type | Data | Update |
|---|---------|----------------------|-------|---------------|
| 1 | **KPI summary** | Horizontal bars with On Target / At Risk / Critical zones | Current value of each department KPI vs defined thresholds | Real time |
| 2 | **KPI trend** | Line chart (1 line per KPI) | Weekly history of each department KPI. X axis = weeks | Weekly |
| 3 | **Observation history** | Timeline / chronological list | Formal observations issued to the department: state (open / addressed / closed), issue date, description | Real time |

### Department-specific charts

In addition to the standard charts, each department has particular visualizations that leverage the nature of its data.

#### Inspection

| Chart | Visualization type | Data |
|---------|----------------------|-------|
| **Zone coverage map** | Geographic map or zone diagram | The 6 [[Core/Catalogs/Zones|zones]] with an [[Inspector]] availability indicator (active / temporary coverage / no coverage) |

#### Hotel

| Chart | Visualization type | Data |
|---------|----------------------|-------|
| **Hotel ranking by punch-in compliance** | Sorted table / vertical bars | Hotels ordered by % of timesheets with 6 complete punches, from best to worst |

#### Collaborator

| Chart | Visualization type | Data |
|---------|----------------------|-------|
| **Collaborator Status Light distribution** | Donut chart | Percentage of collaborators in each of the 12 states of the [[Collaborator Status Light|Collaborator Status Light]] |

#### Sales

| Chart | Visualization type | Data |
|---------|----------------------|-------|
| **Onboarding Status Light funnel** | Funnel chart | Number of hotels at each stage of the [[Core/Modules/Status Lights/Onboarding Status Light|Onboarding Status Light]] (Gray → Light Blue → Green → Yellow → Pink → Orange) |

#### Recruitment

| Chart | Visualization type | Data |
|---------|----------------------|-------|
| **Recruitment funnel** | Funnel chart | Candidates interviewed → approved → added to the [[Collaborator Pool|Collaborator Pool]] → assigned to position |
| **Take-up time heatmap by urgency** | Heatmap | Requisition take-up time (Y axis) vs urgency level of the [[Core/Modules/Status Lights/Requisition Urgency Status Light|Urgency Status Light]] (X axis). Intensity = number of requisitions |

#### Customer Service

> [!note]
> The Customer Service specific charts will be defined once the department's KPIs are established. See [[QA/Metrics and KPIs by Department#Customer Service|Metrics and KPIs — Customer Service]].

## Related

- [[QA/QA|QA]]
- [[QA Manager|QA Manager]]
- [[QA Operator|QA Operator]]
- [[QA/Metrics and KPIs by Department|Metrics and KPIs by Department]]
- [[Core/Modules/Status Lights/Quality Indicator|Quality Indicator]]
