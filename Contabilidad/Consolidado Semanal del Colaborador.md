---
tags:
  - module/accounting
aliases:
  - Weekly Associate Summary
  - Weekly Summary
---

# Weekly Associate Summary

Weekly summary that groups all [[Timesheet|Timesheets]] for an associate across the hotels where they worked during the week, applying the [[Core/Modules/Contract|pay rate]] for each hotel to calculate the total amount to be paid.

## Origin

- The system automatically generates the Weekly Summary at the end of the hotel's week (according to the week start/end configuration in the [[Core/Modules/Contract|Contract]]), based on the [[Timesheet|Timesheets]] for that week
- If the associate worked at a single hotel, the summary contains a single Timesheet
- If they worked at multiple hotels (via temporary assignment [[Associate Status Indicator|Brown]]), the summary groups the Timesheets from each hotel

## Structure

| Field              | Description                                                                    |
| ------------------ | ------------------------------------------------------------------------------ |
| Associate          | Associate name and details                                                     |
| Week               | Week number and date range                                                     |
| Detail per hotel   | Hotel, net hours, pay rate from the [[Core/Modules/Contract\|Contract]], subtotal |
| Overtime per hotel | Overtime hours calculated per each hotel's contract policy                    |
| Total to pay       | Sum of subtotals across all hotels                                             |

## Calculation

- **For each hotel where they worked:**
  - Net hours × hotel contract pay rate = regular subtotal
  - Overtime hours × hotel contract overtime rate = overtime subtotal
- **Overtime threshold:** calculated per hotel from **40 gross weekly hours** (8 hrs × 5 days). Hours exceeding that threshold at a hotel are considered overtime for that hotel
- **Total to pay** = Σ (regular subtotal + overtime subtotal) across all hotels
- Overtime is calculated **per hotel**, not globally across hotels

> [!info] **Holidays** — The [[Core/Modules/Contract|Contract]] defines the handling and surcharges for holidays, but the rule for calculating holiday surcharges has not yet been defined. Once defined, it will be integrated into this section.

### Internal Rate

- The pay rate applied to the associate may be **higher** than the rate agreed in the hotel's [[Core/Modules/Contract|Contract]] (by internal agreement: experience, seniority, or negotiation with the associate)
- When an internal rate exists, the system uses it to calculate the associate's payment instead of the contractual rate
- The internal rate is **not reflected** in the [[Hotel Invoice|Hotel Invoice]] (which always uses the contractual bill rate)
- Visible only to Accounting ([[Accounting Manager]] and [[Accountant]])

### Deductions

- Before releasing payment, the system applies the associate's active [[Deductions]]
- Deductions (uniform, food, 16% withholding) reduce the net check amount
- See [[Deductions]] for details on each type and its conditions

### Multiple Positions at the Same Hotel

- An associate may hold two or more different positions at the same hotel during the same week (e.g., Breakfast + Housekeeper)
- Each position has its own rate
- They are presented as **separate lines** in the Summary, each with their own independent hours and subtotal

### Partially Authorized Overtime

- The hotel may authorize only a fraction of the overtime worked
- The system allows the [[Accounting Manager]] to adjust the payable OT hours based on what the hotel authorized
- **Example:** associate worked 50 hrs (10 OT), hotel authorizes only 5 OT → 5 OT are paid to the associate and 5 OT are billed to the hotel
- Unauthorized OT hours are recorded but not billed to the hotel

### Check Assignment

- When the associate worked at multiple hotels during the week, the check is assigned to the hotel where they accumulated the **most hours**
- This assignment is for check printing and physical delivery purposes

## Period

- The Weekly Summary is generated at the close of each week
- The payment period is **weekly**, aligned with the [[Timesheet]] cycle
- Oranje pays the associate; the hotel pays Oranje based on their [[Core/Modules/Contract|Contract]] bill rate

## Visibility

> [!important] The Weekly Associate Summary is for exclusive use by Oranje's **Accounting** department. The hotel and the associate do not have access to this document.

## Validation

- The system generates the Summary automatically at the end of each week
- The [[Accountant]] reviews the Summary and the [[Accounting Manager]] approves it before executing the associate payment
- Payment is not executed without the [[Accounting Manager]]'s approval

## Related

- [[Timesheet]]
- [[Core/Modules/Contract|Contract]]
- [[Core/Modules/Schedule|Schedule]]
- [[Associate Status Indicator]]
- [[Accounting/Payroll Flow|Payroll Flow]]
- [[Accounting Manager]]
- [[Accountant]]
- [[Deductions]]
- [[Hotel Invoice]]
- [[Vacation Pay]]
