---
tags:
  - modulo/core
aliases:
  - Workplace Accident Flow
---

# Workplace Accident Flow

Life cycle of a [[Core/Modules/Workplace Accident/Workplace Accident|Workplace Accident]]: from when the incident is reported until the [[Inspector|Zone Inspector]] closes the card with the complete information. The flow has two origin scenarios depending on who detects the accident first.

## Actors

- **Collaborator** — the injured party. Only originates the report (scenario A); the subsequent filling falls to the operational roles.
- **SUP — [[Hotel/Supervisor|Supervisor]]** — captures the on-site information. Originates the report in scenario B.
- **Inspector — [[Inspector|Zone Inspector]]** — complements with medical follow-up. Final party responsible for closing the card.

---

## Scenario A — The collaborator reports

Occurs when the injured collaborator is the one who detects and reports the incident first.

### 1. Initial report

1. The **Collaborator** reports the accident from the app.
2. The [[Core/Modules/Workplace Accident/Workplace Accident|Workplace Accident]] card is generated with an automatic report number.
3. The **Collaborator** transitions to **Gray — Injured** in the [[Collaborator Status Light|Collaborator Status Light]].
4. The signal reaches the SUP and the assigned Zone Inspector **simultaneously**.

### 2. On-site capture (SUP)

5. The **SUP** physically goes to the location of the incident.
6. Captures the on-site information in the card:
   - Exact location within the property.
   - Circumstances of the accident.
   - Witnesses.
   - Immediate care provided.

### 3. Medical follow-up (Inspector)

7. The **Inspector** complements the card with the follow-up information:
   - Transfer to the medical center (if applicable, which one).
   - Diagnosis received.
   - Days of disability.
   - Medical observations.

### 4. Closure

8. The **Inspector** closes the card once the information is complete.
9. Upon receiving medical clearance, the collaborator transitions from `Gray → Strong Green` in the [[Collaborator Status Light|Collaborator Status Light]].

---

## Scenario B — The SUP reports

Occurs when the [[Hotel/Supervisor|SUP]] detects the incident first (the collaborator cannot report on their own or the SUP sees it first).

### 1. Initial report with on-site information

1. The **SUP** detects the incident and creates the card from the app.
2. The [[Core/Modules/Workplace Accident/Workplace Accident|Workplace Accident]] card is generated with an automatic report number.
3. The **Collaborator** transitions to **Gray — Injured** in the [[Collaborator Status Light|Collaborator Status Light]].
4. The **SUP** directly captures the on-site information:
   - Exact location within the property.
   - Circumstances of the accident.
   - Witnesses.
   - Immediate care provided.
5. The signal reaches the assigned Zone **Inspector**.

### 2. Medical follow-up (Inspector)

6. The **Inspector** complements the card with the follow-up information:
   - Transfer to the medical center (if applicable, which one).
   - Diagnosis received.
   - Days of disability.
   - Medical observations.

### 3. Closure

7. The **Inspector** closes the card once the information is complete.
8. Upon receiving medical clearance, the collaborator transitions from `Gray → Strong Green` in the [[Collaborator Status Light|Collaborator Status Light]].

---

## Protection rule

While the collaborator is in the **Gray — Injured** state, no-shows **do not count** toward the rule of 3 no-shows → [[Core/Modules/Blacklist|Blacklist]] of the [[Collaborator Status Light|Collaborator Status Light]]. The collaborator is out of active operation for medical reasons.

---

## Related

- [[Core/Modules/Workplace Accident/Workplace Accident|Workplace Accident]]
- [[Collaborator Status Light|Collaborator Status Light]]
- [[Hotel/Supervisor|Supervisor]]
- [[Inspector]]
- [[Collaborator|Collaborator]]
- [[Hotel/Hotel|Hotel]]
- [[Core/Modules/Blacklist|Blacklist]]
