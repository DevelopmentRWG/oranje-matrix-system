---
tags:
  - modulo/contabilidad
aliases:
  - Deductions
  - Deduction
---

# Deductions

Monetary deductions that the system automatically applies to the collaborator's check before releasing the payment. Each deduction has a specific trigger and activation conditions.

## Types of deduction

### Uniform

| Field | Value |
| ----- | ----- |
| Amount | $15 USD per uniform |
| Trigger | The [[Inspection/Inspector\|Inspector]] records delivery or loss of a uniform via a form |
| Application | Applied automatically to the next [[Collaborator Weekly Summary\|Weekly Summary]] |
| Stackable | Yes — if the collaborator loses the uniform and receives another, a new deduction is added |

### Meal

| Field | Value |
| ----- | ----- |
| Amount | $3 USD per day worked |
| Trigger | Hotel configuration in the [[Core/Modules/Contrato\|Contract]] (field: "Deduct meal: yes/no") |
| Application | Only on days where the collaborator has a registered [[Timesheet]] |
| Particularity | It is deducted from the collaborator AND credited to the hotel on its [[Hotel Invoicing\|Invoice]] |

> [!note] This deduction is by hotel configuration. Not all hotels apply it.

### 16% Withholding

| Field | Value |
| ----- | ----- |
| Amount | 16% of the total check amount |
| Trigger | [[Collaborator/Collaborator\|Collaborator]] field: "Has SSN/TaxID: no" |
| Activation | Automatic when registering the collaborator without tax documents |
| Deactivation | The [[Accountant\|Accountant]] deactivates it manually when the collaborator submits documents |
| Refund | Upon deactivation, the system allows generating a refund of the accumulated withheld amount |

> [!important] The 16% withholding is refundable. The system must keep a historical record of the accumulated withheld amount in order to generate the refund when appropriate.

## Behavior in the system

- Deductions are applied in step 2 of the [[Accounting/Payroll Flow|Payroll Flow]] (Pre-Payroll calculation)
- They reduce the net amount of the collaborator's check
- The [[Accountant|Accountant]] verifies that the deductions are correctly applied in step 3 (validation)
- The system keeps a history of deductions applied per collaborator/week

## Related

- [[Collaborator Weekly Summary|Collaborator Weekly Summary]]
- [[Accounting/Payroll Flow|Payroll Flow]]
- [[Accountant|Accountant]]
- [[Hotel Invoicing|Hotel Invoice]]
- [[Inspection/Inspector|Inspector]]
- [[Core/Modules/Contrato|Contract]]
- [[Collaborator/Collaborator|Collaborator]]
