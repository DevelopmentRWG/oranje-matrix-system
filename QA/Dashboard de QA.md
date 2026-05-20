---
tags:
  - department/qa
aliases:
  - QA Dashboard
---

# QA Dashboard

Specification of the visualizations and charts that the application must provide to the [[QA/QA|QA]] team to monitor the operational quality of each department. This document is a **functional requirement** for development.

> [!info]
> All data feeding these charts is already tracked by the system (status indicators, timesheets, journals, requisitions). The dashboard presents them visually to facilitate analysis by the QA team.

## Access by Role

| Role | Visible Panels |
|---|---|
| [[Manager de QA]] | Global panel + the 6 department panels |
| [[Operador de QA]] | Only the panel for their assigned department |

## Global Panel — QA Manager

Consolidated view of the 6 supervised departments. Allows the [[Manager de QA]] to quickly identify which departments require attention.

### Global Panel Charts

| # | Chart | Visualization Type | Data | Update |
|---|---------|----------------------|-------|---------------|
| 1 | **Current status of all 6 departments** | Summary cards (1 per department) | [[Indicador de Calidad]] per department + count of KPIs at Target / At Risk / Critical | Real time |
| 2 | **Quality Indicator trend** | Line chart (1 line per department) | History of [[Indicador de Calidad]] changes per department. X axis = weeks | Weekly |
| 3 | **KPIs in Critical status** | Table with alerts | List of KPIs at Critical level in any department, with KPI name, department, and current value | Real time |

## Department Panel — QA Operator

Each of the 6 departments has a detailed panel with the following standard charts, fed by the KPIs defined in [[QA/Métricas y KPIs por Departamento|Metrics and KPIs by Department]].

### Standard Charts (apply to all 6 departments)

| # | Chart | Visualization Type | Data | Update |
|---|---------|----------------------|-------|---------------|
| 1 | **KPI Summary** | Horizontal bars with Target / At Risk / Critical zones | Current value of each department KPI vs defined thresholds | Real time |
| 2 | **KPI Trend** | Line chart (1 line per KPI) | Weekly history of each department KPI. X axis = weeks | Weekly |
| 3 | **Observation history** | Timeline / chronological list | Formal observations issued to the department: status (open / addressed / closed), issue date, description | Real time |

### Department-Specific Charts

In addition to the standard charts, each department has particular visualizations that leverage the nature of its data.

#### Inspection

| Chart | Visualization Type | Data |
|---------|----------------------|-------|
| **Zone coverage map** | Geographic map or zone diagram | The 6 [[Core/Catálogos/Zonas|zones]] with [[Inspector]] availability indicator (active / temporary coverage / no coverage) |

#### Hotel

| Chart | Visualization Type | Data |
|---------|----------------------|-------|
| **Hotel ranking by punch compliance** | Sorted table / vertical bars | Hotels ranked by % of timesheets with 6 complete punches, from best to worst |

#### Associate

| Chart | Visualization Type | Data |
|---------|----------------------|-------|
| **Associate Status Indicator distribution** | Donut chart | Percentage of associates in each of the 12 states of the [[Semáforo del Colaborador]] |

#### Sales

| Chart | Visualization Type | Data |
|---------|----------------------|-------|
| **Onboarding Status Indicator funnel** | Funnel chart | Number of hotels at each stage of the [[Core/Módulos/Semáforos/Semáforo Onboarding|Onboarding Status Indicator]] (Gray → Light Blue → Green → Yellow → Pink → Orange) |

#### Recruitment

| Chart | Visualization Type | Data |
|---------|----------------------|-------|
| **Recruitment funnel** | Funnel chart | Interviewed candidates → approved → admitted to [[Pool de Colaboradores]] → assigned to position |
| **Pickup time heatmap by urgency** | Heat map | Requisition pickup time (Y axis) vs urgency level of the [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición|Urgency Status Indicator]] (X axis). Intensity = number of requisitions |

#### Customer Service

> [!note]
> The specific charts for Customer Service will be defined once the department's KPIs are established. See [[QA/Métricas y KPIs por Departamento#Customer Service|Metrics and KPIs — Customer Service]].

## Related

- [[QA/QA|QA]]
- [[Manager de QA]]
- [[Operador de QA]]
- [[QA/Métricas y KPIs por Departamento|Metrics and KPIs by Department]]
- [[Core/Módulos/Semáforos/Indicador de Calidad|Quality Indicator]]
