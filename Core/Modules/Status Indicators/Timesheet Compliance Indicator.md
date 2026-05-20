---
tags:
  - module/core
aliases:
  - Timesheet Compliance Indicator
  - Compliance Indicator
  - Compliance Status Green
  - Compliance Status Yellow
  - Compliance Status Red
---

# Timesheet Compliance Indicator

Automatically calculated indicator that compares the associate's actual compliance against the hotel's contractual parameters, evaluated on a weekly basis.

> [!info]
> This indicator takes as input the parameters from the [[Core/Modules/Contract|Contract]] and the data from the [[Timesheet]]. See also: [[Associate Status Indicator]].

## Navigation structure

- **Year → Weeks** (numbered according to calendar and hotel's week start/end)
- When selecting a week, the system automatically displays **start and end date** (e.g. week 37 = Wed Sep 9 2026 → Tue Sep 15 2026)
- An internal matrix determines the range of available days based on year + week + hotel's week start/end

## States

| Color  | State       | Description                                                                                  |
| ------ | ----------- | -------------------------------------------------------------------------------------------- |
| Green  | Compliance  | Everything within contractual parameters                                                     |
| Yellow | Alert       | Moderate deviation (e.g. 6/5 days worked, 43/40 hrs, 1/2 rest days)                         |
| Red    | Anomaly     | Situation that should not occur (e.g. punch on a day prior to the associate's onboarding)    |
| Gray   | No data     | Days prior to the associate's onboarding in that week (no punch expected)                    |

## Contractual vs. actual comparison

The system automatically compares the following indicators per week:

| Indicator                           | Example |
| ----------------------------------- | ------- |
| Days worked / required              | 5/5     |
| Rest days / required                | 2/2     |
| Hours worked / required             | 40/40   |

Detected differences:
- Extra hours
- Missing hours
- Extra days worked
- Rest days not taken

## Mid-week onboarding case

If the associate starts mid-week, the system **automatically prorates** the remaining days of the weekly cycle.

- **Example:** the hotel requests an associate on Wednesday to start Thursday → 6 days remain in that week → the system calculates **4 working days + 2 rest days**
- Days prior to onboarding are marked in **Gray** (no punch or activity expected)
- If a punch exists on a day prior to onboarding → **Red** (anomaly)

> [!important] There cannot be a punch record on a day when the associate had not yet been onboarded at the hotel.

## Business Rules

- **Automatic calculation by system**
- **Input:** parameters from the [[Core/Modules/Contract|Contract]] + [[Timesheet]] data
- **No human intervention**: the system evaluates at the close of each week
- **Weekly evaluation** (current version)

## Related

- [[Timesheet]]
- [[Core/Modules/Contract|Contract]]
- [[Core/Modules/Schedule|Schedule]]
- [[Associate Status Indicator]]
