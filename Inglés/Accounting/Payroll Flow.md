---
tags:
  - modulo/contabilidad
aliases:
  - Payroll Flow
  - Payroll Process
  - Pre-Payroll
---

# Payroll Flow

Semi-automated weekly process that transforms approved [[Timesheet|Timesheets]] into payments to the collaborator and invoices to the hotel. The system automates the calculation; the [[Accountant|Accountant]] validates and the [[Accounting Manager|Accounting Manager]] authorizes.

## Flow steps

### 1. Automatic generation of the Weekly Summary

- The system groups approved [[Timesheet|Timesheets]] by collaborator/hotel/week
- Applies the pay rate of each [[Core/Modules/Contrato|Contract]]
- Calculates overtime according to each hotel's contract rules
- See [[Collaborator Weekly Summary|Collaborator Weekly Summary]] for structure and calculation

> [!success] **Automated** — Requires no human intervention.

### 2. Automatic Pre-Payroll calculation

- The system generates the Pre-Payroll from the Summary:
  - Applies the **internal rate** if it exists (may be higher than the contractual rate)
  - Applies the collaborator's active **[[Deductions|Deductions]]** (uniform, meal, 16% withholding)
  - Applies the **authorized overtime** (only the hours approved by the hotel)
- The Pre-Payroll reflects the net amount each collaborator will receive

> [!success] **Automated** — Requires no human intervention.

### 3. Human validation

- The [[Accountant|Accountant]] reviews the generated Pre-Payroll
- Verifies for each line:
  - Correct collaborator ID
  - Name/surnames match the ID
  - Correct hours according to the approved Timesheet
  - Correct rate (internal or contractual as applicable)
  - Deductions correctly applied
  - Correct positions if there are multiple
  - Correct hotel if working at multiple
- Approves, corrects or rejects individual lines

> [!warning] **Semi-automated** — Requires validation by the [[Accountant|Accountant]].

### 4. Automatic generation of the Hotel Invoice

- The system generates the [[Hotel Invoicing|Hotel Invoice]] using the **bill rate** from the [[Core/Modules/Contrato|Contract]] (never the internal rate)
- Applies credits if applicable (e.g. meal deduction)
- The billed overtime is only the overtime **authorized** by the hotel
- If the week crosses two months, it generates two separate invoices

> [!success] **Automated** — Requires no human intervention.

### 5. Export to external payment system

- The system generates the file/data needed for the check provider
- The integration with the external provider is configurable

> [!success] **Automated** — Requires no human intervention.

### 6. Reconciliation

- The provider returns the confirmation of the generated checks
- The [[Accountant|Accountant]] validates that what was returned matches what was sent
- Identifies discrepancies and resolves them before authorizing

> [!warning] **Semi-automated** — Requires validation by the [[Accountant|Accountant]].

### 7. Final authorization

- The [[Accounting Manager|Accounting Manager]] releases the payroll
- The payments are executed
- The system records the date and person responsible for the authorization

> [!warning] **Semi-automated** — Requires authorization by the [[Accounting Manager|Accounting Manager]].

## Automation summary

| Step | Description | Automation |
| ---- | ----------- | -------------- |
| 1 | Generation of the Weekly Summary | Automatic |
| 2 | Pre-Payroll calculation | Automatic |
| 3 | Pre-Payroll validation | Semi-automatic ([[Accountant|Accountant]] validates) |
| 4 | Generation of the Hotel Invoice | Automatic |
| 5 | Export to check provider | Automatic |
| 6 | Reconciliation | Semi-automatic ([[Accountant|Accountant]] validates) |
| 7 | Final authorization | Semi-automatic ([[Accounting Manager|Accounting Manager]] releases) |

## Related

- [[Collaborator Weekly Summary|Collaborator Weekly Summary]]
- [[Accounting Manager|Accounting Manager]]
- [[Accountant|Accountant]]
- [[Deductions|Deductions]]
- [[Hotel Invoicing|Hotel Invoice]]
- [[Vacation|Vacation]]
- [[Core/Modules/Contrato|Contract]]
- [[Timesheet]]
