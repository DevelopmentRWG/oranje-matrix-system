---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - CU RF-06
---

# 🪪 ID: RF-06
🏷️ **Nombre:** Buscar candidatos en Pool

**Historia:**
La Reclutadora abre el Pool de Colaboradores y aplica filtros (posición, zona, modalidad, inglés, disponibilidad) para encontrar candidatos que cumplan con los requisitos de la requisición tomada.

**Criterios de aceptación:**
La búsqueda devuelve resultados en menos de 2 segundos. Permite combinar al menos 4 filtros simultáneamente. Muestra el Semáforo del Colaborador en cada resultado.

**Documentación:**
- PRD: PRD-RECL-02 Reclutadora
- Flow: Búsqueda en Pool
- Prototipo: (link de Figma)

**Flujo:**
`Módulo Reclutamiento → Pool` → MANUAL → `Aplicar filtros` → AUTOMATICO → `Sistema filtra Pool en <2s` → `Lista de candidatos disponibles` → MANUAL → `Click en candidato` → `Vista de detalle del colaborador`
