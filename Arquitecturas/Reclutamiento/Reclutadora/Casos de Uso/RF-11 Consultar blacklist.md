---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - CU RF-11
---

# 🪪 ID: RF-11
🏷️ **Nombre:** Consultar Blacklist

**Historia:**
Antes de asignar a un candidato, la Reclutadora DEBE consultar la Blacklist (regla RR-02). Si el candidato figura en Blacklist, el sistema bloquea la asignación con alerta visible y muestra el motivo del veto.

**Criterios de aceptación:**
La consulta es obligatoria antes de cada asignación. Si el candidato está en Blacklist, el sistema bloquea con alerta visible y muestra el motivo + fecha del veto.

**Documentación:**
- PRD: PRD-RECL-02 Reclutadora
- Flow: Consulta Blacklist
- Prototipo: (link de Figma)

**Flujo:**
`Módulo Pool / Asignación` → AUTOMATICO → `Sistema verifica si candidato está en Blacklist` → Si está → `Bloquea con alerta + Muestra motivo del veto` / Si no está → `Permite continuar con asignación`
