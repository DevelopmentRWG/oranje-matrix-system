---
tags:
  - modulo/contabilidad
aliases:
  - Vacaciones
  - Cálculo de Vacaciones
---

# Vacaciones

Cálculo automatizado del pago de vacaciones de un colaborador, basado en el promedio de horas laboradas en las últimas 52 semanas.

## Fórmula

**Promedio de horas = Σ horas netas pagadas (últimas 52 semanas) ÷ 52**

- El sistema toma como fuente los [[Consolidado Semanal del Colaborador|Consolidados Semanales]] históricos del colaborador
- Si el colaborador tiene menos de 52 semanas de antigüedad, se promedia sobre las semanas disponibles

## Complejidad por múltiples rates

Cuando el colaborador trabajó con distintos rates durante el periodo (distintos hoteles o distintas posiciones), el sistema debe:

1. **Separar** las semanas/horas por rate
2. **Calcular** el promedio por cada rate independientemente
3. **Presentar** el desglose:
   - Promedio por hotel
   - Promedio por posición
   - Promedio por rate

> [!example] **Ejemplo**
> Colaborador trabajó 30 semanas en Hotel A (Housekeeper, $14/hr) y 22 semanas en Hotel B (Breakfast, $13/hr):
> - Promedio Hotel A: Σ horas Hotel A ÷ 30
> - Promedio Hotel B: Σ horas Hotel B ÷ 22

## Funcionalidad en el sistema

- La [[Contadora]] selecciona el colaborador y el periodo
- El sistema calcula automáticamente sin intervención manual
- Presenta el resultado con desglose por rate/hotel/posición
- Permite ajustar el rango de semanas si se requiere un cálculo parcial

## Relacionado

- [[Consolidado Semanal del Colaborador]]
- [[Manager de Contabilidad]]
- [[Contadora]]
- [[Core/Módulos/Contrato|Contrato]]
- [[Contabilidad/Flujo de Nómina|Flujo de Nómina]]
