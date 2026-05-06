---
tags:
  - modulo/contabilidad
aliases:
  - Flujo de Nómina
  - Proceso de Nómina
  - Pre-Payroll
---

# Flujo de Nómina

Proceso semanal semi-automatizado que transforma los [[Timesheet|Timesheets]] aprobados en pagos al colaborador y facturas al hotel. El sistema automatiza el cálculo; [[Contabilista|Contabilidad]] valida y autoriza.

## Pasos del flujo

### 1. Generación automática del Consolidado Semanal

- El sistema agrupa los [[Timesheet|Timesheets]] aprobados por colaborador/hotel/semana
- Aplica el pay rate de cada [[Core/Módulos/Contrato|Contrato]]
- Calcula overtime según las reglas del contrato de cada hotel
- Ver [[Consolidado Semanal del Colaborador]] para estructura y cálculo

> [!success] **Automatizado** — No requiere intervención humana.

### 2. Cálculo automático del Pre-Payroll

- El sistema genera el Pre-Payroll a partir del Consolidado:
  - Aplica el **rate interno** si existe (puede ser mayor al rate contractual)
  - Aplica las **[[Deducciones]]** activas del colaborador (uniforme, comida, retención 16%)
  - Aplica el **overtime autorizado** (solo las horas aprobadas por el hotel)
- El Pre-Payroll refleja el monto neto que recibirá cada colaborador

> [!success] **Automatizado** — No requiere intervención humana.

### 3. Validación humana

- [[Contabilista|Contabilidad]] revisa el Pre-Payroll generado
- Verifica por cada línea:
  - ID del colaborador correcto
  - Nombre/apellidos coinciden con el ID
  - Horas correctas según Timesheet aprobado
  - Rate correcto (interno o contractual según corresponda)
  - Descuentos aplicados correctamente
  - Posiciones correctas si tiene múltiples
  - Hotel correcto si trabaja en múltiples
- Aprueba, corrige o rechaza líneas individuales

> [!warning] **Semi-automatizado** — Requiere aprobación de Contabilidad.

### 4. Generación automática de la Factura al Hotel

- El sistema genera la [[Facturación al Hotel|Factura al Hotel]] usando el **bill rate** del [[Core/Módulos/Contrato|Contrato]] (nunca el rate interno)
- Aplica acreditaciones si corresponden (ej. deducción de comida)
- El overtime facturado es solo el **autorizado** por el hotel
- Si la semana cruza dos meses, genera dos facturas separadas

> [!success] **Automatizado** — No requiere intervención humana.

### 5. Exportación a sistema de pago externo

- El sistema genera el archivo/datos necesarios para el proveedor de cheques
- La integración con el proveedor externo es configurable

> [!success] **Automatizado** — No requiere intervención humana.

### 6. Conciliación

- El proveedor devuelve la confirmación de los cheques generados
- [[Contabilista|Contabilidad]] valida que lo devuelto coincida con lo enviado
- Identifica discrepancias y las resuelve antes de autorizar

> [!warning] **Semi-automatizado** — Requiere validación de Contabilidad.

### 7. Autorización final

- [[Contabilista|Contabilidad]] libera la nómina
- Los pagos se ejecutan
- El sistema registra la fecha y responsable de la autorización

> [!warning] **Semi-automatizado** — Requiere autorización de Contabilidad.

## Resumen de automatización

| Paso | Descripción | Automatización |
| ---- | ----------- | -------------- |
| 1 | Generación del Consolidado Semanal | Automático |
| 2 | Cálculo del Pre-Payroll | Automático |
| 3 | Validación del Pre-Payroll | Semi-automático (Contabilidad aprueba) |
| 4 | Generación de Factura al Hotel | Automático |
| 5 | Exportación a proveedor de cheques | Automático |
| 6 | Conciliación | Semi-automático (Contabilidad valida) |
| 7 | Autorización final | Semi-automático (Contabilidad libera) |

## Relacionado

- [[Consolidado Semanal del Colaborador]]
- [[Contabilista]]
- [[Deducciones]]
- [[Facturación al Hotel]]
- [[Vacaciones]]
- [[Core/Módulos/Contrato|Contrato]]
- [[Timesheet]]
