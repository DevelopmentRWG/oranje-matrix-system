---
tags:
  - module/hotel-onboarding
  - concept
aliases:
  - Automatic Trigger
  - Automatic Conversion Trigger
---

# Automatic Conversion Trigger

Set of automatic actions that the system executes **in parallel** when the [[Business Developer Coordinator]] approves the conversion at [[Semáforo Onboarding|Onboarding Status Pink]] and the [[Usuario del Hotel]] is created.

## Automatic Actions

- System sends a **welcome email** to the hotel.
- System **notifies the assigned [[Business Developer|BD]]**.
- The hotel **disappears from the prospect list**.

## Trigger

- **Event:** conversion approval at [[Semáforo Onboarding|Onboarding Status Pink]].
- **Precondition:** creation of the [[Usuario del Hotel]] in the system.
- **Result:** the hotel moves to [[Semáforo Onboarding|Onboarding Status Orange]] and is enabled to generate [[Requisición|requisitions]].

## Related

- [[Flujo de Onboarding]]
- [[Usuario del Hotel]]
- [[Semáforo Onboarding|Onboarding Status Pink]]
- [[Semáforo Onboarding|Onboarding Status Orange]]
