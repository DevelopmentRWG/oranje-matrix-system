---
tags:
  - arquitectura
  - rol/supervisor-hotel
  - caso-de-uso
aliases:
  - CU RF-H-20
---

# 🪪 ID: RF-H-20
🏷️ **Nombre:** Reportar accidente laboral — Escenario A

**Historia:**
**Escenario A:** un colaborador asignado al hotel sufre un accidente y lo reporta primero desde la app del colaborador. La señal llega **simultáneamente** al Supervisor del depto y al [[Inspector]] de zona. El Supervisor debe **acudir físicamente** al lugar del incidente y capturar información presencial: ubicación exacta, circunstancias, testigos y atención inmediata brindada.

**Criterios de aceptación:**
Notificación simultánea a Supervisor y al Inspector en menos de 1 min tras el reporte del colaborador. El Supervisor debe completar el formulario presencial (todos los campos obligatorios). La descripción de circunstancias debe tener al menos 50 caracteres. La atención inmediata es obligatoria. El colaborador pasa al estado **Gris (Accidentado)** en el Semáforo del Colaborador, lo que lo protege de la regla de 3 inasistencias (RR-H-20).

**Documentación:**
- PRD: PRD-HOTEL-02 Supervisor
- Flow: Accidente Laboral — Escenario A
- Prototipo: (link de Figma)

**Flujo:**
`Sidebar → Accidentes Laborales ← Notificación push: "Colaborador X reportó accidente"` → AUTOMATICO → `Estado del colaborador a Gris + Tarjeta de accidente creada con datos del reporte del colaborador + Inspector de zona notificado simultáneamente` → MANUAL → `Supervisor acude físicamente al lugar` → `Abre la tarjeta de accidente desde la app` → `Captura presencial: ubicación exacta + circunstancias (mín. 50 caracteres) + atención inmediata (mín. 20 caracteres) + testigos opcional` → `Adjunta evidencia (foto/video, máx. 10 MB)` → `Confirma escenario A` → `Confirmar` → AUTOMATICO → `Tarjeta actualizada con captura presencial + Notifica al Inspector del avance + Queda en log auditable`
