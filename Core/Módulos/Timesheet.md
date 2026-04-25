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

## Deducción de Lunch

Después de 6 horas de trabajo, el sistema aplica una deducción de lunch al cómputo de horas del colaborador.

### Regla de deducción

| Escenario               | Deducción aplicada       |
| ------------------------ | ------------------------ |
| Lunch < 30 min           | 30 min (mínimo)          |
| Lunch ≥ 30 min           | Tiempo real tomado        |
| Sin ponche de Lunch      | 30 min (auto-deducción)  |

> [!info] La regla aplica a **todos** los colaboradores sin excepción. Ver [[Reglas de Negocio#Deducción de Lunch]] para la definición formal.

### Cálculo de horas pagables

- **Horas brutas** = Salida − Entrada
- **Horas netas** = Horas brutas − Deducción de Lunch
- Solo se aplica la deducción cuando las horas brutas superan 6 horas

> [!note] El mecanismo actual registra un único ponche de **Lunch**. Para calcular la duración real del lunch, el sistema necesita capturar inicio y fin del periodo (dos ponches o lógica automática). Consideración pendiente para desarrollo.

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
