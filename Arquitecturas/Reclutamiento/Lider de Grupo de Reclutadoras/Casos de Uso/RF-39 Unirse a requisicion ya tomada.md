---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-39
---

# 🪪 ID: RF-39
🏷️ **Nombre:** Tomar / Unirse a requisición ya tomada (colaborativo)

**Historia:**
El Líder ve la bandeja de Autorizadas y abre una requisición que ya están trabajando otros reclutadores (etiqueta "Compartida · N reclutadores"). En lugar de bloquearse, el sistema le ofrece **Unirme** como reclutador participante adicional. Al confirmar, la requisición aparece en "Mis Requisiciones" y el Líder pasa a trabajarla junto al resto, con el avance de cobertura **compartido** (modelo colaborativo, RR-15). Si la requisición aún no la trabaja nadie, la acción es **Tomar** y el semáforo cambia a Amarillo (En proceso).

**Criterios de aceptación:**
Una requisición ya tomada puede ser tomada por otro reclutador, que **se agrega sin desplazar a los existentes ni retroceder el semáforo** (AC-21). La ficha lista a **todos los reclutadores activos** (AC-22). Tomar/unirse NO transfiere ni bloquea la requisición: nadie pierde la requisición. El avance de cobertura es compartido; el lock de concurrencia es a nivel de **posición/slot**, no de la requisición completa: si dos asignan la misma posición, gana la primera y la segunda ve "posición ya cubierta" (AC-23). No se puede unir a una requisición ya cerrada (cubierta o parcial). Cada unión queda registrada en el **Historial** con actor y timestamp (RR-16).

> [!note]
> A las personas que trabajan una requisición se les llama **reclutadores participantes** (no "colaboradores"). "Colaborador" está reservado para el trabajador del Pool que se asigna a una posición.

**Documentación:**
- PRD: PRD-RECL-03 Líder de Grupo
- Flow: Unirse a requisición colaborativa
- Prototipo: (link de Figma)

**Flujo:**
`Bandeja de Autorizadas` → MANUAL → `Abrir requisición "Compartida · N reclutadores"` → `Click en "Unirme"` (o "Tomar" si nadie la trabaja) → `Confirmar` → AUTOMATICO → `Agrega al Líder como reclutador participante + Aparece en Mis Requisiciones + Mantiene semáforo Amarillo y lo ya asignado + Registra en el Historial quién se unió (autor + fecha)`
