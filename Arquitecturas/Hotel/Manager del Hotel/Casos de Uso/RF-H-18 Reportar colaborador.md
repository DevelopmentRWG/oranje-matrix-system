---
tags:
  - arquitectura
  - rol/manager-del-hotel
  - caso-de-uso
aliases:
  - CU RF-H-18
---

# 🪪 ID: RF-H-18
🏷️ **Nombre:** Reportar colaborador (Rojo)

**Historia:**
Cuando un colaborador comete una falta grave (mala conducta, robo, conflicto, falta justificada), el Manager del Hotel lo **reporta** desde el módulo Mi Personal. Esta acción es **exclusiva del Manager del Hotel** (regla RR-H-10 — el Supervisor NO puede reportar). El colaborador pasa al estado **Rojo** en el Semáforo del Colaborador y se inicia automáticamente la investigación del Inspector de zona.

**Criterios de aceptación:**
Solo el Manager del Hotel puede reportar (RR-H-10). El motivo es obligatorio (catálogo: Falta grave / Mala conducta / Robo / Conflicto / Otro). La descripción debe tener al menos 50 caracteres para iniciar la investigación. Evidencia opcional (PDF/JPG/PNG, máx. 10 MB). El colaborador debe estar asignado al depto del Manager. Notifica al Inspector de zona en menos de 1 min. Queda en log auditable.

**Documentación:**
- PRD: PRD-HOTEL-03 Manager del Hotel
- Flow: Reporte de colaborador (Rojo)
- Prototipo: (link de Figma)

**Flujo:**
`Módulo Mi Personal → Detalle del colaborador` → MANUAL → `Click "Reportar"` → `Selecciona motivo (catálogo)` → `Escribe descripción detallada (mín. 50 caracteres)` → `Adjunta evidencia opcional` → `Agrega testigos opcional` → `Confirmar` → AUTOMATICO → Si validaciones OK → `Estado del colaborador a Rojo + Notifica al Inspector de zona + Inicia investigación + Registra en log auditable + Notifica al Supervisor del depto` / Si descripción <50 caracteres → `Bloquea con mensaje`
