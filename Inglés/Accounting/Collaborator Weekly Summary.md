---
tags:
  - modulo/contabilidad
aliases:
  - Collaborator Weekly Summary
  - Weekly Summary
---

# Collaborator Weekly Summary

Weekly summary that groups all of a collaborator's [[Timesheet|Timesheets]] across the hotels where they worked during the week, applying each hotel's [[Core/Modules/Contrato|pay rate]] to calculate the total amount to be paid.

## Origin

- The system automatically generates the Weekly Summary at the end of the hotel's week (according to the week start/end configuration of the [[Core/Modules/Contrato|Contract]]), based on that week's [[Timesheet|Timesheets]]
- If the collaborator worked at a single hotel, the summary contains a single Timesheet
- If they worked at multiple hotels (via temporary [[Collaborator Status Light|Brown]] assignment), the summary groups the Timesheets from each hotel

## Structure

| Field             | Description                                                                    |
| ----------------- | ------------------------------------------------------------------------------ |
| Collaborator      | Collaborator's name and details                                                |
| Week              | Week number and date range                                                     |
| Detail per hotel  | Hotel, net hours, pay rate from the [[Core/Modules/Contrato\|Contract]], subtotal |
| Overtime per hotel | Overtime hours calculated according to each hotel's contract policy           |
| Total to pay      | Sum of subtotals across all hotels                                             |

## Calculation

- **For each hotel where they worked:**
  - Net hours × that hotel's contract pay rate = regular subtotal
  - Overtime hours × that hotel's contract overtime rate = overtime subtotal
- **Overtime threshold:** calculated per hotel starting from **40 gross hours per week** (8 hrs × 5 days). Hours exceeding that threshold at a hotel are considered that hotel's overtime
- **Total to pay** = Σ (regular subtotal + overtime subtotal) across all hotels
- Overtime is calculated **per hotel**, not globally across hotels

> [!info] **Holidays** — The [[Core/Modules/Contrato|Contract]] defines the handling and surcharges for holidays, but the surcharge calculation rule for holidays is not yet defined. Once defined, it will be integrated into this section.

### Internal rate

- The pay rate applied to the collaborator may be **higher** than the rate agreed in the hotel's [[Core/Modules/Contrato|Contract]] (by internal agreement: experience, seniority or negotiation with the collaborator)
- When an internal rate exists, the system uses it to calculate the payment to the collaborator instead of the contractual rate
- The internal rate is **not reflected** in the [[Hotel Invoicing|Hotel Invoice]] (that always uses the contractual bill rate)
- Visible only to Accounting ([[Accounting Manager|Accounting Manager]] and [[Accountant|Accountant]])

### Deductions

- Before releasing the payment, the system applies the collaborator's active [[Deductions|Deductions]]
- Deductions (uniform, meal, 16% withholding) reduce the net check amount
- See [[Deductions|Deductions]] for the detail of each type and its conditions

### Multiple positions at the same hotel

- A collaborator can hold two or more different positions at the same hotel during the same week (e.g. Breakfast + Housekeeper)
- Each position has its own rate
- They are presented as **separate lines** in the Summary, each with its own independent hours and subtotal

### Partially authorized overtime

- The hotel may authorize only a fraction of the overtime worked
- The system allows the [[Accounting Manager|Accounting Manager]] to adjust the payable OT hours according to what the hotel authorized
- **Example:** collaborator worked 50 hrs (10 OT), hotel authorizes only 5 OT → 5 OT are paid to the collaborator and 5 OT are billed to the hotel
- Unauthorized OT hours are recorded but not billed to the hotel

### Check assignment

- When the collaborator worked at multiple hotels during the week, the check is assigned to the hotel where they accumulated the **greatest number of hours**
- This assignment is for purposes of printing and delivering the physical check

## Period

- The Weekly Summary is generated at the close of each week
- The payment period is **weekly**, aligned with the [[Timesheet]] cycle
- Oranje pays the collaborator; the hotel pays Oranje according to the bill rate of its [[Core/Modules/Contrato|Contract]]

## Visibility

> [!important] The Weekly Summary is for the exclusive use of Oranje's **Accounting** department. The hotel and the collaborator do not have access to this document.

## Validation

- The system generates the Summary automatically at the end of each week
- The [[Accountant|Accountant]] reviews the Summary and the [[Accounting Manager|Accounting Manager]] approves it before executing the payment to the collaborator
- The payment is not executed without the [[Accounting Manager|Accounting Manager]]'s approval

## Related

- [[Timesheet]]
- [[Core/Modules/Contrato|Contract]]
- [[Core/Modules/Schedule|Schedule]]
- [[Collaborator Status Light|Collaborator Status Light]]
- [[Accounting/Payroll Flow|Payroll Flow]]
- [[Accounting Manager|Accounting Manager]]
- [[Accountant|Accountant]]
- [[Deductions|Deductions]]
- [[Hotel Invoicing|Hotel Invoice]]
- [[Vacation|Vacation]]
