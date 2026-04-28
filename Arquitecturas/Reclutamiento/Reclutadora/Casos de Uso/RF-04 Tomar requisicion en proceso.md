---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - CU RF-04
---

# 🪪 ID: RF-04
🏷️ **Nombre:** Tomar requisición en proceso (Self-Pick)

**Historia:**
La Reclutadora ve la bandeja de Autorizadas con todas las requisiciones disponibles. Selecciona una que pueda cubrir y la "toma" libremente (modelo Self-Pick). La requisición pasa de Autorizadas a Mis Requisiciones y el semáforo cambia automáticamente a Amarillo (En proceso).

**Criterios de aceptación:**
Al tomar la requisición, esta aparece en "Mis Requisiciones" en menos de 2s y el semáforo cambia a Amarillo automáticamente. Otra Reclutadora ya no puede tomarla.

**Documentación:**
- PRD: PRD-RECL-02 Reclutadora
- Flow: Tomar requisición
- Prototipo: (link de Figma)

**Flujo:**
`Bandeja de Autorizadas` → MANUAL → `Click en "Tomar"` → `Confirmar selección` → AUTOMATICO → `Mueve a Mis Requisiciones + Semáforo Amarillo + Bloquea para otros`
