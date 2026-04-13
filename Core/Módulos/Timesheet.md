---
tags:
  - modulo/core
aliases:
  - Timesheet
---

# Timesheet

Registro de tiempo trabajado por un colaborador en un hotel. Se crea a partir del [[Core/Módulos/Schedule|Schedule]] y se alimenta con los ponchados del colaborador durante la semana.

## Origen

- Cada colaborador inscrito en el [[Core/Módulos/Schedule|Schedule]] del hotel tiene su propio timesheet.
- El schedule es el que abre la puerta a la creación del timesheet.

## Ponchado

El colaborador poncha vía **QR** que genera el [[Hotel/Manager del Hotel|Manager del Hotel]]. Los ponches registrados son:

- **Entrada**
- **Lunch**
- **Salida**

Esto contabiliza el tiempo trabajado del colaborador.

## Uso por el hotel

En otra parte del panel, el hotel puede ver cuánto va a tener que pagar al finalizar la semana por todas las horas trabajadas registradas en los timesheets.

## Relacionado

- [[Core/Módulos/Schedule|Schedule]]
- [[Hotel/Manager del Hotel|Manager del Hotel]]
- [[Reclutadora]]
