---
tags:
  - modulo/contabilidad
aliases:
  - Deducciones
  - Deducción
---

# Deducciones

Descuentos monetarios que el sistema aplica automáticamente al cheque del colaborador antes de liberar el pago. Cada deducción tiene un disparador específico y condiciones de activación.

## Tipos de deducción

### Uniforme

| Campo | Valor |
| ----- | ----- |
| Monto | $15 USD por uniforme |
| Disparador | El [[Inspección/Inspector\|Inspector]] registra entrega o pérdida de uniforme vía formulario |
| Aplicación | Se aplica automáticamente al siguiente [[Consolidado Semanal del Colaborador\|Consolidado Semanal]] |
| Acumulable | Sí — si el colaborador pierde el uniforme y recibe otro, se suma una nueva deducción |

### Comida

| Campo | Valor |
| ----- | ----- |
| Monto | $3 USD por día laborado |
| Disparador | Configuración del hotel en el [[Core/Módulos/Contrato\|Contrato]] (campo: "Deduce comida: sí/no") |
| Aplicación | Solo en días donde el colaborador tiene [[Timesheet]] registrado |
| Particularidad | Se descuenta al colaborador Y se acredita al hotel en su [[Facturación al Hotel\|Factura]] |

> [!note] Esta deducción es por configuración del hotel. No todos los hoteles la aplican.

### Retención 16%

| Campo | Valor |
| ----- | ----- |
| Monto | 16% del monto total del cheque |
| Disparador | Campo del [[Colaborador/Colaborador\|Colaborador]]: "Tiene SSN/TaxID: no" |
| Activación | Automática al registrar al colaborador sin documentos fiscales |
| Desactivación | [[Contabilista]] la desactiva manualmente cuando el colaborador entrega documentos |
| Reembolso | Al desactivar, el sistema permite generar el reembolso del monto acumulado retenido |

> [!important] La retención 16% es reembolsable. El sistema debe mantener un registro histórico del monto acumulado retenido para poder generar el reembolso cuando corresponda.

## Comportamiento en el sistema

- Las deducciones se aplican en el paso 2 del [[Contabilidad/Flujo de Nómina|Flujo de Nómina]] (cálculo del Pre-Payroll)
- Reducen el monto neto del cheque del colaborador
- [[Contabilista|Contabilidad]] verifica que las deducciones estén correctamente aplicadas en el paso 3 (validación)
- El sistema mantiene un historial de deducciones aplicadas por colaborador/semana

## Relacionado

- [[Consolidado Semanal del Colaborador]]
- [[Contabilidad/Flujo de Nómina|Flujo de Nómina]]
- [[Contabilista]]
- [[Facturación al Hotel]]
- [[Inspección/Inspector|Inspector]]
- [[Core/Módulos/Contrato|Contrato]]
- [[Colaborador/Colaborador|Colaborador]]
