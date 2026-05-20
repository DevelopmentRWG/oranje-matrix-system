---
tags:
  - module/accounting
aliases:
  - Deductions
  - Deduction
---

# Deductions

Monetary discounts that the system automatically applies to the associate's check before releasing payment. Each deduction has a specific trigger and activation conditions.

## Deduction Types

### Uniform

| Field | Value |
| ----- | ----- |
| Amount | $15 USD per uniform |
| Trigger | The [[Inspección/Inspector\|Inspector]] registers uniform delivery or loss via form |
| Application | Applied automatically to the next [[Consolidado Semanal del Colaborador\|Weekly Summary]] |
| Cumulative | Yes — if the associate loses a uniform and receives another, a new deduction is added |

### Food

| Field | Value |
| ----- | ----- |
| Amount | $3 USD per day worked |
| Trigger | Hotel configuration in the [[Core/Módulos/Contrato\|Contrato]] (field: "Deduct food: yes/no") |
| Application | Only on days where the associate has a recorded [[Timesheet]] |
| Particularity | Deducted from the associate AND credited to the hotel on their [[Facturación al Hotel\|Invoice]] |

> [!note] This deduction is based on hotel configuration. Not all hotels apply it.

### 16% Withholding

| Field | Value |
| ----- | ----- |
| Amount | 16% of the total check amount |
| Trigger | [[Colaborador/Colaborador\|Associate]] field: "Has SSN/TaxID: no" |
| Activation | Automatic upon registering the associate without tax documents |
| Deactivation | The [[Contadora]] deactivates it manually when the associate submits documents |
| Refund | Upon deactivation, the system allows generating a refund for the accumulated withheld amount |

> [!important] The 16% withholding is refundable. The system must maintain a historical record of the accumulated withheld amount in order to generate the refund when applicable.

## System Behavior

- Deductions are applied in step 2 of the [[Contabilidad/Flujo de Nómina|Flujo de Nómina]] (Pre-Payroll calculation)
- They reduce the associate's net check amount
- The [[Contadora]] verifies that deductions are correctly applied in step 3 (validation)
- The system maintains a history of deductions applied per associate/week

## Related

- [[Consolidado Semanal del Colaborador]]
- [[Contabilidad/Flujo de Nómina|Flujo de Nómina]]
- [[Contadora]]
- [[Facturación al Hotel]]
- [[Inspección/Inspector|Inspector]]
- [[Core/Módulos/Contrato|Contrato]]
- [[Colaborador/Colaborador|Colaborador]]
