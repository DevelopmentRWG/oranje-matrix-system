---
tags:
  - arquitectura
  - rol/supervisor-hotel
  - caso-de-uso
aliases:
  - CU RF-H-21
---

# 🪪 ID: RF-H-21
🏷️ **Nombre:** Reportar accidente laboral — Escenario B

**Historia:**
**Escenario B:** el Supervisor detecta primero un accidente en la propiedad (antes de que el colaborador alcance a reportarlo desde su app, o cuando el colaborador no puede reportarlo). El Supervisor crea la tarjeta de accidente desde su app con todos los datos presenciales. La señal llega al [[Inspector]] de zona automáticamente para que inicie la investigación.

**Criterios de aceptación:**
El Supervisor debe identificar al colaborador afectado de la lista de asignados. La descripción de circunstancias debe tener al menos 50 caracteres. La atención inmediata es obligatoria. La fecha del accidente no puede ser futura. La tarjeta se crea con número auto (mismo formato que requisiciones — RR-H-04). Notifica al Inspector de zona en menos de 1 min. El colaborador pasa a estado **Gris** (RR-H-20).

**Documentación:**
- PRD: PRD-HOTEL-02 Supervisor
- Flow: Accidente Laboral — Escenario B
- Prototipo: (link de Figma)

**Flujo:**
`Sidebar → Accidentes Laborales (Supervisor detecta el accidente en la propiedad)` → MANUAL → `Abre app → Click "Reportar Accidente"` → `Selecciona Escenario B` → `Selecciona colaborador afectado de la lista de asignados` → `Llena fecha y hora del accidente (no futuras)` → `Ubicación exacta (mín. 10 caracteres)` → `Circunstancias (mín. 50 caracteres)` → `Atención inmediata brindada (mín. 20 caracteres)` → `Testigos opcional` → `Adjunta evidencia (foto/video, máx. 10 MB)` → `Confirmar` → AUTOMATICO → `Tarjeta de accidente creada con número auto + Estado del colaborador a Gris + Notifica al Inspector de zona + Inicia investigación + Log auditable`
