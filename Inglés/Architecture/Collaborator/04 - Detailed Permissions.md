---
tags:
  - architecture
  - role/collaborator
aliases:
  - Collaborator Detailed Permissions
---

# DETAILED PERMISSIONS BY ROLE

## ROL-C-01 · 👷 Collaborator (COL)

---

| Module                | Feature                                                      | Permission   | Description                                                                                                                                                                      |
| --------------------- | ------------------------------------------------------------ | ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Onboarding**        | Complete sign-up — Phase 2 (work data)                       | ➕ Create     | Position, English level, experience, transportation, hiring modality (required); SSN/ITIN optional; SSN/ITIN document optional (JPG/PNG/PDF, max. 10 MB); no SSN/ITIN → 16% refundable retention notice (RF-C-01, see [[Deductions]]) |
| Onboarding            | Complete emergency data — Phase 3                            | ➕ Create     | Emergency contact, blood type, allergies (RF-C-02)                                                                                                                               |
| Onboarding            | View sign-up validation status                               | 👁️ View     | Can only see if approved or pending; cannot see internal observations                                                                                                            |
| **Attendance / QR**   | Scan QR and clock in (6 punches)                             | ➕ Create     | Clock-in, Lunch Out, Lunch In, Break Out, Break In, Clock-out (RF-C-03)                                                                                                          |
| Attendance / QR       | Correct own punch                                            | —            | No access (exclusive to the Area Manager)                                                                                                                                        |
| Attendance / QR       | Generate QR                                                  | —            | No access (exclusive to the Area Manager / General Manager)                                                                                                                      |
| **My Schedule**       | View their weekly schedule                                   | 👁️ View     | Own schedule only; read-only (RF-C-06)                                                                                                                                           |
| My Schedule           | Edit Schedule                                                | —            | No access (RR-C-01; exclusive to the Area Manager)                                                                                                                               |
| **My Timesheet**      | View gross hours, lunch deduction, net hours                 | 👁️ View     | Own timesheet only; read-only (RF-C-07)                                                                                                                                          |
| My Timesheet          | View Extended Lunch Indicator                                | —            | No access (exclusive to Inspection and Recruitment)                                                                                                                              |
| My Timesheet          | Export own Timesheet                                         | 👁️ View     | PDF of the personal timesheet for the week                                                                                                                                       |
| **My Pay**            | View payment history                                         | 👁️ View     | Week, hotel(s), hours, amount paid, and payment date — only for already-released payments; no access to the current payment amount (RR-C-05; RF-C-08)                            |
| My Pay                | View internal financial details (pay rate, internal deductions, billing) | — | No access (exclusive to Accounting; RR-C-05)                                                                                                                              |
| My Pay                | View current or upcoming payment amount                      | —            | No access until Accounting releases the payment (RR-C-05)                                                                                                                        |
| **Availability**      | Activate voluntary availability — Yellow                     | ➕ Create     | Self-service without approval (RR-C-02; RF-C-04)                                                                                                                                 |
| Availability          | Deactivate Yellow                                            | 📝 Edit      | Can return to Strong Green by deactivating voluntary availability                                                                                                                |
| **Accident**          | Report workplace accident (Scenario A — they report first)   | ➕ Create     | Creates the initial card; notifies Supervisor and Inspector (RF-C-05)                                                                                                            |
| Accident              | Complete on-site accident information                        | —            | No access (exclusive to the Supervisor)                                                                                                                                          |
| Accident              | Close accident card                                          | —            | No access (exclusive to the Inspector)                                                                                                                                           |
| **Notifications**     | View own notifications                                       | 👁️ View     | Status changes, assignments, validations (RF-C-09)                                                                                                                               |
| **My Profile**        | View their profile data (Phase 1 + 2 + 3)                   | 👁️ View     | Own profile only (RR-C-01; RF-C-10)                                                                                                                                              |
| My Profile            | Edit own contact data                                        | 📝 Edit      | Phone, emergency data with defined limits                                                                                                                                        |
| My Profile            | Edit SSN/ITIN                                                | —            | No access after Phase 2 approval (sensitive data — requires Recruiter intervention)                                                                                              |
| My Profile            | View own status light state                                  | 👁️ View     | Current state color and name (RF-C-10)                                                                                                                                           |
| **System** (cross.)   | Receive push notifications                                   | 👁️ View     | Alerts for status changes, assignments, validations                                                                                                                              |

---

## Explicit section — The Collaborator CANNOT

- View any other collaborator's data (RR-C-01).
- Accept, reject, or request assignments.
- Modify the Schedule (read-only).
- Correct own or others' punches (exclusive to the Area Manager).
- Generate clock-in QR (exclusive to the Area Manager / General Manager).
- View the Extended Lunch Indicator (exclusive to Inspection and Recruitment).
- View the full Weekly Consolidated with internal deductions and Accounting financial details.
- Access management modules: requisitions, pool, Blacklist, accounting, QA.
- Put another collaborator in any status light state.
- Clock in via web (RR-C-04) — QR clock-in requires the phone camera and is exclusive to mobile.
