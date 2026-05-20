---
tags:
  - module/hotel-onboarding
  - concept
aliases:
  - Automatic Trigger
  - Automatic Conversion Trigger
---

# Automatic Conversion Trigger

Set of automatic actions that the system executes **in parallel** when the [[Business Developer Coordinator]] approves the conversion at [[Onboarding Status Indicator|Onboarding Status Pink]] and the [[Hotel User Account]] is created.

## Automatic Actions

- System sends a **welcome email** to the hotel.
- System **notifies the assigned [[Business Developer|BD]]**.
- The hotel **disappears from the prospect list**.

## Trigger

- **Event:** conversion approval at [[Onboarding Status Indicator|Onboarding Status Pink]].
- **Precondition:** creation of the [[Hotel User Account]] in the system.
- **Result:** the hotel moves to [[Onboarding Status Indicator|Onboarding Status Orange]] and is enabled to generate [[Requisition|requisitions]].

## Related

- [[Onboarding Flow]]
- [[Hotel User Account]]
- [[Onboarding Status Indicator|Onboarding Status Pink]]
- [[Onboarding Status Indicator|Onboarding Status Orange]]
