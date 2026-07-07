---
tags:
  - architecture
  - role/collaborator
aliases:
  - Collaborator Validations
---

# 4. VALIDATIONS — COLLABORATOR

---

## Onboarding Validations

| Case                                                              | System Behavior                                                                                                                                                              |
| ----------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Phase 2 submitted without SSN or ITIN                             | Does NOT block submission; shows informational notice: *"Without an SSN or ITIN, a 16% retention will be applied to your pay (refundable)"* — see [[Deductions]]            |
| SSN with incorrect format (not XXX-XX-XXXX)                       | Blocks field; displays: *"Invalid SSN format. Enter in XXX-XX-XXXX format"* (applies only if the collaborator enters an SSN)                                                 |
| ITIN with incorrect format (not 9XX-XX-XXXX)                      | Blocks field; displays: *"Invalid ITIN format. ITINs start with 9"* (applies only if the collaborator enters an ITIN)                                                        |
| Position not selected                                             | Blocks submission; displays: *"Select your position"*                                                                                                                        |
| English level not selected                                        | Blocks submission; displays: *"Select your English level"*                                                                                                                   |
| Experience level not selected                                     | Blocks submission; displays: *"Select your experience level"*                                                                                                                |
| Transportation type not selected                                  | Blocks submission; displays: *"Select your transportation type"*                                                                                                             |
| Hiring modality not selected                                      | Blocks submission; displays: *"Select a hiring modality"*                                                                                                                    |
| SSN/ITIN document in unsupported format (not JPG/PNG/PDF)         | Rejects file; displays: *"Only JPG, PNG, or PDF files are accepted"* (applies only if the collaborator attaches a document)                                                  |
| SSN/ITIN document exceeding 10 MB                                 | Rejects file; displays: *"File must not exceed 10 MB"* (applies only if the collaborator attaches a document)                                                                |
| Phase 3 submitted with incomplete emergency contact               | Blocks submission; displays: *"Emergency contact is required. Complete name, phone, and relationship"*                                                                       |
| Emergency contact phone with invalid format                       | Blocks field; displays: *"Enter a valid phone number"*                                                                                                                       |
| Blood type not selected                                           | Blocks submission; displays: *"Select your blood type. If you don't know it, select 'Don't know'"*                                                                           |

---

## QR Clock-in Validations (RF-C-03)

See full business rules in [[Collaborator Rules#Clock-in and Timesheet]]

| Case                                                              | System Behavior                                                                                                                                                              |
| ----------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Attempt to clock in without active Timesheet                      | Blocks action; displays: *"You don't have an active shift. Contact your supervisor"* (RR-C-03)                                                                               |
| Attempt to clock in with invalid or expired QR                   | Blocks action; displays: *"Invalid QR code. Request an updated QR from your supervisor"*                                                                                     |
| Attempt to clock in out of order (e.g. Lunch Out without Clock-in) | System alerts; displays: *"Register your Clock-in before punching Lunch Out"*                                                                                              |
| Duplicate punch in the same shift                                 | System blocks; displays: *"You already registered this punch today. If there's an error, contact your supervisor"*                                                           |
| No connection when clocking in (offline)                          | System queues the record locally; displays: *"No connection. Your punch will be registered when you regain signal"* (RNF-C-02)                                               |
| Lunch < 30 minutes                                                | System automatically applies a 30-min minimum deduction · Does not block the collaborator · See [[Collaborator Rules#Lunch Deduction]]                                       |
| Shift with no Lunch punch                                         | System applies auto-deduction of 30 min when closing the shift · See [[Collaborator Rules#Lunch Deduction]]                                                                  |

---

## Availability Validations — Yellow (RF-C-04)

| Case                                                              | System Behavior                                                                                                                                                              |
| ----------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Attempt to activate Yellow while in Café state (active assignment) | Blocks action; displays: *"You cannot declare yourself available while you have an active assignment"*                                                                      |
| Attempt to activate Yellow while in Purple, Red, Gray, or Black   | Blocks action; displays: *"You cannot modify your availability in your current state. Contact Recruitment"*                                                                  |
| Activate Yellow without explicit confirmation                     | System requires modal confirmation before executing the state change (RR-C-02)                                                                                               |

---

## Accident Report Validations (RF-C-05)

| Case                                                              | System Behavior                                                                                                                                                              |
| ----------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Report without accident date                                      | Blocks submission; displays: *"Indicate when the accident occurred"*                                                                                                         |
| Report with a future date                                         | Blocks submission; displays: *"The accident date cannot be in the future"*                                                                                                   |
| Report without description                                        | Blocks submission; displays: *"Briefly describe what happened (minimum 50 characters)"*                                                                                      |
| Description with fewer than 50 characters                         | Blocks submission; displays: *"The description must be at least 50 characters"*                                                                                              |
| Photo evidence > 10 MB                                            | Rejects file; displays: *"Maximum photo size: 10 MB"*                                                                                                                        |

---

## Profile Edit Validations (RF-C-10)

| Case                                                              | System Behavior                                                                                                                                                              |
| ----------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Attempt to edit SSN/ITIN after Phase 2 validation                 | Field locked; displays: *"To modify this information, contact your Recruiter"*                                                                                               |
| Own phone with invalid format                                     | Blocks save; displays: *"Enter a valid phone number"*                                                                                                                        |
| Save emergency data without contact name                          | Blocks save; displays: *"Emergency contact name is required"*                                                                                                                |

---

## General Validations

| Case                                                              | System Behavior                                                                                                                                                              |
| ----------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Session expired                                                   | Redirects to login; displays: *"Your session has expired, please sign in again"*                                                                                             |
| Attempt to access another collaborator's data                     | No access; the system never exposes other collaborators' data in the interface (RR-C-01)                                                                                     |
| Attempt to clock in via QR from web                               | Action not available on web; displays: *"QR clock-in requires your phone camera. Use the mobile app to clock in."* (RR-C-04)                                                |
