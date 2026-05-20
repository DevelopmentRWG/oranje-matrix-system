---
tags:
  - module/accounting
aliases:
  - Payroll Flow
  - Payroll Process
  - Pre-Payroll
---

# Payroll Flow

Semi-automated weekly process that transforms approved [[Timesheet|Timesheets]] into associate payments and hotel invoices. The system automates the calculation; the [[Contadora]] validates and the [[Manager de Contabilidad]] authorizes.

## Flow Steps

### 1. Automatic Generation of the Weekly Associate Summary

- The system groups approved [[Timesheet|Timesheets]] by associate/hotel/week
- Applies the pay rate from each [[Core/Módulos/Contrato|Contrato]]
- Calculates overtime according to each hotel's contract rules
- See [[Consolidado Semanal del Colaborador]] for structure and calculation

> [!success] **Automated** — No human intervention required.

### 2. Automatic Pre-Payroll Calculation

- The system generates the Pre-Payroll from the Summary:
  - Applies the **internal rate** if one exists (may be higher than the contractual rate)
  - Applies the active **[[Deducciones]]** for the associate (uniform, food, 16% withholding)
  - Applies **authorized overtime** (only hours approved by the hotel)
- The Pre-Payroll reflects the net amount each associate will receive

> [!success] **Automated** — No human intervention required.

### 3. Human Validation

- The [[Contadora]] reviews the generated Pre-Payroll
- Verifies for each line:
  - Associate ID is correct
  - Name/last name matches the ID
  - Hours are correct per approved Timesheet
  - Rate is correct (internal or contractual as applicable)
  - Discounts are correctly applied
  - Positions are correct if they have multiple
  - Hotel is correct if they work at multiple
- Approves, corrects, or rejects individual lines

> [!warning] **Semi-automated** — Requires validation by the [[Contadora]].

### 4. Automatic Hotel Invoice Generation

- The system generates the [[Facturación al Hotel|Hotel Invoice]] using the **bill rate** from the [[Core/Módulos/Contrato|Contrato]] (never the internal rate)
- Applies credits if applicable (e.g. food deduction)
- Overtime invoiced is only what was **authorized** by the hotel
- If the week spans two months, two separate invoices are generated

> [!success] **Automated** — No human intervention required.

### 5. Export to External Payment System

- The system generates the file/data required for the check provider
- Integration with the external provider is configurable

> [!success] **Automated** — No human intervention required.

### 6. Reconciliation

- The provider returns confirmation of the generated checks
- The [[Contadora]] validates that what was returned matches what was submitted
- Identifies discrepancies and resolves them before authorizing

> [!warning] **Semi-automated** — Requires validation by the [[Contadora]].

### 7. Final Authorization

- The [[Manager de Contabilidad]] releases payroll
- Payments are executed
- The system records the date and responsible for the authorization

> [!warning] **Semi-automated** — Requires authorization from the [[Manager de Contabilidad]].

## Automation Summary

| Step | Description | Automation |
| ---- | ----------- | -------------- |
| 1 | Weekly Associate Summary generation | Automated |
| 2 | Pre-Payroll calculation | Automated |
| 3 | Pre-Payroll validation | Semi-automated ([[Contadora]] validates) |
| 4 | Hotel Invoice generation | Automated |
| 5 | Export to check provider | Automated |
| 6 | Reconciliation | Semi-automated ([[Contadora]] validates) |
| 7 | Final authorization | Semi-automated ([[Manager de Contabilidad]] releases) |

## Related

- [[Consolidado Semanal del Colaborador]]
- [[Manager de Contabilidad]]
- [[Contadora]]
- [[Deducciones]]
- [[Facturación al Hotel]]
- [[Vacaciones]]
- [[Core/Módulos/Contrato|Contrato]]
- [[Timesheet]]
