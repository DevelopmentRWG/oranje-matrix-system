---
tags:
  - arquitectura
  - rol/colaborador
  - caso-de-uso
aliases:
  - CU RF-C-08
---

# 🪪 ID: RF-C-08
🏷️ **Nombre:** Consultar historial de pagos
**Alias del caso de uso:** Consultar Mi Pago semanal

**Historia:**
El Colaborador quiere consultar sus pagos ya recibidos. Desde la app accede a "Mi Pago" y ve el **historial de pagos ya liberados**: semana, hotel(es) en los que trabajó, horas netas, monto pagado y fecha de pago. La semana en curso aparece en la lista como "En cálculo", sin monto visible. El Colaborador **no puede ver el monto de su pago en curso o próximo**: el cálculo es exclusivo de Contabilidad y solo se revela al Colaborador una vez que el pago ha sido liberado. Esta vista es un concepto distinto y acotado, separado del [[Contabilidad/Consolidado Semanal del Colaborador|Consolidado Semanal del Colaborador]], que sigue siendo de uso exclusivo del departamento de Contabilidad (RR-C-05).

> [!info]
> El historial de pagos del colaborador y el [[Contabilidad/Consolidado Semanal del Colaborador|Consolidado Semanal del Colaborador]] son documentos distintos con audiencias distintas. El Consolidado Semanal incluye: pay rate, rate interno, deducciones individuales, facturación al hotel y datos de nómina completos — todo exclusivo de Contabilidad. El historial del colaborador muestra únicamente: semana, hotel(es), horas netas, monto pagado y fecha de pago — solo para pagos ya liberados.

**Criterios de aceptación (RR-C-05):**
Vista solo lectura. Solo muestra datos del propio colaborador. Información visible (solo para pagos ya liberados): semana y rango de fechas, hotel(es) en los que trabajó esa semana, horas netas por hotel, monto pagado y fecha de pago. La semana en curso se muestra en la lista con estado "En cálculo" y **sin monto**: el monto del pago en curso o próximo no es visible para el Colaborador hasta que Contabilidad lo libere. Información **nunca visible** para el colaborador: pay rate interno, rate contractual, deducciones individuales (uniforme, comida, retención), información de facturación al hotel, ni cualquier otro dato del Consolidado Semanal completo. El colaborador puede navegar entre semanas anteriores. Si no hay registros en la semana seleccionada → `Muestra estado vacío: "No hay registros de pago para esta semana"`.

**Documentación:**
- PRD: PRD-COLAB-01
- Flow: [[Contabilidad/Consolidado Semanal del Colaborador|Consolidado Semanal del Colaborador]] — Historial de pagos liberados
- Prototipo: (link de Figma)

**Flujo:**
`App → Sección Mi Pago` → AUTOMATICO → `Sistema carga historial de pagos liberados` → `Lista de entradas: semana · hotel(es) · horas · monto pagado · fecha de pago` → Semana en curso → `Muestra entrada con estado "En cálculo" · sin monto` / Semana sin registros → `Muestra estado vacío: "No hay registros de pago para esta semana"`
