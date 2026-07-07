---
tags:
  - architecture
  - role/collaborator
aliases:
  - Collaborator Mockup
  - Collaborator UI
  - Collaborator UI Decisions
---

# Mockup and UI Decisions — Collaborator

Documents the interactive web mockup for the Collaborator role and the design decisions made during its implementation.

> [!info]
> The mockup lives in the mockups repo: `oranje-mockups/Mockups/Colaborador/Colaborador - Oranje.html`. The visual source of truth (tokens and components) is `oranje-seed.css` — see [[Design Conventions]].

---

## Implemented Screens

| Screen | Description |
|---|---|
| **Onboarding (Phase 2 + Phase 3)** | Full-screen wizard (no sidebar, no access yet) for the new collaborator: stepper Work data (Phase 2) → Emergency (Phase 3) → Review → Submit. Phase 2 includes optional SSN/ITIN fields and the document upload field (JPG/PNG/PDF, max. 10 MB, also optional · recommended if SSN/ITIN provided); the upload field is enabled upon entering SSN or ITIN. If the collaborator provides neither SSN nor ITIN, a banner notifies them of the 16% retention (refundable) and they can proceed anyway. Ends on a **Pending validation** screen (White state): no access to modules until the Recruiter validates (RF-08). RF-C-01, RF-C-02. In the mockup this alternates with the **demo switch** (floating, bottom right): "New collaborator" / "Already in Oranje". |
| **Home** | Personal dashboard: greeting with status light state ([[Collaborator Status Light]]), weekly KPIs, next shift, and quick access links. |
| **My Schedule** | Weekly calendar of assigned shifts; read-only. |
| **Punch** | View of the status of the 6 daily punches. Actual registration is a mobile QR action (RR-C-04). |
| **My Timesheet** | Weekly hours table with lunch deduction per shift and total net hours. |
| **My Pay** | History of received payments (week, hotel, hours, amount, date). The current week is shown as "In calculation" without an amount; the upcoming payment is not visible (RR-C-05). |
| **Availability** | Toggle to activate Yellow state (voluntary availability); includes a visual stepper of the flow (Yellow → Café → Green), history of recent extra shifts, and a guide on when to activate it. |
| **Report accident** | Accident report form (Scenario A); upon submission activates Gray state and notifies the Inspector. |

> [!note]
> **Notifications** and **My Profile** are accessed from the header (bell and avatar), not from the sidebar. They are not independent modules in the side navigation.

---

## UI Decisions

- **Onboarding access gate.** Without completing Phase 2 + Phase 3 and being validated by the Recruiter, the collaborator remains in White state (Pre-assignment) **with no access to modules** and no possibility of assignment. The mockup implements the sign-up wizard (Phase 2/3) and the "Pending validation" screen. Rationale: RF-C-01, RF-C-02, RF-08; White → Strong Green transition of the [[Collaborator Status Light]].
- **Passive model reflected in the UI.** The Collaborator has no assignment or management controls. The interface exposes only their own data and their two autonomous actions: activate Yellow and report accident. Rationale: RR-C-01, RR-C-02.
- **QR clock-in is a mobile action.** The Punch screen on web shows the status of the 6 punches but does not allow registering them. Actual registration requires the device camera. Rationale: RR-C-04.
- **Payment history, no upcoming payment.** My Pay shows only already-released payments (week, hotel, hours, amount, date); the current or upcoming payment amount is not revealed to the Collaborator until Accounting releases it. The current week appears as "In calculation" without an amount. Rationale: RR-C-05.
- **Notifications and profile in the header.** Bell (notifications) and avatar (profile menu) live in the header, following the global convention. See [[General App Structure]].
- **Shared design seed.** The mockup links `oranje-seed.css` and only adds Collaborator-specific styles. Does not reimplement components. See [[Design Conventions]].
- **SSN/ITIN optional + 16% retention.** SSN, ITIN, and the SSN/ITIN document are optional in Phase 2. If the collaborator provides neither SSN nor ITIN, a banner notifies them of the 16% retention (refundable) and they can proceed anyway. The document upload field is enabled upon entering an SSN or ITIN. Rationale: [[Deductions]] (trigger "no SSN/TaxID"); also closes the inconsistency with RF-08.

---

## Related

- [[Design Conventions]]
- [[General App Structure]]
- [[03 - PRD]]
- [[07 - Feature Map]]
- [[08 - User Actions]]
- [[Collaborator Status Light]]
- [[00 - Collaborator Architecture]]
