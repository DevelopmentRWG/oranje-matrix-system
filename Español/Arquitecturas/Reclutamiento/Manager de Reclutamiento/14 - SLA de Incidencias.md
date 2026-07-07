---
tags:
  - arquitectura
  - rol/manager-reclutamiento
aliases:
  - SLA de Incidencias Manager
  - Tiempos de Incidencia
  - SLA Incidencias
---

# 14. SLA DE INCIDENCIAS — MANAGER DE RECLUTAMIENTO

> [!warning] PROPUESTA — pendiente de validación de negocio
> Las cifras de este documento **NO están definidas en el vault**; son un punto de partida para que Dirección y el Manager las confirmen o las descarten. Lo único que sí está documentado hoy se indica explícitamente en la sección correspondiente.

---

## Lo que SÍ está documentado hoy

Los siguientes tiempos provienen directamente de los casos de uso formalizados:

- La incidencia llega al Manager en **< 1 min** tras el escalamiento — [[Casos de Uso/RF-30 Resolver incidencia|RF-30]].
- La notificación al BD/BDC se produce en **< 1 min** al escalar a comercial — [[Casos de Uso/RF-31 Escalar a comercial|RF-31]].
- El sistema emite una alerta automática de requisición urgente sin tomar "tras N horas configuradas" ([[11 - Respuestas del Sistema]]) — **N no tiene valor definido**.

---

## Sin definir (decisiones abiertas)

Los siguientes puntos no tienen valor ni regla documentados en el vault y requieren decisión de negocio:

- Tiempo máximo de resolución de una incidencia.
- Tiempo máximo permitido en estado "En investigación" antes de actuar.
- Si existe escalado automático por timeout (el sistema cambia el estado si nadie actúa en X tiempo).
- La definición exacta de "SLA en riesgo" (qué condición lo dispara y cómo se notifica).

---

## Propuesta de SLA por prioridad

> [!warning] Las cifras de la tabla siguiente son una propuesta sujeta a validación; no representan reglas aprobadas.

| Prioridad | Atender (pasar a En investigación) | Resolver |
| --------- | ---------------------------------- | -------- |
| Crítica | < 4 h | < 24 h |
| Alta | < 8 h | < 48 h |
| Media | < 24 h | < 5 días |
| Baja | < 48 h | < 10 días |

**Definición propuesta de "SLA en riesgo":** caso que superó su tiempo objetivo de atención sin haber pasado a estado "En investigación", o que superó su tiempo objetivo de resolución sin haberse cerrado.

> [!note]
> El campo "Prioridad" también es un recurso del mockup pendiente de confirmar como dato oficial — ver [[09 - Campos de formulario]] (sección Caso de incidencia) y [[13 - Estados de Incidencia]].

---

## Preguntas a resolver

- [ ] ¿Las incidencias tienen SLA formal con tiempo límite definido, o se trabajan por prioridad sin restricción de tiempo?
- [ ] ¿Hay escalado automático por timeout? (el sistema mueve el estado si el Manager no actúa en X horas)
- [ ] ¿Cuál es el valor de N para la alerta de requisición urgente sin tomar? (ver [[11 - Respuestas del Sistema]])
- [ ] ¿Quién define y ajusta los valores de N? ¿El Manager, Dirección, o configuración de sistema?

---

## Relacionado

- [[13 - Estados de Incidencia]]
- [[Casos de Uso/RF-30 Resolver incidencia|RF-30 — Resolver incidencia]]
- [[Casos de Uso/RF-31 Escalar a comercial|RF-31 — Escalar a comercial]]
- [[09 - Campos de formulario]]
- [[11 - Respuestas del Sistema]]
- [[12 - Mockup y Decisiones de UI]]
