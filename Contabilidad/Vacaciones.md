---
tags:
  - module/accounting
aliases:
  - Vacation Pay
  - Vacation Pay Calculation
---

# Vacation Pay

Automated calculation of an associate's vacation pay, based on the average hours worked over the last 52 weeks.

## Formula

**Average hours = Σ net paid hours (last 52 weeks) ÷ 52**

- The system uses the associate's historical [[Weekly Associate Summary|Weekly Summaries]] as the source
- If the associate has fewer than 52 weeks of seniority, the average is calculated over the available weeks

## Complexity with Multiple Rates

When the associate worked with different rates during the period (different hotels or different positions), the system must:

1. **Separate** the weeks/hours by rate
2. **Calculate** the average for each rate independently
3. **Present** the breakdown:
   - Average per hotel
   - Average per position
   - Average per rate

> [!example] **Example**
> Associate worked 30 weeks at Hotel A (Housekeeper, $14/hr) and 22 weeks at Hotel B (Breakfast, $13/hr):
> - Hotel A average: Σ Hotel A hours ÷ 30
> - Hotel B average: Σ Hotel B hours ÷ 22

## System Functionality

- The [[Accountant]] selects the associate and the period
- The system calculates automatically without manual intervention
- Presents the result with a breakdown by rate/hotel/position
- Allows adjusting the week range if a partial calculation is required

## Related

- [[Weekly Associate Summary]]
- [[Accounting Manager]]
- [[Accountant]]
- [[Core/Modules/Contract|Contract]]
- [[Accounting/Payroll Flow|Payroll Flow]]
