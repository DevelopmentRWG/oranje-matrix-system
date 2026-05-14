---
tags:
  - modulo/contabilidad
aliases:
  - Facturación al Hotel
  - Factura al Hotel
  - Invoice
---

# Facturación al Hotel

Documento fiscal generado automáticamente por el sistema al cierre del periodo semanal, que detalla el cobro a cada hotel por los servicios de personal proporcionados por Oranje.

## Generación

- El sistema genera la Factura automáticamente al finalizar la semana (paso 4 del [[Contabilidad/Flujo de Nómina|Flujo de Nómina]])
- Se genera una factura **por hotel por semana**
- El [[Manager de Contabilidad]] aprueba la factura antes de enviarla al hotel

## Cálculo

- **Horas regulares** × bill rate del [[Core/Módulos/Contrato|Contrato]]
- **Overtime autorizado** × tasa de overtime del Contrato
- **Acreditaciones** (si aplican): monto de [[Deducciones#Comida|deducción de comida]] del colaborador se acredita al hotel

> [!important] La Factura al Hotel usa exclusivamente el **bill rate** del Contrato. El rate interno (lo que Oranje realmente paga al colaborador) nunca se refleja en la Factura.

## Reglas especiales

### Factura partida por cruce de mes

- Cuando una semana abarca dos meses calendario, el sistema genera **dos facturas separadas**: una por los días del mes que termina y otra por los días del mes nuevo
- El [[Core/Módulos/Contrato|Contrato]] indica si el hotel requiere este comportamiento (campo: "Factura partida por mes: sí/no")

### Overtime autorizado

- Solo se factura al hotel el overtime que el hotel **autorizó**
- Si el colaborador trabajó horas extra no autorizadas, esas horas no se incluyen en la Factura al hotel (pero sí pueden pagarse al colaborador según decisión de Oranje)

### Folio

- El folio de la factura es generado por el sistema Oranje
- Es independiente de cualquier referencia externa

## Estructura

| Campo | Descripción |
| ----- | ----------- |
| Hotel | Nombre y datos del hotel |
| Periodo | Rango de fechas de la semana (o fracción si hay partición por mes) |
| Detalle por colaborador | Nombre, posición, horas regulares, horas OT autorizadas, rate, subtotal |
| Acreditaciones | Montos a favor del hotel (ej. deducción de comida) |
| Total a cobrar | Suma de subtotales menos acreditaciones |
| Folio | Identificador único generado por Oranje |

## Relacionado

- [[Contabilidad/Flujo de Nómina|Flujo de Nómina]]
- [[Consolidado Semanal del Colaborador]]
- [[Manager de Contabilidad]]
- [[Contadora]]
- [[Deducciones]]
- [[Core/Módulos/Contrato|Contrato]]
