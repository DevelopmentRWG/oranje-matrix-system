---
tags:
  - module/core
aliases:
  - Work Accident
  - Accident Report
  - Accident Card
---

# Work Accident

Entity that records an incident where an [[Associate]] suffers an injury or accident while assigned to a [[Hotel/Hotel|Hotel]]. The card originates from the app by the associate themselves or by the [[Hotel/Supervisor|Supervisor]] (SUP), and is completed between the SUP and the [[Inspector|zone Inspector]].

> [!important] Responsible for closure
> The [[Inspector]] is always the final person responsible for closing the card, once the on-site and medical follow-up information is complete.

## Card Data

### Header

| Field | Description |
|---|---|
| Report number | Automatic (same pattern as [[Requisition]]: date/time + homoclave) |
| Hotel | [[Hotel/Hotel\|Hotel]] where the incident occurred |
| Injured associate | [[Associate]] affected |
| Reported by | Who originates the report: the Associate or the SUP |
| Incident date and time | When the accident occurred |
| Status | Current card status |

### On-Site Information

Captured by the [[Hotel/Supervisor|SUP]], who physically goes to the incident location:

| Field | Description |
|---|---|
| Exact location | Place within the property where it occurred |
| Circumstances | Description of how the accident happened |
| Witnesses | People present at the time of the incident |
| Immediate care | First aid or care provided on-site |

### Follow-Up Information

Captured by the [[Inspector|zone Inspector]]:

| Field | Description |
|---|---|
| Transfer to medical facility | Whether they were transferred and to which facility |
| Diagnosis | Medical diagnosis received |
| Disability days | Days of medical disability granted |
| Medical observations | Additional notes from medical follow-up |

## Effect on the Associate Status Indicator

When a work accident report is generated, the [[Associate]] transitions to **Gray — Injured** in the [[Associate Status Indicator]]. This status protects them from the 3 absences rule → [[Blacklist]] while their disability lasts. Upon receiving medical clearance and closing the card, they transition to `Dark Green` (Available).

## Journal

Each status change on the card generates a journal entry with: Report number, Hotel, Associate, Reported by, Status, Note, Date and time of status.

## Related

- [[Core/Modules/Work Accident/Work Accident Flow|Work Accident Flow]]
- [[Associate Status Indicator]]
- [[Hotel/Supervisor|Supervisor]]
- [[Inspector]]
- [[Associate]]
- [[Hotel/Hotel|Hotel]]
- [[Core/Modules/Blacklist|Blacklist]]
