---
tags:
  - module/core
aliases:
  - Work Accident Flow
---

# Work Accident Flow

Lifecycle of a [[Core/Módulos/Accidente Laboral/Accidente Laboral|Work Accident]]: from when the incident is reported until the [[Inspector|zone Inspector]] closes the card with complete information. The flow has two origin scenarios depending on who detects the accident first.

## Actors

- **Associate** — the injured party. Only originates the report (Scenario A); subsequent documentation falls on operational roles.
- **SUP — [[Hotel/Supervisor|Supervisor]]** — captures on-site information. Originates the report in Scenario B.
- **Inspector — [[Inspector|zone Inspector]]** — supplements with medical follow-up. Final person responsible for closing the card.

---

## Scenario A — The Associate Reports

Occurs when the injured associate is the one who first detects and reports the incident.

### 1. Initial Report

1. The **Associate** reports the accident from the app.
2. A [[Core/Módulos/Accidente Laboral/Accidente Laboral|Work Accident]] card is generated with an automatic report number.
3. The **Associate** transitions to **Gray — Injured** in the [[Semáforo del Colaborador]].
4. The notification reaches the SUP and the assigned zone Inspector **simultaneously**.

### 2. On-Site Capture (SUP)

5. The **SUP** physically goes to the incident location.
6. Captures the on-site information on the card:
   - Exact location within the property.
   - Circumstances of the accident.
   - Witnesses.
   - Immediate care provided.

### 3. Medical Follow-Up (Inspector)

7. The **Inspector** supplements the card with follow-up information:
   - Transfer to medical facility (if applicable, which one).
   - Diagnosis received.
   - Disability days.
   - Medical observations.

### 4. Closure

8. The **Inspector** closes the card once the information is complete.
9. Upon receiving medical clearance, the associate transitions from `Gray → Dark Green` in the [[Semáforo del Colaborador]].

---

## Scenario B — The SUP Reports

Occurs when the [[Hotel/Supervisor|SUP]] detects the incident first (the associate cannot self-report or the SUP sees it first).

### 1. Initial Report with On-Site Information

1. The **SUP** detects the incident and creates the card from the app.
2. A [[Core/Módulos/Accidente Laboral/Accidente Laboral|Work Accident]] card is generated with an automatic report number.
3. The **Associate** transitions to **Gray — Injured** in the [[Semáforo del Colaborador]].
4. The **SUP** directly captures the on-site information:
   - Exact location within the property.
   - Circumstances of the accident.
   - Witnesses.
   - Immediate care provided.
5. The notification reaches the assigned zone **Inspector**.

### 2. Medical Follow-Up (Inspector)

6. The **Inspector** supplements the card with follow-up information:
   - Transfer to medical facility (if applicable, which one).
   - Diagnosis received.
   - Disability days.
   - Medical observations.

### 3. Closure

7. The **Inspector** closes the card once the information is complete.
8. Upon receiving medical clearance, the associate transitions from `Gray → Dark Green` in the [[Semáforo del Colaborador]].

---

## Protection Rule

While the associate is in **Gray — Injured** status, absences **do not count** toward the 3 absences rule → [[Core/Módulos/Blacklist|Blacklist]] of the [[Semáforo del Colaborador]]. The associate is out of active operations for medical reasons.

---

## Related

- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Work Accident]]
- [[Semáforo del Colaborador]]
- [[Hotel/Supervisor|Supervisor]]
- [[Inspector]]
- [[Colaborador]]
- [[Hotel/Hotel|Hotel]]
- [[Core/Módulos/Blacklist|Blacklist]]
