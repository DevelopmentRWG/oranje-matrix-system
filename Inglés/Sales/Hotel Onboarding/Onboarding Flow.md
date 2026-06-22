---
tags:
  - modulo/onboarding-hotel
  - flujo
aliases:
  - Hotel Onboarding Flow
---

# Onboarding Flow

Step-by-step commercial process to incorporate a hotel as an active client of Oranje. Each stage corresponds to a status of the [[Onboarding Status Light|Onboarding Status Light]].

## Stage 1 — [[Onboarding Status Light#Gris — Hotel identificado|Gray]] Hotel identified

**Responsible:** [[Business Developer]]
**Single action:** the BD identifies the hotel within their territory as a possible client.

**Advance →** when they start contact and data collection, they move the status to [[Onboarding Status Light#Azul Claro — Contacto y recopilación de datos|Light Blue]].

## Stage 2 — [[Onboarding Status Light#Azul Claro — Contacto y recopilación de datos|Light Blue]] Contact and data collection

**Responsible:** [[Business Developer]]
**Actions during this status:**

- Creates the hotel profile in the system.
- Collects data: hotel name, email, phone, name and position of the contact, business need.
- Performs a cold visit to the hotel.

**Advance →** upon sending the proposal, the status changes to [[Onboarding Status Light#Verde — Propuesta enviada|Green]].

## Stage 3 — [[Onboarding Status Light#Verde — Propuesta enviada|Green]] Proposal sent

**Responsible:** [[Business Developer]]
**Actions:**

- Prepares a [[Personalized Proposal|customized proposal]] (services, prices, conditions).
- Attaches and sends the proposal to the hotel.
- Records contact attempts and responses.
- Follows up with the hotel.

**Decision: Does the hotel respond with interest?**

- **YES →** moves to [[Onboarding Status Light#Amarillo — En seguimiento tras propuesta|Yellow]].
- **NO →** moves to [[Onboarding Status Light#Rojo — Rechazo o no interés|Red]].

**Alternate branch:** if there is a stall, [[Onboarding Status Light#Café — Renegociación / desbloqueo|Brown]] is activated and the [[Business Developer Coordinator]] investigates and provides a solution to resume the proposal → returns to [[Onboarding Status Light#Azul Claro — Contacto y recopilación de datos|Light Blue]].

## Stage 4 — [[Onboarding Status Light#Amarillo — En seguimiento tras propuesta|Yellow]] Follow-up after proposal

**Responsible:** [[Business Developer]] (with support from the [[Business Developer Coordinator]])
**Actions during this status:**

- BD or BDC creates the [[Terms and Conditions Document|Terms and Conditions Document]], which establishes:
  - Pay rate
  - Bill rate
  - Overtime
  - Holidays
  - Calendar

**Advance →** upon starting the formal negotiation, it moves to [[Onboarding Status Light#Rosa — Negociación de términos|Pink]].

## Stage 5 — [[Onboarding Status Light#Rosa — Negociación de términos|Pink]] Terms negotiation

**Responsible:** [[Business Developer]] + [[Business Developer Coordinator]]

**Decision: Is the agreement closed?**

- **NO →** returns to the flow (renegotiation / [[Onboarding Status Light#Café — Renegociación / desbloqueo|Brown]] / End).
- **YES →** the BDC approves the conversion and the [[Hotel User|Hotel User]] is created in the system.

**When the user is created** the [[Automatic Conversion Trigger|Automatic Conversion Trigger]] fires (in parallel):

- The system sends a welcome email to the hotel.
- The system notifies the assigned BD.
- The hotel disappears from the prospect list.

**Advance →** moves to [[Onboarding Status Light#Naranja — Acuerdo firmado, hotel cliente activo|Orange]].

## Stage 6 — [[Onboarding Status Light#Naranja — Acuerdo firmado, hotel cliente activo|Orange]] Active client hotel

**Operational responsible:** [[Inspector]] + [[Recruiter|Recruiters]]
**Status:** the hotel already has a [[Hotel User|created user]] and is working with Oranje.

- Moves to the responsibility of [[Recruiter|Recruiters]].
- Operational cycle begins: [[Requisition|requisitions]] → coverage → [[Core/Modules/Schedule|Schedule]] → [[Timesheet]].
- BD and BDC remain as commercial references.

**Decision: Does the hotel stop operating?**

- **NO →** End (remains active).
- **YES →** moves to [[Onboarding Status Light#Negro — Cliente pausado o inactivo|Black]].

## Stage 7 — [[Onboarding Status Light#Rojo — Rechazo o no interés|Red]] Hotel rejected the proposal / not interested

**Responsible:** [[Business Developer]]

**Decision: Reactivate?**

- **NO →** End.
- **YES →** returns to [[Onboarding Status Light#Azul Claro — Contacto y recopilación de datos|Light Blue]].

## Stage 8 — [[Onboarding Status Light#Negro — Cliente pausado o inactivo|Black]] Client stopped operating / relationship paused

**Responsible:** [[Business Developer Coordinator]]
**Reasons:** hotel closure, change of administration, pause, dispute.

**Decision: Reactivate?**

- **NO →** End.
- **YES →** returns to [[Onboarding Status Light#Azul Claro — Contacto y recopilación de datos|Light Blue]].

## Key points

- Every status change is recorded with date, responsible and comment.
- [[Onboarding Status Light#Naranja — Acuerdo firmado, hotel cliente activo|Orange]] is the only status that enables the hotel to generate [[Requisition|requisitions]].
- The [[Hotel User|Hotel User]] is created upon approving the conversion in [[Onboarding Status Light#Rosa — Negociación de términos|Pink]], just before the [[Automatic Conversion Trigger|automatic trigger]].
- [[Onboarding Status Light#Rojo — Rechazo o no interés|Red]], [[Onboarding Status Light#Negro — Cliente pausado o inactivo|Black]] and [[Onboarding Status Light#Café — Renegociación / desbloqueo|Brown]] always reactivate towards [[Onboarding Status Light#Azul Claro — Contacto y recopilación de datos|Light Blue]].
- The final conversion approval is given solely by the [[Business Developer Coordinator]].
