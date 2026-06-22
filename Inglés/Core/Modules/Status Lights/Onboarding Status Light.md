---
tags:
  - modulo/onboarding-hotel
aliases:
  - Onboarding Status Light
  - Hotel Onboarding Status Light
  - Onboarding Status Gray
  - Onboarding Status Light Blue
  - Onboarding Status Brown
  - Onboarding Status Green
  - Onboarding Status Yellow
  - Onboarding Status Pink
  - Onboarding Status Orange
  - Onboarding Status Red
  - Onboarding Status Black
---

# Onboarding Status Light

System of states that represents the tracking of the commercial negotiation with a hotel, from its identification as a prospect to its activation as a client (or its pause/rejection).

> [!info]
> This status light applies only to the [[Hotel Onboarding|Hotel Onboarding]] module. Once the hotel reaches [[#Orange — Agreement signed, active client hotel|Orange]], its operation is governed by the status lights of the [[Hotel/Hotel|Hotel]] module ([[Requisition Status Light|Requisition Status Light]], [[Collaborator Status Light|Collaborator Status Light]], etc.).

## States

| Color      | State                                                              | Responsible                                                          |
| ---------- | ------------------------------------------------------------------ | -------------------------------------------------------------------- |
| Gray       | [[#Gray — Hotel identified\|Hotel identified]]                     | [[Business Developer\|BD]]                                           |
| Light Blue | [[#Light Blue — Contact and data collection\|Contact and data collection]] | [[Business Developer\|BD]]                          |
| Brown      | [[#Brown — Renegotiation / unblocking\|Renegotiation / unblocking]] | [[Business Developer Coordinator\|BDC]]                             |
| Green      | [[#Green — Proposal sent\|Proposal sent]]                          | [[Business Developer\|BD]]                                           |
| Yellow     | [[#Yellow — Follow-up after proposal\|Follow-up after proposal]]   | [[Business Developer\|BD]]                                           |
| Pink       | [[#Pink — Terms negotiation\|Terms negotiation]]                   | [[Business Developer\|BD]] + [[Business Developer Coordinator\|BDC]] |
| Orange     | [[#Orange — Agreement signed, active client hotel\|Agreement signed, active client hotel]] | [[Business Developer Coordinator\|BDC]]       |
| Red        | [[#Red — Rejection or no interest\|Rejection or no interest]]      | [[Business Developer\|BD]]                                           |
| Black      | [[#Black — Paused or inactive client\|Paused or inactive client]]  | [[Business Developer Coordinator\|BDC]]                             |

---

## Gray — Hotel identified

**Responsible:** [[Business Developer]]

The BD identifies the hotel within their territory as a possible client.

**Advance →** when contact and data collection begins, it moves to [[#Light Blue — Contact and data collection|Light Blue]].

---

## Light Blue — Contact and data collection

**Responsible:** [[Business Developer]]

### Actions during this status

- Creates the hotel's profile in the system.
- Collects data: hotel name, email, phone, contact's name and position, business need.
- Performs a cold visit to the hotel.

**Advance →** upon sending the [[Personalized Proposal|proposal]], it moves to [[#Green — Proposal sent|Green]].

> It is also reached here by reactivation from [[#Red — Rejection or no interest|Red]], [[#Black — Paused or inactive client|Black]] or [[#Brown — Renegotiation / unblocking|Brown]].

---

## Green — Proposal sent

**Responsible:** [[Business Developer]]

### Actions during this status

- Prepares the [[Personalized Proposal|customized proposal]] (services, prices, conditions).
- Attaches and sends the proposal to the hotel.
- Records contact attempts and responses.
- Follows up with the hotel.

### Decision

**Does the hotel respond with interest?**

- **YES →** [[#Yellow — Follow-up after proposal|Yellow]].
- **NO →** [[#Red — Rejection or no interest|Red]].

**Alternate branch:** if the negotiation stalls → [[#Brown — Renegotiation / unblocking|Brown]] (managed by [[Business Developer Coordinator]]).

---

## Yellow — Follow-up after proposal

**Responsible:** [[Business Developer]] (with support from the [[Business Developer Coordinator]])

### Actions during this status

- BD or BDC creates the [[Terms and Conditions Document|Terms and Conditions Document]], which establishes:
  - Pay rate
  - Bill rate
  - Overtime
  - Holidays
  - Calendar

**Advance →** upon starting formal negotiation, it moves to [[#Pink — Terms negotiation|Pink]].

---

## Pink — Terms negotiation

**Responsible:** [[Business Developer]] + [[Business Developer Coordinator]]

### Decision

**Is the agreement closed?**

- **NO →** returns to the flow (renegotiation / [[#Brown — Renegotiation / unblocking|Brown]] / End).
- **YES →** the [[Business Developer Coordinator|BDC]] approves the conversion and the [[Hotel User|Hotel User]] is created in the system.

### Upon approving the conversion

The [[Automatic Conversion Trigger|Automatic Conversion Trigger]] is fired (in parallel):

- The system sends a welcome email to the hotel.
- The system notifies the assigned [[Business Developer|BD]].
- The hotel disappears from the prospects list.

**Advance →** it moves to [[#Orange — Agreement signed, active client hotel|Orange]].

---

## Orange — Agreement signed, active client hotel

**Operational responsible:** [[Inspector]] + [[Recruiter|Recruiters]]
**Commercial responsible:** [[Business Developer Coordinator]] (reference) · [[Business Developer]] (assigned)

> [!important]
> **Orange is the only status that enables the hotel to generate [[Requisition|requisitions]].**

### Operational state

- The hotel already has a [[Hotel User|user created]] in the system.
- It passes to the responsibility of [[Recruiter|Recruiters]].
- The operational cycle begins: [[Requisition|requisitions]] → coverage → [[Core/Modules/Schedule|Schedule]] → [[Timesheet]].
- BD and BDC remain as commercial references for the account.

### Decision

**Does the hotel stop operating?**

- **NO →** End (remains active).
- **YES →** it moves to [[#Black — Paused or inactive client|Black]].

---

## Brown — Renegotiation / unblocking

**Responsible:** [[Business Developer Coordinator]]

> [!info]
> Brown is not a terminal status: it is an **unblocking bridge** operated by the BDC when a negotiation stalls.

### Actions during this status

- The BDC investigates the cause of the stall (price, conditions, competition, hotel's timing).
- The BDC provides a solution or adjustment to resume the proposal and advance to contracting.

**Advance →** with the adjusted proposal, it returns to [[#Light Blue — Contact and data collection|Light Blue]].

---

## Red — Rejection or no interest

**Responsible:** [[Business Developer]]

The hotel rejected the proposal or is not interested.

### Decision

**Reactivate?**

- **NO →** End (hotel archived as not viable).
- **YES →** returns to [[#Light Blue — Contact and data collection|Light Blue]] to restart contact.

---

## Black — Paused or inactive client

**Responsible:** [[Business Developer Coordinator]]

The client stopped operating or the relationship was paused.

### Frequent reasons

- Hotel closure.
- Change of administration.
- Temporary operation pause.
- Commercial dispute.

### Decision

**Reactivate?**

- **NO →** End (archived as inactive client).
- **YES →** returns to [[#Light Blue — Contact and data collection|Light Blue]] to renegotiate reactivation conditions.

---

## Related

- [[Hotel Onboarding|Hotel Onboarding]]
- [[Onboarding Flow|Onboarding Flow]]
- [[Business Developer]]
- [[Business Developer Coordinator]]
