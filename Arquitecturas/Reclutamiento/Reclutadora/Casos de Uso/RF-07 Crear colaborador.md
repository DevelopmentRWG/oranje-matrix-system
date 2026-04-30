---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - CU RF-07
---

# 🪪 ID: RF-07
🏷️ **Nombre:** Crear colaborador (Fase 1 — Entrevista inicial)

**Historia:**
La Reclutadora realiza una entrevista inicial al candidato. Captura datos básicos (nombre, edad, género, domicilio, teléfono) y crea el registro en el sistema. Tras crear, se envía link al candidato para completar Fase 2 (alta en App) y Fase 3 (datos de emergencia).

**Criterios de aceptación:**
El registro se crea con estado "Pendiente de alta en app". Se envía link al candidato por email/SMS. La Reclutadora recibe notificación cuando el candidato completa su alta.

**Documentación:**
- PRD: PRD-RECL-02 Reclutadora
- Flow: Crear colaborador
- Prototipo: (link de Figma)

**Flujo:**
`Módulo Reclutamiento → Pool` → MANUAL → `Click en "Nuevo Colaborador"` → `Llena formulario Fase 1` → `Confirmar` → AUTOMATICO → `Crea registro + Envía link al candidato + Notifica a Reclutadora cuando completa Fase 2`
