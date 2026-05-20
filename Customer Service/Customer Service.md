---
tags:
  - module/customer-service
aliases:
  - Customer Service
  - Customer Service Module
  - CS
---

# Customer Service

Module responsible for post-onboarding service to the active client hotel. Customer Service is the formal communication channel between the hotel and Oranje for inquiries, requests, complaints, and incident follow-up that do not correspond to the predefined operational flows ([[Requisición|requisitions]], [[Core/Módulos/Schedule|Schedule]], [[Timesheet]]).

It operates from the moment the hotel reaches **Orange** status in the [[Core/Módulos/Semáforos/Semáforo Onboarding|Onboarding Status Indicator]] and remains the point of contact throughout the hotel's life as a client.

## Roles

- [[Customer Service/Customer Service Manager|Customer Service Manager]] — Supervises the agent team, manages escalations, and reports satisfaction metrics.
- [[Customer Service/Agente de Customer Service|Customer Service Agent]] — Receives, documents, and follows up on hotel requests until closure.

## Scope

### What Customer Service Handles

- General hotel inquiries about operations with Oranje.
- Complaints or grievances about assigned associates, billing, or processes.
- Requests that do not fit into existing operational flows.
- Follow-up on commercial disputes before they escalate to **Black** status in the [[Core/Módulos/Semáforos/Semáforo Onboarding|Onboarding Status Indicator]].
- Coordination with internal departments to resolve incidents reported by the hotel.

### What Customer Service Does NOT Handle

- Creation or authorization of [[Requisición|requisitions]] — that is the responsibility of [[Hotel/Hotel|Hotel]].
- Staff assignment — that is the responsibility of [[Reclutamiento/Reclutamiento|Recruitment]].
- On-site associate verification — that is the responsibility of [[Inspección/Inspección|Inspection]].
- Acquisition of new hotels — that is the responsibility of [[Ventas/Ventas|Sales]].

## Processes

- [[Customer Service/Flujo de Customer Service|Customer Service Flow]] — Step-by-step process for handling hotel requests.

## Rules

See [[Customer Service/Reglas de Customer Service|Customer Service Rules]].

## Related Core Concepts

- [[Hotel/Hotel|Hotel]]
- [[Core/Módulos/Semáforos/Semáforo Onboarding|Onboarding Status Indicator]]
- [[Ventas/Ventas|Sales]]
- [[Reglas de Negocio]]

## Relationship with Other Modules

- [[Hotel/Hotel|Hotel]] — The hotel is the source of support requests. The [[Hotel/Manager General|General Manager]] is the primary point of contact.
- [[Ventas/Ventas|Sales]] — Customer Service is the continuation of the commercial cycle post-conversion. The [[Ventas/Roles/Business Developer Coordinator|BDC]] is the escalation point for commercial matters.
- [[QA/QA|QA]] — A [[Operador de QA]] supervises Customer Service performance metrics.
- [[Inspección/Inspección|Inspection]] — For incidents requiring on-site verification, Customer Service coordinates with the [[Inspección/Coordinador|Inspection Coordinator]].
