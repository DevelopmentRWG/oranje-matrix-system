---
tags:
  - module/core
aliases:
  - Oranje Matrix System
  - Home
---
# Oranje Matrix System

Organizational management system for hotel staffing. It documents the roles, processes, business rules, and operational modules that structure Oranje's operations, from personnel recruitment to their assignment and tracking at client hotels.

## Departments and Roles

### [[Recruitment/Recruitment|Recruitment]]

Search, interview, and assignment of personnel to hotels.

- [[Recruitment Manager]] — monitors the recruitment operation and intervenes only in exceptional cases: balancing between groups, absent team lead, or assignment error correction.
- [[Recruiter Team Lead]] — recruits and supervises the performance of a group of recruiters.
- [[Recruiter]] — searches, interviews, validates, and assigns associates.

### [[Hotel/Hotel|Hotel]]

Daily operations and personnel management at client hotels.

- [[Hotel/General Manager|General Manager]] — highest authority at hotels with extended hierarchy.
- [[Hotel/Area Manager|Area Manager]] — approves requisitions, generates punch QR codes, and manages the weekly schedule. In extended hierarchy: Department Manager.
- [[Hotel/Supervisor|Supervisor]] — creates personnel requisitions and reports work accidents.

### [[Inspection/Inspection|Inspection]]

On-site supervision of associates during their first days of assignment.

- [[Coordinator]] — assigns inspectors to zones and acts as liaison with other departments.
- [[Inspector]] — supervises associates on-site, verifies arrivals, and closes accident cards.

### [[QA/QA|QA]]

Quality control across all Oranje departments.

- [[QA Manager]] — defines metrics and KPIs, supervises operators, and presents reports to management.
- [[QA Operator]] — monitors status indicators, measures metrics, and issues observations per department.

### [[Sales/Sales|Sales]]

Business development and onboarding of new client hotels.

- [[Business Developer Coordinator]] — supervises BDs in their territory and approves the conversion of prospects into clients.
- [[Business Developer]] — manages the commercial cycle with prospect hotels.

Process: [[Onboarding-Hotel]]

### [[Customer Service/Customer Service|Customer Service]]

Post-onboarding support for active client hotels: inquiries, complaints, incident follow-up, and interdepartmental coordination.

- [[Customer Service/Customer Service Manager|Customer Service Manager]] — supervises agents, manages escalations, and reports satisfaction metrics.
- [[Customer Service/Customer Service Agent|Customer Service Agent]] — receives, documents, and follows up on hotel requests.

### Accounting

Weekly financial validation, associate payment management, and hotel billing.

- [[Accounting Manager]] — supervises, approves, and authorizes weekly financial processes.
- [[Accountant]] — executes the validation, configuration, and reconciliation of the payroll cycle.

Process: [[Accounting/Payroll Flow|Payroll Flow]]

## Central Entity

- [[Associate/Associate|Associate]] — the person who is recruited, assigned, and operates at hotels. Their lifecycle is the system's axis.

## Core Modules

### Processes

- [[Requisition]] — formal personnel request from a hotel. See [[Requisition Flow]].
- [[Contract]] — legal agreement between Oranje and the associate.
- [[Recruitment Flow]] — recruitment and onboarding process for new associates.
- [[Onboarding Flow]] — onboarding process for a new hotel as a client.

### Operations

- [[Core/Modules/Schedule|Schedule]] — weekly assignment of associates to hotels.
- [[Timesheet]] — record of worked hours via QR punches.
- [[Associate Pool]] — repository of associates available for assignment.

### Control

- [[Core/Modules/Blacklist|Blacklist]] — registry of blocked associates.
- [[Core/Modules/Work Accident/Work Accident|Work Accident]] — on-site incident management. See [[Work Accident Flow]].
- [[Business Rules]] — operational restrictions and conditions of the system.

### Accounting

- [[Weekly Associate Summary]] — weekly timesheet summary and payment calculation.
- [[Deductions]] — automatic deductions from the associate's paycheck.
- [[Hotel Invoice]] — weekly fiscal billing document to the hotel.
- [[Vacation Pay]] — vacation pay calculation based on 52-week average.

## Catalogs

- [[Positions]] — types of positions an associate can hold.
- [[Zones]] — geographic areas of operation.
- [[English Levels]] — associate language proficiency scale.
- [[Hotel Departments]] — hotel internal operational areas.
- [[Employment Modalities]] — available employment types.

## Status Indicators

Status indicators that reflect the real-time operational situation of each entity.

- [[Associate Status Indicator]] — associate status in their lifecycle.
- [[Requisition Status Indicator]] — requisition status in its coverage process.
- [[Requisition Urgency Indicator]] — urgency level of an open requisition.
- [[Requisition Position Status Indicator]] — status of each position within a requisition.
- [[Onboarding Status Indicator]] — status of the negotiation with a prospect hotel.
- [[Quality Indicator]] — performance level of an area supervised by QA.
- [[Timesheet Compliance Indicator]] — comparison between worked hours and the associate's contractual hours.

## Simulations

Narrative walkthroughs that illustrate how the system operates from the perspective of each department.

- [[Simulation - Recruitment Perspective]]
- [[Simulation - Associate Lifecycle]]
- [[Simulation - Hotel Perspective]]
- [[Simulation - Inspection Perspective]]
- [[Simulation - QA Point of View]]
- [[Simulation - Sales Point of View]]
- [[Simulation - Accounting Point of View]]
