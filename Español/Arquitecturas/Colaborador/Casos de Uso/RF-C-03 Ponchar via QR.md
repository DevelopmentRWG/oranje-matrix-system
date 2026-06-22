---
tags:
  - arquitectura
  - rol/colaborador
  - caso-de-uso
aliases:
  - CU RF-C-03
---

# 🪪 ID: RF-C-03
🏷️ **Nombre:** Ponchar vía QR

**Historia:**
El Colaborador llega al hotel y necesita registrar su asistencia escaneando el código QR generado por el [[Hotel/Manager General|Manager General]] o el [[Hotel/Manager de Área|Manager de Área]] del hotel. Cada jornada tiene hasta 6 ponches posibles: Entrada, Salida Lunch, Entrada Lunch, Salida Break, Entrada Break y Salida. El sistema determina automáticamente qué tipo de ponche corresponde según el orden de los ponches ya registrados en la jornada. Para ponchar, el colaborador debe tener un [[Timesheet]] activo, lo cual requiere estar inscrito en el [[Core/Módulos/Schedule|Schedule]] con una asignación activa (RR-C-03). Al cerrar la jornada (ponche de Salida), el sistema calcula horas brutas, aplica la deducción de lunch según las reglas, y actualiza el Timesheet con las horas netas.

**Criterios de aceptación:**
El colaborador debe tener Timesheet activo (RR-C-03); sin Timesheet activo, el sistema bloquea y muestra: *"No tienes un turno activo. Comunícate con tu supervisor"*. El QR debe ser válido y no expirado; QR inválido o expirado bloquea la acción. El sistema identifica el tipo de ponche según el orden de los registros previos de la jornada; no se puede saltar el orden. No se permiten ponches duplicados del mismo tipo en la misma jornada. Si el almacenamiento offline está activo (RNF-C-02), el registro se encola y se sincroniza al recuperar conexión. Deducción de lunch: lunch < 30 min → se deducen 30 min (mínimo obligatorio); lunch ≥ 30 min → se deduce el tiempo real; sin ponche de lunch → auto-deducción de 30 min al cerrar la jornada. Horas netas = horas brutas − deducción de lunch − breaks reales.

**Documentación:**
- PRD: PRD-COLAB-01
- Flow: [[Timesheet]] — Ponchado QR
- Prototipo: (link de Figma)

**Flujo:**
`App → Sección Asistencia → Escanear QR` → MANUAL → `Apunta cámara al QR del hotel` → AUTOMATICO → Si QR válido y Timesheet activo → `Identifica tipo de ponche por orden` → `Registra ponche con hora y fecha` → `Muestra confirmación: "Entrada registrada a las HH:MM" (o el tipo de ponche correspondiente)` → `Timesheet de la jornada actualizado` / Si Salida (fin de jornada) → `Calcula horas brutas (Salida − Entrada)` → `Aplica deducción de lunch` → `Calcula horas netas` → `Confirma: "Salida registrada. Horas netas de hoy: X.X hrs"` / Si sin Timesheet activo → `Bloquea · Muestra: "No tienes un turno activo. Comunícate con tu supervisor"` / Si QR inválido → `Bloquea · Muestra: "Código QR no válido. Solicita un QR actualizado a tu supervisor"` / Si sin conexión → `Encola registro localmente · Muestra: "Sin conexión. Tu ponche se registrará cuando recuperes señal"`
