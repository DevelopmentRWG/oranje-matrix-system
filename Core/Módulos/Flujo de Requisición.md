---
tags:
  - modulo/core
aliases:
  - Flujo de Requisición
---

# Flujo de Requisición

Ciclo de vida de una [[Requisición]]: desde que el [[Hotel/Solicitante del Hotel|Solicitante del Hotel]] la crea hasta que queda **Cubierta** (total o parcialmente). Este flujo **consume** colaboradores de la [[Pool de Colaboradores]]; no los produce.

> [!info] Punto de encuentro con el [[Flujo de Reclutamiento]]
> La [[Pool de Colaboradores]] es el único punto donde ambos flujos se conectan. El [[Flujo de Reclutamiento]] corre de forma **continua** alimentando la pool (haya o no requisiciones); este flujo la **consume** cuando necesita cubrir posiciones.

## Pasos

1. **Creación** — El [[Hotel/Solicitante del Hotel|Solicitante del Hotel]] crea la requisición desde la app (estado **En elaboración**).
2. **Envío a revisión** — El Solicitante la envía al [[Hotel/Manager del Hotel|Manager del Hotel]] (estado **Pendiente de aprobación**).
3. **Revisión del HM**:
   - Si **aprueba** → estado **Autorizada**. La requisición llega al [[Manager de Reclutamiento]].
   - Si **rechaza** → regresa a **En elaboración** con observaciones.
4. **Asignación** — El [[Manager de Reclutamiento]] asigna la requisición a una [[Reclutadora]] (estado **En proceso**).
5. **Búsqueda de match en la [[Pool de Colaboradores]]**:
   - **Si hay match** → la reclutadora asigna al colaborador al hotel; el colaborador se registra en el [[Core/Módulos/Schedule|Schedule]] del hotel.
   - **Si no hay match** → la requisición queda esperando a que el [[Flujo de Reclutamiento]] (que corre de forma continua) incorpore colaboradores compatibles a la pool. Puede escalarse prioridad por zona/posición, pero no se "lanza" el reclutamiento — ya está siempre activo.
6. **Cierre** — La requisición queda como **Cubierta totalmente** o **Cubierta parcialmente**.

## Estados

Los estados de la requisición se rigen por:

- [[Semáforo de Requisición]] — ciclo de vida general.
- [[Semáforo de Urgencia de Requisición]] — urgencia por tiempo.
- [[Semáforo de Posiciones de la Requisición]] — cobertura por posición.

## Relacionado

- [[Requisición]]
- [[Pool de Colaboradores]]
- [[Flujo de Reclutamiento]]
- [[Hotel/Solicitante del Hotel|Solicitante del Hotel]]
- [[Hotel/Manager del Hotel|Manager del Hotel]]
- [[Manager de Reclutamiento]]
- [[Reclutadora]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Semáforo de Requisición]]
- [[Semáforo de Urgencia de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
