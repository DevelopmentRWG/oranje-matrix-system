---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-36
---

# 🪪 ID: RF-36
🏷️ **Nombre:** Ver carga detallada de la Reclutadora

**Historia:**
Desde el detalle de una Reclutadora en el módulo "Mi Grupo", el Líder abre su **carga actual**: las requisiciones que tiene **en proceso** (no cerradas), con hotel · zona, posición, urgencia (semáforo) y % de cobertura. Le permite ver de un vistazo si una Reclutadora está sobrecargada o tiene casos urgentes sin avance, para decidir si la apoya o reasigna alguna requisición (RF-37).

**Criterios de aceptación:**
Alcance restringido a Reclutadoras del propio grupo (regla RR-10). Muestra **solo requisiciones en proceso** (activas), no el histórico de cerradas. Por cada requisición: ID, hotel · zona, posición, urgencia (🔴/🟡/🟢) y % de cobertura. Se abre desde el detalle de la Reclutadora (RF-23). Desde aquí se puede disparar la reasignación (RF-37).

**Documentación:**
- PRD: PRD-RECL-03 Líder de Grupo
- Flow: Carga actual de la Reclutadora
- Prototipo: (link de Figma)

**Flujo:**
`Mi Grupo → Click en Reclutadora (RF-23)` → MANUAL → `Click "Ver carga detallada"` → AUTOMATICO → `Sistema lista las requisiciones EN PROCESO de esa Reclutadora con urgencia y % de cobertura` → MANUAL → `(opcional) Reasignar una requisición (RF-37)` o `Cerrar`
