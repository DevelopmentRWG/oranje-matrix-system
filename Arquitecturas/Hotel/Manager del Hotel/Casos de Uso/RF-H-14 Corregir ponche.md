---
tags:
  - arquitectura
  - rol/manager-del-hotel
  - caso-de-uso
aliases:
  - CU RF-H-14
---

# 🪪 ID: RF-H-14
🏷️ **Nombre:** Corregir ponche del Timesheet

**Historia:**
Cuando un colaborador olvida ponchar, poncha mal o tiene un problema técnico con el QR, el Manager del Hotel corrige manualmente el ponche. Es una acción excepcional con **justificación obligatoria** que queda en log auditable. Solo el Manager del Hotel puede hacerlo (no el Supervisor, no el Manager General).

**Criterios de aceptación:**
La justificación es obligatoria (mín. 20 caracteres). El cambio queda en log auditable con autor, fecha, motivo, valor anterior y valor nuevo. Notifica al colaborador del cambio. Si la hora corregida está fuera del rango de la jornada del colaborador, el sistema muestra advertencia y solicita confirmación adicional. Recalcula horas brutas, deducción de Lunch y horas netas.

**Documentación:**
- PRD: PRD-HOTEL-03 Manager del Hotel
- Flow: Corrección de ponche
- Prototipo: (link de Figma)

**Flujo:**
`Módulo Timesheet` → MANUAL → `Click en jornada con problema` → `Identifica ponche a corregir` → `Click "Corregir ponche"` → `Selecciona tipo (Entrada / Salida Lunch / Entrada Lunch / Salida Break / Entrada Break / Salida)` → `Ingresa hora corregida (HH:MM)` → `Justificación obligatoria` → `Adjunta evidencia opcional` → `Confirmar` → AUTOMATICO → Si hora válida → `Aplica cambio + Recalcula horas brutas, lunch, netas + Log auditable + Notifica al colaborador` / Si hora fuera de rango → `Advertencia + confirmación adicional`
