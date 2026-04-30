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
- Si el [[Core/Módulos/Schedule|Schedule]] cambia después de que el timesheet fue creado, el timesheet se actualiza automáticamente para reflejar los cambios.

## Ponchado

El colaborador poncha vía **QR** que genera el [[Hotel/Manager del Hotel|Manager del Hotel]]. Los ponches se registran por pares de entrada/salida para cada periodo:

- **Entrada** — inicio de jornada
- **Salida Lunch** — sale a comer
- **Entrada Lunch** — regresa de comer
- **Salida Break** — sale a descanso
- **Entrada Break** — regresa de descanso
- **Salida** — fin de jornada

Esto contabiliza el tiempo trabajado del colaborador.

## Uso por el hotel

En otra parte del panel, el hotel puede ver cuánto va a tener que pagar al finalizar la semana por todas las horas trabajadas registradas en los timesheets.

## Deducción de Lunch

El sistema aplica una deducción de lunch al cómputo de horas del colaborador en cada jornada.

### Regla de deducción

| Escenario               | Deducción aplicada       |
| ------------------------ | ------------------------ |
| Lunch < 30 min           | 30 min (mínimo)          |
| Lunch ≥ 30 min           | Tiempo real tomado       |
| Sin ponche de Lunch      | 30 min (auto-deducción)  |
| Break registrado         | Tiempo real del break    |

> [!info] La regla aplica a **todos** los colaboradores sin excepción. Ver [[Reglas de Negocio#Deducción de Lunch]] para la definición formal.

### Cálculo de horas pagables

- **Horas brutas** = Salida − Entrada
- **Horas netas** = Horas brutas − Lunch real − Breaks reales
- La deducción de lunch aplica en cada jornada sin excepción

### Deducción de Breaks

El sistema deduce el tiempo de breaks del cómputo de horas del colaborador en cada jornada.

- Los breaks se registran con el par **Salida Break / Entrada Break**
- La cantidad y duración de breaks la define cada hotel
- El tiempo deducido es el tiempo real registrado entre cada par de ponches de break

### Indicador de Lunch Extendido

El sistema marca automáticamente a los colaboradores cuyo lunch excede 30 minutos.

- **Quién lo ve:** [[Inspector]], [[Inspección/Coordinador|Coordinador]], [[Manager de Reclutamiento]]
- **Quién NO lo ve:** [[Hotel/Manager del Hotel|Manager del Hotel]], [[Hotel/Supervisor|Supervisor]]
- **Qué muestra:** colaborador, hotel, fecha, tiempo de lunch real
- **Cuándo se activa:** cuando el tiempo de lunch registra más de 30 minutos

> [!important] Este indicador es una herramienta de supervisión interna de Oranje. El hotel no tiene visibilidad sobre los tiempos de lunch individuales de los colaboradores.

## Relacionado

- [[Core/Módulos/Schedule|Schedule]]
- [[Hotel/Manager del Hotel|Manager del Hotel]]
- [[Reclutadora]]
- [[Reglas de Negocio]]
- [[Inspector]]
- [[Inspección/Coordinador|Coordinador]]
- [[Manager de Reclutamiento]]
