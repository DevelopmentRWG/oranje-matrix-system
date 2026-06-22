---
tags:
  - modulo/onboarding-hotel
  - concepto
aliases:
  - Automatic Trigger
  - Automatic Conversion Trigger
---

# Automatic Conversion Trigger

Set of automatic actions that the system executes **in parallel** when the [[Business Developer Coordinator]] approves the conversion in [[Onboarding Status Light|Onboarding Status Pink]] and the [[Hotel User|Hotel User]] is created.

## Automatic actions

- The system sends a **welcome email** to the hotel.
- The system **notifies the assigned [[Business Developer|BD]]**.
- The hotel **disappears from the prospect list**.

## Trigger

- **Event:** approval of the conversion in [[Onboarding Status Light|Onboarding Status Pink]].
- **Precondition:** creation of the [[Hotel User|Hotel User]] in the system.
- **Result:** the hotel moves to [[Onboarding Status Light|Onboarding Status Orange]] and is enabled to generate [[Requisition|requisitions]].

## Related

- [[Onboarding Flow|Onboarding Flow]]
- [[Hotel User|Hotel User]]
- [[Onboarding Status Light|Onboarding Status Pink]]
- [[Onboarding Status Light|Onboarding Status Orange]]
