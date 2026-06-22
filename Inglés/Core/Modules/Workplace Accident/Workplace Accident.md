---
tags:
  - modulo/core
aliases:
  - Workplace Accident
  - Accident Report
  - Accident Card
---

# Workplace Accident

Entity that records an incident where a [[Collaborator|Collaborator]] suffers an injury or accident while assigned to a [[Hotel/Hotel|Hotel]]. The card originates from the app by the collaborator themselves or by the [[Hotel/Supervisor|Supervisor]] (SUP), and is completed between the SUP and the [[Inspector|Zone Inspector]].

> [!important] Responsible for closure
> The [[Inspector]] is always the final party responsible for closing the card, once the on-site information and medical follow-up are complete.

## Card data

### Header

| Field | Description |
|---|---|
| Report number | Automatic (same pattern as [[Requisition|Requisition]]: date/time + check digit) |
| Hotel | [[Hotel/Hotel\|Hotel]] where the incident occurred |
| Injured collaborator | Affected [[Collaborator|Collaborator]] |
| Reported by | Who originates the report: the Collaborator or the SUP |
| Date and time of the incident | Moment when the accident occurred |
| Status | Current status of the card |

### On-site information

Captured by the [[Hotel/Supervisor|SUP]], who physically goes to the location of the incident:

| Field | Description |
|---|---|
| Exact location | Place within the property where it occurred |
| Circumstances | Description of how the accident happened |
| Witnesses | People present at the time of the incident |
| Immediate care | First aid or care provided on site |

### Follow-up information

Captured by the [[Inspector|Zone Inspector]]:

| Field | Description |
|---|---|
| Transfer to medical center | Whether they were transferred and to which center |
| Diagnosis | Medical diagnosis received |
| Days of disability | Days of medical disability granted |
| Medical observations | Additional notes from the medical follow-up |

## Effect on the Collaborator Status Light

When a workplace accident report is generated, the [[Collaborator|Collaborator]] transitions to **Gray — Injured** in the [[Collaborator Status Light|Collaborator Status Light]]. This state protects them from the rule of 3 no-shows → [[Blacklist]] for the duration of their disability. Upon receiving medical clearance and closing the card, they transition to `Strong Green` (Available).

## Journal

Each status change in the card generates a record in the journal with: Report number, Hotel, Collaborator, Reported by, Status, Note, Date and time of the status.

## Related

- [[Core/Modules/Workplace Accident/Workplace Accident Flow|Workplace Accident Flow]]
- [[Collaborator Status Light|Collaborator Status Light]]
- [[Hotel/Supervisor|Supervisor]]
- [[Inspector]]
- [[Collaborator|Collaborator]]
- [[Hotel/Hotel|Hotel]]
- [[Core/Modules/Blacklist|Blacklist]]
