---
tags:
  - architecture
  - role/collaborator
aliases:
  - Collaborator Form Fields
---

# 3. FORM FIELDS — COLLABORATOR

---

## A) Sign-up Form — Phase 2 (RF-C-01)

Completed by the Collaborator themselves. Source: [[Collaborator#Phase 2 — App sign-up]]

| Field                  | Input Type         | Required                              | Validation                                                                                    | Description                                           |
| ---------------------- | ------------------ | ------------------------------------- | --------------------------------------------------------------------------------------------- | ----------------------------------------------------- |
| SSN                    | Text               | No (optional)                         | Format XXX-XX-XXXX · Mask after entry · Encrypted in storage                                  | Social Security Number                                |
| ITIN                   | Text               | No (optional)                         | Format 9XX-XX-XXXX · Mask after entry · Encrypted in storage                                  | Individual Taxpayer Identification Number             |
| Position               | Select             | Yes                                   | Catalog from [[Posiciones]] (Housekeeper, Hoseman, Chef, Laundry, etc.)                       | Desired position                                      |
| English level          | Select             | Yes                                   | Catalog from [[English Levels]] (Basic / Intermediate / Advanced / Conversational)            | Language proficiency                                  |
| Experience level       | Select             | Yes                                   | Options: No experience / 1–2 years / 3–5 years / More than 5 years                           | Years of experience in the position                   |
| Transportation type    | Select             | Yes                                   | Options: Own / Public transportation / Other                                                  | How they commute to the hotel                         |
| Hiring modality        | Select             | Yes                                   | Catalog from [[Employment Types]] (Full time / Part time / Temporary / On request)            | Preferred hiring modality                             |
| SSN/ITIN Document      | File (JPG/PNG/PDF) | No (optional · recommended if SSN/ITIN provided) | Max. 10 MB · Enabled upon entering SSN/ITIN · Secure storage (RNF-C-03)             | Photo/scan of SSN card or ITIN document               |

> [!note]
> SSN and ITIN are optional. If the collaborator provides neither (no SSN nor ITIN/TaxID), a **16% retention** is automatically activated on their pay (refundable) — see [[Deductions]]. If they provide an ITIN, the retention is not applied (ITIN is a TaxID).

---

## B) Emergency Data Form — Phase 3 (RF-C-02)

Completed by the Collaborator themselves. Source: [[Collaborator#Phase 3 — Emergency data]]

| Field                              | Input Type | Required | Validation                                                       | Description                                                          |
| ---------------------------------- | ---------- | -------- | ---------------------------------------------------------------- | -------------------------------------------------------------------- |
| Emergency contact — name           | Text       | Yes      | Min. 3 characters                                                | Full name of the person to contact in case of emergency              |
| Emergency contact — phone          | Tel        | Yes      | Valid phone format                                               | Contact's phone number                                               |
| Emergency contact — relationship   | Select     | Yes      | Options: Mother / Father / Spouse / Sibling / Child / Friend / Other | Relationship to the collaborator                                 |
| Blood type                         | Select     | Yes      | Options: A+, A–, B+, B–, AB+, AB–, O+, O–, Don't know          | Blood group                                                          |
| Allergies or medical conditions    | Textarea   | No       | Max. 500 characters                                              | Relevant medical information for emergencies                         |

---

## C) Accident Report Form (RF-C-05)

Scenario A: the Collaborator reports first. Source: [[Workplace Accident]]

| Field                        | Input Type | Required | Validation                            | Description                                                          |
| ---------------------------- | ---------- | -------- | ------------------------------------- | -------------------------------------------------------------------- |
| Accident date                | Date       | Yes      | Current or past date (not future)     | When it occurred                                                     |
| Accident time                | Time       | Yes      | HH:MM format (24h)                    | What time it occurred                                                |
| Accident description         | Textarea   | Yes      | Min. 50 characters                    | Description of how the accident occurred from their perspective      |
| Evidence (photos)            | File       | No       | JPG/PNG, max. 10 MB                   | Photos of the incident or injury                                     |
| Geolocation (mobile)         | Auto       | No       | Auto from device                      | Location when the report is opened (if the collaborator allows access) |

> [!info]
> On-site information (exact location, detailed circumstances, witnesses, immediate care) is captured by the [[Workplace Accident|Supervisor]] who physically attends. The Collaborator only generates the initial signal and briefly describes the incident. See [[Workplace Accident]] for the full card structure.

---

## D) Availability Toggle — Activate Yellow (RF-C-04)

Not an extensive form; it is an activation control with confirmation.

| Field                | Input Type      | Required             | Validation                                                                  | Description                                                                 |
| -------------------- | --------------- | -------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Availability toggle  | Toggle (On/Off) | Yes (explicit action) | Only available if the collaborator is in Strong Green, Orange, or Pink     | Activates the Yellow state in the [[Collaborator Status Light]]             |
| Confirmation         | Modal           | Yes                  | "Confirm availability" button required                                      | System requests confirmation before changing the state                      |

> [!important]
> Activating Yellow is the **only autonomous state-change action** of the Collaborator (RR-C-02). It does not require approval from any other role. The system executes the change immediately upon confirmation.

---

## E) Filters and Read-only Views

### My Schedule (RF-C-06)

| Field       | Input Type | Description                                    |
| ----------- | ---------- | ---------------------------------------------- |
| Week        | Selector   | Navigate between current and next week         |
| View        | Toggle     | List view / Calendar view                      |

### My Timesheet (RF-C-07)

| Field       | Input Type | Description                                    |
| ----------- | ---------- | ---------------------------------------------- |
| Week        | Selector   | Current week and previous weeks                |

### My Pay (RF-C-08)

Read-only view. Shows the history of already-released payments; the current week appears as "In calculation" without an amount (RR-C-05).

| Column         | Type     | Description                                                                  |
| -------------- | -------- | ---------------------------------------------------------------------------- |
| Week           | Text     | Week label (e.g. "Week 24 · Jun 9–15")                                       |
| Hotel(s)       | Text     | Hotel(s) where they worked that week                                         |
| Hours          | Numeric  | Net hours worked in the week                                                 |
| Amount paid    | Currency | Amount received (visible only if payment was released)                       |
| Payment date   | Date     | Date Accounting released the payment                                         |
| Status         | Label    | "Paid" for released payments; "In calculation" for the current week          |
