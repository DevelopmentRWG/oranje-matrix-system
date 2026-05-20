---
tags:
  - module/hotel-onboarding
  - flow
aliases:
  - Hotel Onboarding Flow
---

# Onboarding Flow

Step-by-step commercial process for incorporating a hotel as an active Oranje client. Each stage corresponds to a status in the [[Semáforo Onboarding]].

## Stage 1 — [[Semáforo Onboarding#Gris — Hotel identificado|Gris]] Hotel Identified

**Responsible:** [[Business Developer]]
**Single action:** the BD identifies the hotel within their territory as a potential client.

**Advance →** when they initiate contact and data collection, the status moves to [[Semáforo Onboarding#Azul Claro — Contacto y recopilación de datos|Azul Claro]].

## Stage 2 — [[Semáforo Onboarding#Azul Claro — Contacto y recopilación de datos|Azul Claro]] Contact and Data Collection

**Responsible:** [[Business Developer]]
**Actions during this status:**

- Creates the hotel profile in the system.
- Collects data: hotel name, email, phone, contact name and title, business need.
- Conducts a cold visit to the hotel.

**Advance →** upon sending the proposal, the status changes to [[Semáforo Onboarding#Verde — Propuesta enviada|Verde]].

## Stage 3 — [[Semáforo Onboarding#Verde — Propuesta enviada|Verde]] Proposal Sent

**Responsible:** [[Business Developer]]
**Actions:**

- Prepares a [[Propuesta Personalizada|customized proposal]] (services, prices, conditions).
- Attaches and sends the proposal to the hotel.
- Records contact attempts and responses.
- Follows up with the hotel.

**Decision: Does the hotel respond with interest?**

- **YES →** moves to [[Semáforo Onboarding#Amarillo — En seguimiento tras propuesta|Amarillo]].
- **NO →** moves to [[Semáforo Onboarding#Rojo — Rechazo o no interés|Rojo]].

**Alternate branch:** if there is a stall, [[Semáforo Onboarding#Café — Renegociación / desbloqueo|Café]] is activated and the [[Business Developer Coordinator]] investigates and provides a solution to resume the proposal → returns to [[Semáforo Onboarding#Azul Claro — Contacto y recopilación de datos|Azul Claro]].

## Stage 4 — [[Semáforo Onboarding#Amarillo — En seguimiento tras propuesta|Amarillo]] In Follow-up After Proposal

**Responsible:** [[Business Developer]] (with support from the [[Business Developer Coordinator]])
**Actions during this status:**

- BD or BDC creates the [[Documento de Términos y Condiciones]], which establishes:
  - Pay rate
  - Bill rate
  - Overtime
  - Holidays
  - Calendar

**Advance →** when formal negotiation begins, moves to [[Semáforo Onboarding#Rosa — Negociación de términos|Rosa]].

## Stage 5 — [[Semáforo Onboarding#Rosa — Negociación de términos|Rosa]] Terms Negotiation

**Responsible:** [[Business Developer]] + [[Business Developer Coordinator]]

**Decision: Is the agreement closed?**

- **NO →** returns to the flow (renegotiation / [[Semáforo Onboarding#Café — Renegociación / desbloqueo|Café]] / End).
- **YES →** the BDC approves the conversion and the [[Usuario del Hotel]] is created in the system.

**When the user is created**, the [[Trigger Automático de Conversión]] fires (in parallel):

- System sends a welcome email to the hotel.
- System notifies the assigned BD.
- Hotel disappears from the prospect list.

**Advance →** moves to [[Semáforo Onboarding#Naranja — Acuerdo firmado, hotel cliente activo|Naranja]].

## Stage 6 — [[Semáforo Onboarding#Naranja — Acuerdo firmado, hotel cliente activo|Naranja]] Active Hotel Client

**Operational responsible:** [[Inspector]] + [[Reclutadora|Recruiters]]
**Status:** the hotel already has a [[Usuario del Hotel|user account created]] and is working with Oranje.

- Passes to responsibility of [[Reclutadora|Recruiters]].
- Operational cycle begins: [[Requisición|requisitions]] → coverage → [[Core/Módulos/Schedule|Schedule]] → [[Timesheet]].
- BD and BDC remain as commercial references.

**Decision: Does the hotel stop operating?**

- **NO →** End (continues active).
- **YES →** moves to [[Semáforo Onboarding#Negro — Cliente pausado o inactivo|Negro]].

## Stage 7 — [[Semáforo Onboarding#Rojo — Rechazo o no interés|Rojo]] Hotel Rejected the Proposal / Not Interested

**Responsible:** [[Business Developer]]

**Decision: Reactivate?**

- **NO →** End.
- **YES →** returns to [[Semáforo Onboarding#Azul Claro — Contacto y recopilación de datos|Azul Claro]].

## Stage 8 — [[Semáforo Onboarding#Negro — Cliente pausado o inactivo|Negro]] Client Stopped Operating / Paused Relationship

**Responsible:** [[Business Developer Coordinator]]
**Reasons:** hotel closure, management change, pause, dispute.

**Decision: Reactivate?**

- **NO →** End.
- **YES →** returns to [[Semáforo Onboarding#Azul Claro — Contacto y recopilación de datos|Azul Claro]].

## Key Points

- Every status change is recorded with date, responsible, and comment.
- [[Semáforo Onboarding#Naranja — Acuerdo firmado, hotel cliente activo|Naranja]] is the only status that enables the hotel to generate [[Requisición|requisitions]].
- The [[Usuario del Hotel]] is created upon approving the conversion at [[Semáforo Onboarding#Rosa — Negociación de términos|Rosa]], just before the [[Trigger Automático de Conversión|automatic trigger]].
- [[Semáforo Onboarding#Rojo — Rechazo o no interés|Rojo]], [[Semáforo Onboarding#Negro — Cliente pausado o inactivo|Negro]], and [[Semáforo Onboarding#Café — Renegociación / desbloqueo|Café]] always reactivate toward [[Semáforo Onboarding#Azul Claro — Contacto y recopilación de datos|Azul Claro]].
- Final conversion approval is given exclusively by the [[Business Developer Coordinator]].
