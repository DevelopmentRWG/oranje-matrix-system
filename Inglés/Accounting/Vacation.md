---
tags:
  - modulo/contabilidad
aliases:
  - Vacation
  - Vacation Calculation
---

# Vacation

Automated calculation of a collaborator's vacation pay, based on the average of hours worked over the last 52 weeks.

## Formula

**Average hours = Σ net hours paid (last 52 weeks) ÷ 52**

- The system uses the collaborator's historical [[Collaborator Weekly Summary|Weekly Summaries]] as the source
- If the collaborator has less than 52 weeks of seniority, the average is taken over the available weeks

## Complexity with multiple rates

When the collaborator worked with different rates during the period (different hotels or different positions), the system must:

1. **Separate** the weeks/hours by rate
2. **Calculate** the average for each rate independently
3. **Present** the breakdown:
   - Average per hotel
   - Average per position
   - Average per rate

> [!example] **Example**
> Collaborator worked 30 weeks at Hotel A (Housekeeper, $14/hr) and 22 weeks at Hotel B (Breakfast, $13/hr):
> - Hotel A average: Σ Hotel A hours ÷ 30
> - Hotel B average: Σ Hotel B hours ÷ 22

## Functionality in the system

- The [[Accountant|Accountant]] selects the collaborator and the period
- The system calculates automatically without manual intervention
- Presents the result with a breakdown by rate/hotel/position
- Allows adjusting the range of weeks if a partial calculation is required

## Related

- [[Collaborator Weekly Summary|Collaborator Weekly Summary]]
- [[Accounting Manager|Accounting Manager]]
- [[Accountant|Accountant]]
- [[Core/Modules/Contrato|Contract]]
- [[Accounting/Payroll Flow|Payroll Flow]]
