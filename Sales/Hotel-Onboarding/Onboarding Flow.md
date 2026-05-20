---
tags:
  - module/hotel-onboarding
  - flow
aliases:
  - Hotel Onboarding Flow
---

# Onboarding Flow

Step-by-step commercial process for incorporating a hotel as an active Oranje client. Each stage corresponds to a status in the [[Onboarding Status Indicator]].

## Stage 1 — [[Onboarding Status Indicator#Gray — Hotel identified|Gray]] Hotel Identified

**Responsible:** [[Business Developer]]
**Single action:** the BD identifies the hotel within their territory as a potential client.

**Advance →** when they initiate contact and data collection, the status moves to [[Onboarding Status Indicator#Light Blue — Contact and data collection|Light Blue]].

## Stage 2 — [[Onboarding Status Indicator#Light Blue — Contact and data collection|Light Blue]] Contact and Data Collection

**Responsible:** [[Business Developer]]
**Actions during this status:**

- Creates the hotel profile in the system.
- Collects data: hotel name, email, phone, contact name and title, business need.
- Conducts a cold visit to the hotel.

**Advance →** upon sending the proposal, the status changes to [[Onboarding Status Indicator#Green — Proposal sent|Green]].

## Stage 3 — [[Onboarding Status Indicator#Green — Proposal sent|Green]] Proposal Sent

**Responsible:** [[Business Developer]]
**Actions:**

- Prepares a [[Customized Proposal|customized proposal]] (services, prices, conditions).
- Attaches and sends the proposal to the hotel.
- Records contact attempts and responses.
- Follows up with the hotel.

**Decision: Does the hotel respond with interest?**

- **YES →** moves to [[Onboarding Status Indicator#Yellow — Follow-up after proposal|Yellow]].
- **NO →** moves to [[Onboarding Status Indicator#Red — Rejection or no interest|Red]].

**Alternate branch:** if there is a stall, [[Onboarding Status Indicator#Brown — Renegotiation / unblocking|Brown]] is activated and the [[Business Developer Coordinator]] investigates and provides a solution to resume the proposal → returns to [[Onboarding Status Indicator#Light Blue — Contact and data collection|Light Blue]].

## Stage 4 — [[Onboarding Status Indicator#Yellow — Follow-up after proposal|Yellow]] In Follow-up After Proposal

**Responsible:** [[Business Developer]] (with support from the [[Business Developer Coordinator]])
**Actions during this status:**

- BD or BDC creates the [[Terms and Conditions Document]], which establishes:
  - Pay rate
  - Bill rate
  - Overtime
  - Holidays
  - Calendar

**Advance →** when formal negotiation begins, moves to [[Onboarding Status Indicator#Pink — Terms negotiation|Pink]].

## Stage 5 — [[Onboarding Status Indicator#Pink — Terms negotiation|Pink]] Terms Negotiation

**Responsible:** [[Business Developer]] + [[Business Developer Coordinator]]

**Decision: Is the agreement closed?**

- **NO →** returns to the flow (renegotiation / [[Onboarding Status Indicator#Brown — Renegotiation / unblocking|Brown]] / End).
- **YES →** the BDC approves the conversion and the [[Hotel User Account]] is created in the system.

**When the user is created**, the [[Automatic Conversion Trigger]] fires (in parallel):

- System sends a welcome email to the hotel.
- System notifies the assigned BD.
- Hotel disappears from the prospect list.

**Advance →** moves to [[Onboarding Status Indicator#Orange — Signed agreement, active hotel client|Orange]].

## Stage 6 — [[Onboarding Status Indicator#Orange — Signed agreement, active hotel client|Orange]] Active Hotel Client

**Operational responsible:** [[Inspector]] + [[Recruiter|Recruiters]]
**Status:** the hotel already has a [[Hotel User Account|user account created]] and is working with Oranje.

- Passes to responsibility of [[Recruiter|Recruiters]].
- Operational cycle begins: [[Requisition|requisitions]] → coverage → [[Core/Modules/Schedule|Schedule]] → [[Timesheet]].
- BD and BDC remain as commercial references.

**Decision: Does the hotel stop operating?**

- **NO →** End (continues active).
- **YES →** moves to [[Onboarding Status Indicator#Black — Paused or inactive client|Black]].

## Stage 7 — [[Onboarding Status Indicator#Red — Rejection or no interest|Red]] Hotel Rejected the Proposal / Not Interested

**Responsible:** [[Business Developer]]

**Decision: Reactivate?**

- **NO →** End.
- **YES →** returns to [[Onboarding Status Indicator#Light Blue — Contact and data collection|Light Blue]].

## Stage 8 — [[Onboarding Status Indicator#Black — Paused or inactive client|Black]] Client Stopped Operating / Paused Relationship

**Responsible:** [[Business Developer Coordinator]]
**Reasons:** hotel closure, management change, pause, dispute.

**Decision: Reactivate?**

- **NO →** End.
- **YES →** returns to [[Onboarding Status Indicator#Light Blue — Contact and data collection|Light Blue]].

## Key Points

- Every status change is recorded with date, responsible, and comment.
- [[Onboarding Status Indicator#Orange — Signed agreement, active hotel client|Orange]] is the only status that enables the hotel to generate [[Requisition|requisitions]].
- The [[Hotel User Account]] is created upon approving the conversion at [[Onboarding Status Indicator#Pink — Terms negotiation|Pink]], just before the [[Automatic Conversion Trigger|automatic trigger]].
- [[Onboarding Status Indicator#Red — Rejection or no interest|Red]], [[Onboarding Status Indicator#Black — Paused or inactive client|Black]], and [[Onboarding Status Indicator#Brown — Renegotiation / unblocking|Brown]] always reactivate toward [[Onboarding Status Indicator#Light Blue — Contact and data collection|Light Blue]].
- Final conversion approval is given exclusively by the [[Business Developer Coordinator]].
