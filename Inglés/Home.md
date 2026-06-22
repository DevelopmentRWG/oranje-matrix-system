---
tags:
  - modulo/core
aliases:
  - Oranje Matrix System
  - Home
---
# Oranje Matrix System

Organizational management system for hotel staffing. Documents the roles, processes, business rules and operational modules that structure Oranje's operation, from staff recruitment to their assignment and tracking at client hotels.

## Departments and Roles

### [[Recruitment/Recruitment|Recruitment]]

Searching, interviewing and assigning staff to hotels.

- [[Recruitment Manager|Recruitment Manager]] — monitors the recruitment operation and intervenes only in exceptional cases: balancing between groups, absent leader or correction of an assignment error.
- [[Recruiters Group Leader|Recruiters Group Leader]] — recruits and supervises the performance of a group of recruiters.
- [[Recruiter|Recruiter]] — searches, interviews, validates and assigns collaborators.

### [[Hotel/Hotel|Hotel]]

Daily operation and staff management at client hotels.

- [[Hotel/General Manager|General Manager]] — top authority at hotels with extended hierarchy.
- [[Hotel/Area Manager|Area Manager]] — approves requisitions, generates the punching QR and manages the weekly schedule. In extended hierarchy: Department Manager.
- [[Hotel/Supervisor|Supervisor]] — creates staff requisitions and reports work accidents.

### [[Inspection/Inspection|Inspection]]

On-site supervision of collaborators during their first days of assignment.

- [[Coordinator|Coordinator]] — assigns inspectors to zones and acts as liaison with other departments.
- [[Inspector|Inspector]] — supervises collaborators on site, verifies arrivals and closes accident cards.

### [[QA/QA|QA]]

Quality control over all of Oranje's departments.

- [[QA Manager|QA Manager]] — defines metrics and KPIs, supervises operators and presents reports to management.
- [[QA Operator|QA Operator]] — monitors status lights, measures metrics and issues observations by department.

### [[Sales/Sales|Sales]]

Business development and onboarding of new client hotels.

- [[Business Developer Coordinator|Business Developer Coordinator]] — supervises BDs in their territory and gives the go-ahead to convert prospects into clients.
- [[Business Developer|Business Developer]] — manages the commercial cycle with prospect hotels.

Process: [[Hotel Onboarding|Hotel Onboarding]]

### [[Customer Service/Customer Service|Customer Service]]

Post-onboarding support for the active client hotel: inquiries, complaints, incident follow-up and interdepartmental coordination.

- [[Customer Service/Customer Service Manager|Customer Service Manager]] — supervises agents, manages escalations and reports satisfaction metrics.
- [[Customer Service/Customer Service Agent|Customer Service Agent]] — receives, documents and follows up on the hotel's requests.

### Accounting

Weekly financial validation, management of payments to the collaborator and billing to the hotel.

- [[Accounting Manager|Accounting Manager]] — supervises, approves and authorizes the weekly financial processes.
- [[Accountant|Accountant]] — executes the validation, configuration and reconciliation of the payroll cycle.

Process: [[Accounting/Payroll Flow|Payroll Flow]]

## Central Entity

- [[Collaborator/Collaborator|Collaborator]] — the person who is recruited, assigned and operates at the hotels. Their life cycle is the axis of the system.

## Core Modules

### Processes

- [[Requisition|Requisition]] — formal staff request by a hotel. See [[Requisition Flow|Requisition Flow]].
- [[Contrato|Contract]] — legal agreement between Oranje and the collaborator.
- [[Recruitment Flow|Recruitment Flow]] — process of sourcing and onboarding new collaborators.
- [[Onboarding Flow|Onboarding Flow]] — process of incorporating a new hotel as a client.

### Operation

- [[Core/Modules/Schedule|Schedule]] — weekly assignment of collaborators to hotels.
- [[Timesheet|Timesheet]] — record of hours worked through QR punches.
- [[Collaborator Pool|Collaborator Pool]] — repository of collaborators available for assignment.

### Control

- [[Core/Modules/Blacklist|Blacklist]] — record of blocked collaborators.
- [[Core/Modules/Workplace Accident/Workplace Accident|Work Accident]] — management of on-site incidents. See [[Workplace Accident Flow|Work Accident Flow]].
- [[Business Rules|Business Rules]] — operational restrictions and conditions of the system.

### Accounting

- [[Collaborator Weekly Summary|Collaborator Weekly Consolidated]] — weekly summary of timesheets and pay calculation.
- [[Deductions|Deductions]] — automatic deductions from the collaborator's check.
- [[Hotel Invoicing|Hotel Billing]] — weekly tax document for charging the hotel.
- [[Vacation|Vacation]] — vacation pay calculation based on a 52-week average.

## Catalogs

- [[Posiciones|Positions]] — types of position a collaborator can hold.
- [[Zones|Zones]] — geographic areas of operation.
- [[English Levels|English Levels]] — language proficiency scale of collaborators.
- [[Hotel Departments|Hotel Departments]] — internal operational areas of the hotel.
- [[Employment Types|Hiring Modalities]] — available contract forms.

## Status Lights

State indicators that reflect the operational situation of each entity in real time.

- [[Collaborator Status Light|Collaborator Status Light]] — collaborator's state in their life cycle.
- [[Requisition Status Light|Requisition Status Light]] — state of a requisition in its coverage process.
- [[Requisition Urgency Status Light|Requisition Urgency Status Light]] — urgency level of an open requisition.
- [[Requisition Positions Status Light|Requisition Positions Status Light]] — state of each position within a requisition.
- [[Onboarding Status Light|Onboarding Status Light]] — state of the negotiation with a prospect hotel.
- [[Quality Indicator|Quality Indicator]] — performance level of an area supervised by QA.
- [[Timesheet Compliance Indicator|Timesheet Compliance Indicator]] — comparison between hours worked and the collaborator's contractual hours.

## Simulations

Narrative walkthroughs that illustrate how the system operates from each department's perspective.

- [[Simulation - Recruitment Point of View|Simulation - Recruitment Point of View]]
- [[Simulation - Collaborator Life Cycle|Simulation - Collaborator Life Cycle]]
- [[Simulation - Hotel Point of View|Simulation - Hotel Point of View]]
- [[Simulation - Inspection Point of View|Simulation - Inspection Point of View]]
- [[Simulation - QA Point of View|Simulation - QA Point of View]]
- [[Simulation - Sales Point of View|Simulation - Sales Point of View]]
- [[Simulation - Accounting Point of View|Simulation - Accounting Point of View]]
