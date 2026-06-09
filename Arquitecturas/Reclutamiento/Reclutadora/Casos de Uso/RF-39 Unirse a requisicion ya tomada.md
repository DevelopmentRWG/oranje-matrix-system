---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - CU RF-39
---

# 🪪 ID: RF-39
🏷️ **Nombre:** Tomar / Unirse a requisición ya tomada (colaborativo)

**Historia:**
La Reclutadora ve en la bandeja de Autorizadas una requisición que ya tiene otros reclutadores trabajándola, marcada con la etiqueta "Compartida · N reclutadores". En lugar de bloquearla o transferirla, la acción es **Unirme**: se agrega como reclutador participante adicional sin desplazar a los existentes ni retroceder el semáforo (Self-Pick colaborativo, RR-15). El avance de cobertura es compartido entre todos los reclutadores participantes; cada uno puede buscar en el Pool y asignar colaboradores a posiciones, con un lock a nivel de posición/slot (dos reclutadores no asignan el mismo colaborador a la misma posición). Si intenta unirse a una requisición en la que ya participa, el sistema lo bloquea; si la requisición ya está cerrada, tampoco permite unirse.

**Criterios de aceptación:**
Una requisición ya tomada puede ser tomada por otro reclutador que se agrega sin desplazar a los existentes ni retroceder el semáforo (AC-21). Tras unirse, la requisición aparece en "Mis Requisiciones" con la etiqueta "Compartida · N reclutadores" y el sistema notifica a los demás participantes. El evento queda registrado en el Historial de la requisición con autor (rol + nombre) y fecha (RR-16). Unirse cuando ya se participa se bloquea; unirse a una requisición cerrada se bloquea.

**Documentación:**
- PRD: PRD-RECL-02 Reclutadora
- Flow: Unirse a requisición (colaborativo)
- Prototipo: (link de Figma)

**Flujo:**
`Bandeja de Autorizadas (Compartida · N reclutadores)` → MANUAL → `Click en "Unirme"` → `Confirmar` → AUTOMATICO → `Valida que no participo ya y que no está cerrada` → `Me agrega como reclutador participante adicional (no desplaza a nadie, no retrocede semáforo)` → `Aparece en Mis Requisiciones (Compartida) + Notifica a los demás participantes + Registra en Historial con autor (RR-16)`
