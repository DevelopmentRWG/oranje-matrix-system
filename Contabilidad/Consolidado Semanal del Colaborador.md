---
tags:
  - modulo/contabilidad
aliases:
  - Consolidado Semanal del Colaborador
  - Consolidado Semanal
---

# Consolidado Semanal del Colaborador

Resumen semanal que agrupa todos los [[Timesheet|Timesheets]] de un colaborador en los hoteles donde trabajó durante la semana, aplicando el [[Core/Módulos/Contrato|pay rate]] de cada hotel para calcular el monto total a pagar.

## Origen

- El sistema genera automáticamente el Consolidado Semanal al finalizar la semana del hotel (según la configuración de inicio/fin de semana del [[Core/Módulos/Contrato|Contrato]]), a partir de los [[Timesheet|Timesheets]] de esa semana
- Si el colaborador trabajó en un solo hotel, el consolidado contiene un único Timesheet
- Si trabajó en múltiples hoteles (vía asignación temporal [[Semáforo del Colaborador|Café]]), el consolidado agrupa los Timesheets de cada hotel

## Estructura

| Campo              | Descripción                                                                    |
| ------------------ | ------------------------------------------------------------------------------ |
| Colaborador        | Nombre y datos del colaborador                                                 |
| Semana             | Número de semana y rango de fechas                                             |
| Detalle por hotel  | Hotel, horas netas, pay rate del [[Core/Módulos/Contrato\|Contrato]], subtotal |
| Overtime por hotel | Horas extra calculadas según la política del contrato de cada hotel            |
| Total a pagar      | Suma de subtotales de todos los hoteles                                        |

## Cálculo

- **Por cada hotel donde trabajó:**
  - Horas netas × pay rate del contrato de ese hotel = subtotal regular
  - Horas de overtime × tasa de overtime del contrato de ese hotel = subtotal overtime
- **Umbral de overtime:** se calcula por hotel a partir de las **40 horas brutas semanales** (8 hrs × 5 días). Las horas que excedan ese umbral en un hotel se consideran overtime de ese hotel
- **Total a pagar** = Σ (subtotal regular + subtotal overtime) de todos los hoteles
- El overtime se calcula **por hotel**, no de forma global entre hoteles

> [!info] **Festivos** — El [[Core/Módulos/Contrato|Contrato]] define el manejo y recargos por días festivos, pero la regla de cálculo de recargos por festivo aún no está definida. Al definirse, se integrará en esta sección.

## Periodo

- El Consolidado Semanal se genera al cierre de cada semana
- El periodo de pago es **semanal**, alineado al ciclo del [[Timesheet]]
- Oranje paga al colaborador; el hotel paga a Oranje según el bill rate de su [[Core/Módulos/Contrato|Contrato]]

## Visibilidad

> [!important] El Consolidado Semanal es de uso exclusivo del departamento de **Contabilidad** de Oranje. El hotel y el colaborador no tienen acceso a este documento.

## Validación

- El sistema genera el Consolidado automáticamente al finalizar cada semana
- **Contabilidad revisa y aprueba** el Consolidado antes de ejecutar el pago al colaborador
- El pago no se ejecuta sin la validación de Contabilidad

## Relacionado

- [[Timesheet]]
- [[Core/Módulos/Contrato|Contrato]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Semáforo del Colaborador]]
