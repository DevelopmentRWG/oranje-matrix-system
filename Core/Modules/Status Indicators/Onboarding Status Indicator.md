---
tags:
  - module/onboarding-hotel
aliases:
  - Onboarding Status Indicator
  - Hotel Onboarding Status Indicator
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

# Onboarding Status Indicator

Status system that represents the tracking of commercial negotiation with a hotel, from its identification as a prospect to its activation as a client (or its pause/rejection).

> [!info]
> This Status Indicator applies exclusively to the [[Onboarding-Hotel|Hotel Onboarding]] module. Once the hotel reaches [[#Orange — Signed agreement, active hotel client|Orange]], its operation is governed by the Status Indicators in the [[Hotel/Hotel|Hotel]] module ([[Requisition Status Indicator]], [[Associate Status Indicator]], etc.).

## States

| Color      | State                                                                                      | Responsible                                                          |
| ---------- | ------------------------------------------------------------------------------------------ | -------------------------------------------------------------------- |
| Gray       | [[#Gray — Hotel identified\|Hotel identified]]                                             | [[Business Developer\|BD]]                                           |
| Light Blue | [[#Light Blue — Contact and data collection\|Contact and data collection]]                 | [[Business Developer\|BD]]                                           |
| Brown      | [[#Brown — Renegotiation / unblocking\|Renegotiation / unblocking]]                        | [[Business Developer Coordinator\|BDC]]                              |
| Green      | [[#Green — Proposal sent\|Proposal sent]]                                                  | [[Business Developer\|BD]]                                           |
| Yellow     | [[#Yellow — Follow-up after proposal\|Follow-up after proposal]]                           | [[Business Developer\|BD]]                                           |
| Pink       | [[#Pink — Terms negotiation\|Terms negotiation]]                                           | [[Business Developer\|BD]] + [[Business Developer Coordinator\|BDC]] |
| Orange     | [[#Orange — Signed agreement, active hotel client\|Signed agreement, active hotel client]] | [[Business Developer Coordinator\|BDC]]                              |
| Red        | [[#Red — Rejection or no interest\|Rejection or no interest]]                              | [[Business Developer\|BD]]                                           |
| Black      | [[#Black — Paused or inactive client\|Paused or inactive client]]                          | [[Business Developer Coordinator\|BDC]]                              |

---

## Gray — Hotel identified

**Responsible:** [[Business Developer]]

The BD identifies the hotel within their territory as a possible client.

**Advance →** when contact and data collection begins, moves to [[#Light Blue — Contact and data collection|Light Blue]].

---

## Light Blue — Contact and data collection

**Responsible:** [[Business Developer]]

### Actions during this status

- Creates the hotel profile in the system.
- Collects data: hotel name, email, phone, contact name and position, business need.
- Conducts a cold visit to the hotel.

**Advance →** upon sending the [[Customized Proposal|proposal]], moves to [[#Green — Proposal sent|Green]].

> Also reached through reactivation from [[#Red — Rejection or no interest|Red]], [[#Black — Paused or inactive client|Black]] or [[#Brown — Renegotiation / unblocking|Brown]].

---

## Green — Proposal sent

**Responsible:** [[Business Developer]]

### Actions during this status

- Drafts [[Customized Proposal|personalized proposal]] (services, prices, conditions).
- Attaches and sends the proposal to the hotel.
- Logs contact attempts and responses.
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

- BD or BDC creates the [[Terms and Conditions Document]], which establishes:
  - Pay rate
  - Bill rate
  - Overtime
  - Holidays
  - Calendar

**Advance →** when formal negotiation begins, moves to [[#Pink — Terms negotiation|Pink]].

---

## Pink — Terms negotiation

**Responsible:** [[Business Developer]] + [[Business Developer Coordinator]]

### Decision

**Is the agreement closed?**

- **NO →** returns to the flow (renegotiation / [[#Brown — Renegotiation / unblocking|Brown]] / End).
- **YES →** the [[Business Developer Coordinator|BDC]] approves the conversion and the [[Hotel User|Hotel User]] is created in the system.

### Upon conversion approval

The [[Automatic Conversion Trigger|Automatic Conversion Trigger]] fires (in parallel):

- System sends welcome email to the hotel.
- System notifies the assigned [[Business Developer|BD]].
- Hotel disappears from the prospects list.

**Advance →** moves to [[#Orange — Signed agreement, active hotel client|Orange]].

---

## Orange — Signed agreement, active hotel client

**Operational Responsible:** [[Inspector]] + [[Recruiter|Recruiters]]
**Commercial Responsible:** [[Business Developer Coordinator]] (reference) · [[Business Developer]] (assigned)

> [!important]
> **Orange is the only status that enables the hotel to generate [[Requisition|requisitions]].**

### Operational state

- The hotel already has a [[Hotel User|user created]] in the system.
- Transfers to responsibility of [[Recruiter|Recruiters]].
- Operational cycle begins: [[Requisition|requisitions]] → coverage → [[Core/Modules/Schedule|Schedule]] → [[Timesheet]].
- BD and BDC remain as commercial references for the account.

### Decision

**Does the hotel stop operating?**

- **NO →** End (continues active).
- **YES →** moves to [[#Black — Paused or inactive client|Black]].

---

## Brown — Renegotiation / unblocking

**Responsible:** [[Business Developer Coordinator]]

> [!info]
> Brown is not a terminal status: it is an **unblocking bridge** operated by the BDC when a negotiation stalls.

### Actions during this status

- The BDC investigates the cause of the stall (price, conditions, competition, hotel timing).
- The BDC provides a solution or adjustment to resume the proposal and advance toward contracting.

**Advance →** with adjusted proposal, returns to [[#Light Blue — Contact and data collection|Light Blue]].

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

Client stopped operating or the relationship was paused.

### Frequent reasons

- Hotel closure.
- Change of management.
- Temporary operational pause.
- Commercial dispute.

### Decision

**Reactivate?**

- **NO →** End (archived as inactive client).
- **YES →** returns to [[#Light Blue — Contact and data collection|Light Blue]] to renegotiate reactivation conditions.

---

## Related

- [[Onboarding-Hotel]]
- [[Onboarding Flow]]
- [[Business Developer]]
- [[Business Developer Coordinator]]
