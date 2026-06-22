---
tags:
  - modulo/core
aliases:
  - Timesheet Compliance Indicator
  - Compliance Indicator
  - Compliance Status Green
  - Compliance Status Yellow
  - Compliance Status Red
---

# Timesheet Compliance Indicator

Automatically calculated indicator that compares the collaborator's actual compliance against the hotel's contractual parameters, evaluated by week.

> [!info]
> This indicator takes as input the parameters of the [[Core/Modules/Contrato|Contract]] and the data from the [[Timesheet]]. See also: [[Collaborator Status Light|Collaborator Status Light]].

## Navigation structure

- **Year → Weeks** (numbered according to the calendar and the hotel's start/end of week)
- When selecting a week, the system automatically shows the **start and end date** (e.g. week 37 = Wed Sep 9 2026 → Tue Sep 15 2026)
- An internal matrix determines the range of available days from year + week + the hotel's start/end of week

## States

| Color  | State      | Description                                                                            |
| ------ | ---------- | -------------------------------------------------------------------------------------- |
| Green  | Compliance | Everything within contractual terms                                                    |
| Yellow | Alert      | Moderate deviation (e.g. 6/5 days worked, 43/40 hrs, 1/2 rest days)                     |
| Red    | Anomaly    | Situation that should not occur (e.g. punch on a day prior to the collaborator's start) |
| Gray   | No data    | Days prior to the collaborator's start in that week (there cannot be a punch)           |

## Contractual vs. actual comparison

The system automatically compares the following indicators by week:

| Indicator                  | Example |
| -------------------------- | ------- |
| Days worked / required     | 5/5     |
| Rest days / required       | 2/2     |
| Hours worked / required    | 40/40   |

Detected differences:
- Excess hours
- Missing hours
- Extra days worked
- Rest days not taken

## Mid-week onboarding case

If the collaborator starts mid-week, the system **automatically prorates** the remaining days of the weekly cycle.

- **Example:** the hotel requests a collaborator on Wednesday to start on Thursday → 6 days remain in that week → the system calculates **4 work + 2 rest**
- The days prior to the start are marked in **Gray** (no punch or activity is expected)
- If a punch exists on a day prior to the start → **Red** (anomaly)

> [!important] There cannot be a punch record on a day where the collaborator was not yet registered at the hotel.

## Key rules

- **Automatic calculation by the system**
- **Input:** parameters of the [[Core/Modules/Contrato|Contract]] + data from the [[Timesheet]]
- **No human intervention**: the system evaluates at the close of each week
- **Weekly evaluation** (current version)

## Related

- [[Timesheet]]
- [[Core/Modules/Contrato|Contract]]
- [[Core/Modules/Schedule|Schedule]]
- [[Collaborator Status Light|Collaborator Status Light]]
