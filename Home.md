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

### [[Reclutamiento/Reclutamiento|Recruitment]]

Search, interview, and assignment of personnel to hotels.

- [[Manager de Reclutamiento]] — monitors the recruitment operation and intervenes only in exceptional cases: balancing between groups, absent team lead, or assignment error correction.
- [[Líder de Grupo de Reclutadoras]] — recruits and supervises the performance of a group of recruiters.
- [[Reclutadora]] — searches, interviews, validates, and assigns associates.

### [[Hotel/Hotel|Hotel]]

Daily operations and personnel management at client hotels.

- [[Hotel/Manager General|General Manager]] — highest authority at hotels with extended hierarchy.
- [[Hotel/Manager de Área|Area Manager]] — approves requisitions, generates punch QR codes, and manages the weekly schedule. In extended hierarchy: Department Manager.
- [[Hotel/Supervisor|Supervisor]] — creates personnel requisitions and reports work accidents.

### [[Inspección/Inspección|Inspection]]

On-site supervision of associates during their first days of assignment.

- [[Coordinador]] — assigns inspectors to zones and acts as liaison with other departments.
- [[Inspector]] — supervises associates on-site, verifies arrivals, and closes accident cards.

### [[QA/QA|QA]]

Quality control across all Oranje departments.

- [[Manager de QA]] — defines metrics and KPIs, supervises operators, and presents reports to management.
- [[Operador de QA]] — monitors status indicators, measures metrics, and issues observations per department.

### [[Ventas/Ventas|Sales]]

Business development and onboarding of new client hotels.

- [[Business Developer Coordinator]] — supervises BDs in their territory and approves the conversion of prospects into clients.
- [[Business Developer]] — manages the commercial cycle with prospect hotels.

Process: [[Onboarding-Hotel]]

### [[Customer Service/Customer Service|Customer Service]]

Post-onboarding support for active client hotels: inquiries, complaints, incident follow-up, and interdepartmental coordination.

- [[Customer Service/Customer Service Manager|Customer Service Manager]] — supervises agents, manages escalations, and reports satisfaction metrics.
- [[Customer Service/Agente de Customer Service|Customer Service Agent]] — receives, documents, and follows up on hotel requests.

### Accounting

Weekly financial validation, associate payment management, and hotel billing.

- [[Manager de Contabilidad]] — supervises, approves, and authorizes weekly financial processes.
- [[Contadora]] — executes the validation, configuration, and reconciliation of the payroll cycle.

Process: [[Contabilidad/Flujo de Nómina|Payroll Flow]]

## Central Entity

- [[Colaborador/Colaborador|Associate]] — the person who is recruited, assigned, and operates at hotels. Their lifecycle is the system's axis.

## Core Modules

### Processes

- [[Requisición]] — formal personnel request from a hotel. See [[Flujo de Requisición]].
- [[Contrato]] — legal agreement between Oranje and the associate.
- [[Flujo de Reclutamiento]] — recruitment and onboarding process for new associates.
- [[Flujo de Onboarding]] — onboarding process for a new hotel as a client.

### Operations

- [[Core/Módulos/Schedule|Schedule]] — weekly assignment of associates to hotels.
- [[Timesheet]] — record of worked hours via QR punches.
- [[Pool de Colaboradores]] — repository of associates available for assignment.

### Control

- [[Core/Módulos/Blacklist|Blacklist]] — registry of blocked associates.
- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Work Accident]] — on-site incident management. See [[Flujo de Accidente Laboral]].
- [[Reglas de Negocio]] — operational restrictions and conditions of the system.

### Accounting

- [[Consolidado Semanal del Colaborador]] — weekly timesheet summary and payment calculation.
- [[Deducciones]] — automatic deductions from the associate's paycheck.
- [[Facturación al Hotel]] — weekly fiscal billing document to the hotel.
- [[Vacaciones]] — vacation pay calculation based on 52-week average.

## Catalogs

- [[Posiciones]] — types of positions an associate can hold.
- [[Zonas]] — geographic areas of operation.
- [[Niveles de Inglés]] — associate language proficiency scale.
- [[Departamentos del Hotel]] — hotel internal operational areas.
- [[Modalidades de Contratación]] — available employment types.

## Status Indicators

Status indicators that reflect the real-time operational situation of each entity.

- [[Semáforo del Colaborador]] — associate status in their lifecycle.
- [[Semáforo de Requisición]] — requisition status in its coverage process.
- [[Semáforo de Urgencia de Requisición]] — urgency level of an open requisition.
- [[Semáforo de Posiciones de la Requisición]] — status of each position within a requisition.
- [[Semáforo Onboarding]] — status of the negotiation with a prospect hotel.
- [[Indicador de Calidad]] — performance level of an area supervised by QA.
- [[Indicador de Cumplimiento del Timesheet]] — comparison between worked hours and the associate's contractual hours.

## Simulations

Narrative walkthroughs that illustrate how the system operates from the perspective of each department.

- [[Simulación - Punto de Vista de Reclutamiento]]
- [[Simulación - Ciclo de Vida del Colaborador]]
- [[Simulación - Punto de Vista del Hotel]]
- [[Simulación - Punto de Vista de Inspección]]
- [[Simulación - Punto de Vista de QA]]
- [[Simulación - Punto de Vista de Ventas]]
- [[Simulación - Punto de Vista de Contabilidad]]
