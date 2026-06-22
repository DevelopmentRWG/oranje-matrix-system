---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-37
---

# 🪪 ID: RF-37
🏷️ **Nombre:** Reasignar requisición a otra Reclutadora

**Historia:**
Cuando una Reclutadora está sobrecargada, ausente (vacaciones) o un caso requiere otra zona/perfil, el Líder **reasigna una de sus requisiciones en proceso a otra Reclutadora del grupo**. Elige la requisición, la Reclutadora destino y el motivo; el sistema transfiere la requisición y notifica a ambas.

**Criterios de aceptación:**
Solo se reasigna **entre Reclutadoras del propio grupo** (regla RR-10). Solo aplica a requisiciones **en proceso** (no cerradas). El **motivo es obligatorio** (balanceo de carga / Reclutadora ausente / especialización por zona / otro). Al confirmar, la requisición pasa a "Mis Requisiciones" de la Reclutadora destino, se **notifica a la Reclutadora origen y a la destino**, y queda registrado en log auditable.

> [!note]
> Distinto de **RF-17 (Reasignar colaborador)**, que mueve a un **colaborador** entre hoteles. Aquí se reasigna una **requisición** (el trabajo de cubrirla) entre Reclutadoras.

**Documentación:**
- PRD: PRD-RECL-03 Líder de Grupo
- Flow: Reasignación de requisición entre Reclutadoras
- Prototipo: (link de Figma)

**Flujo:**
`Mi Grupo → Detalle de Reclutadora` (o desde "Ver carga detallada", RF-36) → MANUAL → `Click "Reasignar requisición"` → `Selecciona requisición en proceso + Reclutadora destino + motivo` → `Confirmar` → AUTOMATICO → `Transfiere la requisición a la Reclutadora destino + Notifica a origen y destino + Registra en log`
