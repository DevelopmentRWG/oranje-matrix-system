---
tags:
  - arquitectura
  - rol/colaborador
  - caso-de-uso
aliases:
  - CU RF-C-05
---

# 🪪 ID: RF-C-05
🏷️ **Nombre:** Reportar accidente laboral desde la app

**Historia:**
El Colaborador sufre un accidente mientras está asignado al hotel y reporta el incidente directamente desde la app (**Escenario A** del [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]]). Completa el formulario de reporte con la fecha, hora y descripción del accidente; puede adjuntar fotos y permite opcionalmente la captura de geolocalización. Al enviar, el sistema crea la tarjeta de [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]], transiciona el estado del colaborador a **Gris — Accidentado** y notifica simultáneamente al [[Hotel/Supervisor|Supervisor]] del hotel y al [[Inspector]] de zona. El colaborador queda protegido de la regla de 3 inasistencias → [[Core/Módulos/Blacklist|Blacklist]] mientras permanezca en Gris.

> [!info]
> Este caso de uso corresponde al **Escenario A** del [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]]: el colaborador detecta y reporta primero. El rol del colaborador en el flujo completo se limita a generar la señal inicial y describir brevemente el incidente. La información presencial detallada (ubicación exacta, circunstancias, testigos, atención inmediata) es capturada por el [[Hotel/Supervisor|Supervisor]] que acude físicamente. El [[Inspector]] completa el seguimiento médico y es el responsable final del cierre de la tarjeta.

**Criterios de aceptación:**
Fecha del accidente: obligatoria, no puede ser futura. Hora del accidente: obligatoria, formato HH:MM. Descripción: obligatoria, mínimo 50 caracteres. Evidencia fotográfica: opcional, JPG/PNG, máximo 10 MB por archivo; si excede el límite, el sistema rechaza el archivo y muestra mensaje. Geolocalización: opcional, capturada automáticamente desde el dispositivo si el colaborador otorga permiso. Al enviar correctamente: sistema crea tarjeta de accidente con número de reporte automático; estado del colaborador transita a Gris (cualquier estado activo → Gris); notificación simultánea al Supervisor del hotel y al Inspector de zona en menos de 1 minuto; protección contra regla de 3 inasistencias activada. Confirmación al colaborador: *"Tu reporte fue enviado. El Inspector de zona recibirá el caso"*.

**Documentación:**
- PRD: PRD-COLAB-01
- Flow: [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]] — Escenario A
- Prototipo: (link de Figma)

**Flujo:**
`App → Sección Reportar Accidente` → MANUAL → `Ingresa fecha del accidente` → `Ingresa hora del accidente` → `Describe el accidente (mín. 50 caracteres)` → `Adjunta foto/evidencia opcional (JPG/PNG, máx. 10 MB)` → `Permite geolocalización opcional` → `Enviar reporte` → AUTOMATICO → Si campos válidos → `Tarjeta de accidente creada con número automático · Estado del colaborador → Gris (Accidentado) · Notificación simultánea al Supervisor del hotel y al Inspector de zona (< 1 min) · Protección de regla de 3 inasistencias activada · Confirmación al colaborador: "Tu reporte fue enviado. El Inspector de zona recibirá el caso"` / Si descripción < 50 caracteres → `Bloquea · Muestra: "La descripción debe tener al menos 50 caracteres"` / Si fecha futura → `Bloquea · Muestra: "La fecha del accidente no puede ser futura"` / Si foto > 10 MB → `Rechaza archivo · Muestra: "Tamaño máximo de foto: 10 MB"`
