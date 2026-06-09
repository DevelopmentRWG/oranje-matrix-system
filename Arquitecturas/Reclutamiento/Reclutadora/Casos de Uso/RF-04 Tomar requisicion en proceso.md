---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - CU RF-04
---

# 🪪 ID: RF-04
🏷️ **Nombre:** Tomar requisición en proceso (Self-Pick colaborativo)

**Historia:**
La Reclutadora ve la bandeja de Autorizadas con todas las requisiciones disponibles. Selecciona una que pueda cubrir y la "toma" libremente (Self-Pick colaborativo, RR-15). La requisición aparece en Mis Requisiciones y el semáforo cambia automáticamente a Amarillo (En proceso). Tomarla **no la bloquea**: otras Reclutadoras pueden unirse como reclutadores participantes adicionales.

**Criterios de aceptación:**
Al tomar la requisición, esta aparece en "Mis Requisiciones" en menos de 2s y el semáforo cambia a Amarillo automáticamente. Otras Reclutadoras pueden unirse a la misma requisición (no queda bloqueada). El evento queda registrado en el Historial de la requisición con autor y fecha.

**Documentación:**
- PRD: PRD-RECL-02 Reclutadora
- Flow: Tomar requisición
- Prototipo: (link de Figma)

**Flujo:**
`Bandeja de Autorizadas` → MANUAL → `Click en "Tomar"` → `Confirmar selección` → AUTOMATICO → `Me agrega como reclutador participante + Mueve a Mis Requisiciones + Semáforo Amarillo + Registra en Historial (RR-16)`
