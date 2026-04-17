---
tags:
  - modulo/core
aliases:
  - Schedule
---

# Schedule

Tablero de planeación semanal del hotel. Es el **eje central de la operación**: en él convergen la demanda de personal ([[Requisición]]), la cobertura (asignación de colaboradores desde la [[Pool de Colaboradores]]) y el registro de tiempo trabajado ([[Timesheet]]). Cada semana del hotel tiene su propio schedule.

## Configuración inicial

- El hotel define **inicio y fin de su semana** en el contrato.
- Oranje ofrece un **formato de planeación semanal** basado en esa configuración.

## Qué contiene el schedule

### Requisición (qué necesita el hotel)

- Al crearse una [[Requisición]] con fecha de inicio dentro de la semana, sus posiciones quedan reflejadas en el schedule de esa semana.
- El schedule muestra las posiciones solicitadas: puesto, cantidad de personas, horario, fechas e idioma.

### Asignaciones (quién cubre las posiciones)

- La [[Reclutadora]] consulta el schedule del hotel para ver el panorama completo: qué posiciones se pidieron y cuáles ya están cubiertas.
- Al asignar un colaborador desde la [[Pool de Colaboradores]], este queda registrado en el schedule del hotel.

### Timesheet (registro real de horas)

- Cada colaborador inscrito en el schedule tiene su propio [[Timesheet]].
- El schedule es la base sobre la que se genera el timesheet y se habilita el ponchado (entrada, lunch, salida).

## Quién lo gestiona

- **[[Hotel/Manager del Hotel|Manager del Hotel]]** — Administra el schedule semanal: distribuye y planea a su personal.
- **[[Reclutadora]]** — Consulta el schedule para ver la demanda y registra colaboradores al asignarlos.

## Qué habilita

- Vista unificada de la semana operativa del hotel (demanda + cobertura + registro).
- Creación del [[Timesheet]] por colaborador.
- Visibilidad para el hotel de lo que pidió vs. lo que tiene cubierto.

## Relacionado

- [[Requisición]]
- [[Timesheet]]
- [[Reclutadora]]
- [[Pool de Colaboradores]]
- [[Hotel/Manager del Hotel|Manager del Hotel]]
- [[Flujo de Requisición]]
