---
tags:
  - arquitectura
  - rol/colaborador
  - caso-de-uso
aliases:
  - CU RF-C-07
---

# 🪪 ID: RF-C-07
🏷️ **Nombre:** Consultar Mi Timesheet

**Historia:**
El Colaborador quiere revisar sus horas registradas durante la semana. Desde la app accede a "Mi Timesheet" y ve la tabla semanal con los 6 ponches posibles por jornada, las horas brutas, la deducción de lunch aplicada y las horas netas por día. Puede navegar entre la semana en curso y semanas anteriores. La vista es de **solo lectura**; el Colaborador no puede corregir ponches (exclusivo del [[Hotel/Manager de Área|Manager de Área]]). Solo se muestran SUS propios registros.

**Criterios de aceptación:**
Vista solo lectura (RR-C-01). Solo muestra el Timesheet del propio colaborador. Información visible por jornada: Entrada, Salida Lunch, Entrada Lunch, Salida Break, Entrada Break, Salida; horas brutas, deducción de lunch, horas netas. El colaborador puede navegar entre la semana en curso y semanas anteriores. No tiene acceso al Indicador de Lunch Extendido (exclusivo de Inspector, Coordinador y Manager de Reclutamiento). No puede corregir ponches; si detecta un error, debe comunicarse con su supervisor. Si no hay ponches en la semana seleccionada, el sistema muestra estado vacío.

**Documentación:**
- PRD: PRD-COLAB-01
- Flow: [[Timesheet]] — Vista del Colaborador
- Prototipo: (link de Figma)

**Flujo:**
`App → Sección Mi Timesheet` → MANUAL → `Selecciona semana (en curso / semanas anteriores)` → AUTOMATICO → `Sistema carga el Timesheet del colaborador para la semana seleccionada` → `Muestra tabla: ponches por jornada (hasta 6) · horas brutas · deducción de lunch · horas netas` / Si sin registros → `Muestra estado vacío: "No hay registros de asistencia para esta semana"`
