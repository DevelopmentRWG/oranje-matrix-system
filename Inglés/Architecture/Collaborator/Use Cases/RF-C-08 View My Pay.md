---
tags:
  - architecture
  - role/collaborator
  - use-case
aliases:
  - CU RF-C-08
---

# 🪪 ID: RF-C-08
🏷️ **Name:** View My Pay
**Use case alias:** View My weekly pay history

**Story:**
The Collaborator wants to check their received payments. From the app they access "My Pay" and see the **payment history of already released payments**: week, hotel(s) where they worked, net hours, amount paid, and payment date. The current week appears in the list as "Calculating", with no amount visible. The Collaborator **cannot see the amount of their current or upcoming payment**: the calculation is exclusive to Accounting and is only revealed to the Collaborator once the payment has been released. This view is a distinct and limited concept, separate from the [[Collaborator Weekly Summary]], which remains for exclusive use by the Accounting department (RR-C-05).

> [!info]
> The collaborator's payment history and the [[Collaborator Weekly Summary]] are distinct documents with distinct audiences. The Weekly Summary includes: pay rate, internal rate, individual deductions, hotel invoicing, and complete payroll data — all exclusive to Accounting. The collaborator's history shows only: week, hotel(s), net hours, amount paid, and payment date — only for already released payments.

**Acceptance criteria (RR-C-05):**
Read-only view. Only shows the collaborator's own data. Information visible (only for already released payments): week and date range, hotel(s) where they worked that week, net hours per hotel, amount paid, and payment date. The current week is shown in the list with a "Calculating" status and **no amount**: the current or upcoming payment amount is not visible to the Collaborator until Accounting releases it. Information **never visible** to the collaborator: internal pay rate, contractual rate, individual deductions (uniform, food, retention), hotel invoicing information, or any other data from the full Weekly Summary. The collaborator can navigate between previous weeks. If there are no records for the selected week → `Shows empty state: "No payment records for this week"`.

**Documentation:**
- PRD: [[03 - PRD]]
- Flow: [[Collaborator Weekly Summary]] — Released payment history
- Prototype: (Figma link)

**Flow:**
`App → My Pay Section` → AUTOMATIC → `System loads released payment history` → `List of entries: week · hotel(s) · hours · amount paid · payment date` → Current week → `Shows entry with "Calculating" status · no amount` / Week with no records → `Shows empty state: "No payment records for this week"`
