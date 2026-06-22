---
tags:
  - arquitectura
  - rol/manager-de-area
  - caso-de-uso
aliases:
  - CU RF-H-11
---

# 🪪 ID: RF-H-11
🏷️ **Nombre:** Generar / Renovar QR del Timesheet

**Historia:**
Para que los colaboradores asignados puedan ponchar (entrada, salida, lunch, breaks) en el Timesheet, necesitan escanear un código **QR generado por el Manager de Área**. Esta acción es **exclusiva del Manager de Área** (regla RR-H-09). El QR se renueva periódicamente por seguridad o cuando el Manager lo decide.

**Criterios de aceptación:**
Solo el Manager de Área puede generar / renovar el QR (RR-H-09). El QR es válido inmediatamente tras la generación. El sistema notifica a los colaboradores asignados que hay un nuevo QR disponible. Queda en log con fecha de generación y autor. La generación de un nuevo QR invalida el QR anterior.

**Documentación:**
- PRD: PRD-HOTEL-03 Manager de Área
- Flow: Generación de QR del Timesheet
- Prototipo: (link de Figma)

**Flujo:**
`Sidebar → Timesheet` → MANUAL → `Click "Generar / Renovar QR"` → `Confirmar` → AUTOMATICO → `Sistema genera nuevo QR + Invalida QR anterior + Muestra QR en pantalla y como descarga PDF + Notifica a colaboradores asignados al depto + Registra en log con autor y fecha`
