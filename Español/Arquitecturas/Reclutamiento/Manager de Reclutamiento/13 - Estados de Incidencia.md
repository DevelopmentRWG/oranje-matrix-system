---
tags:
  - arquitectura
  - rol/manager-reclutamiento
aliases:
  - Estados de Incidencia Manager
  - Ciclo de Vida de Incidencia
  - Catálogo de Estados de Incidencia
---

# 13. ESTADOS DE INCIDENCIA — MANAGER DE RECLUTAMIENTO

Catálogo del ciclo de vida de un caso de incidencia desde que es escalado al Manager hasta su cierre.

> [!note]
> Los estados a continuación son **inferidos** del flujo de [[Casos de Uso/RF-30 Resolver incidencia|RF-30]] y [[Casos de Uso/RF-31 Escalar a comercial|RF-31]]. El único estado nombrado explícitamente en los RF es **"Escalado a comercial"**; los demás nombres provienen del mockup y están **sujetos a validación**. Los colores son los usados en el mockup (tablero kanban).

---

## Estados

| Estado | Color (mockup) | Descripción | Cómo se entra |
| ---------------------- | -------------- | ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| **Abierto** | `#E11919` (rojo) | Recién escalado, sin investigar. Estado inicial al recibirse. | Un Líder, Inspector o el Sistema escala el caso (RF-30, [[11 - Respuestas del Sistema]]). |
| **En investigación** | `#3B7DDD` (azul) | El Manager revisa evidencia, comentarios, historial e involucrados. | Al pulsar "Investigar" (RF-30). |
| **Esperando info** | `#E6B422` (amarillo) | El Manager solicitó más información; el caso sigue abierto a la espera de respuesta. | Decisión "Solicitar más información" (RF-30). |
| **Escalado a comercial** | `#7B2CBF` (morado) | Notificado al BD/BDC del hotel; el caso pasa al área comercial. | Decisión "Escalar a comercial" ([[Casos de Uso/RF-31 Escalar a comercial|RF-31]]). |
| **Escalado a Dirección** | `#FF7A00` (naranja) | Caso completo enviado al Director. | Acción "Escalar a Dirección" ([[08 - Acciones del Usuario]], [[11 - Respuestas del Sistema]]). |
| **Resuelto (cerrado)** | — (sale de la bandeja) | Caso cerrado con decisión final y comentario obligatorio. | Decisión "Resolver" (RF-30). |

---

## Reglas de transición

- **Abierto → En investigación**: el Manager pulsa "Investigar" (RF-30).
- **En investigación → Resuelto**: decisión "Resolver" con comentario obligatorio (RF-30).
- **En investigación → Escalado a comercial**: decisión "Escalar a comercial", dispara RF-31.
- **En investigación → Esperando info**: decisión "Solicitar más información" (RF-30).
- **En investigación → Escalado a Dirección**: acción "Escalar a Dirección" (doc 08/11).
- **Esperando info → En investigación**: al recibir la información solicitada.
- **Escalado a comercial → Resuelto**: el área comercial cierra el caso.
- **Escalado a comercial → Escalado a Dirección**: el Manager lo eleva además a Dirección.
- **Escalado a Dirección → Resuelto**: Dirección emite resolución final.
- **Todo cierre** notifica a los involucrados (Líder, Reclutadora, Inspector, hotel si aplica) y queda en log auditable (RF-30).

---

## Relacionado

- [[Casos de Uso/RF-30 Resolver incidencia|RF-30 — Resolver incidencia]]
- [[Casos de Uso/RF-31 Escalar a comercial|RF-31 — Escalar a comercial]]
- [[08 - Acciones del Usuario]]
- [[09 - Campos de formulario]]
- [[11 - Respuestas del Sistema]]
- [[14 - SLA de Incidencias]]
- [[12 - Mockup y Decisiones de UI]]
