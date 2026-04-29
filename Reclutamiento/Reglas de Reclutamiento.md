---
tags:
  - modulo/reclutamiento
aliases:
  - Reglas de Reclutamiento
---

# Reglas de Reclutamiento

Consolidación de todas las reglas de negocio que aplican al área de Reclutamiento dentro del sistema Oranje. Referencia cruzada con [[Reglas de Negocio]] (concentrado general del sistema).

## Reclutamiento continuo y Pool

> [!important] El flujo de reclutamiento es **continuo**: siempre se está contratando, haya o no requisiciones abiertas.

- Las requisiciones sin match pueden acelerar o priorizar ciertas posiciones/zonas, pero **no son condición** para iniciar el flujo.
- Solo entran al [[Pool de Colaboradores]] los colaboradores que pasaron el filtro y fueron aprobados por Reclutamiento.
- La [[Reclutadora]] debe consultar la [[Core/Módulos/Blacklist|Blacklist]] antes de reclutar a un candidato.

## Captura y aprobación de colaboradores

El proceso de reclutamiento de un colaborador consta de fases definidas en el [[Reclutamiento/Flujo de Reclutamiento|Flujo de Reclutamiento]].

| Fase | Descripción | Responsable |
|---|---|---|
| 1 — Entrevista inicial | Captura de nombre completo, edad, género, domicilio y teléfono | [[Reclutadora]] |
| 2 — Alta en la app | Colaborador completa SSN, ITIN, Posición, Nivel de inglés, Nivel de experiencia, Tipo de transporte, Modalidad | Colaborador |
| 3 — Validación y aprobación | Reclutamiento revisa los datos y aprueba o rechaza al colaborador | [[Reclutadora]] |
| 4 — Habilitación de acceso | Se habilita el acceso del colaborador a los paneles | [[Reclutadora]] |

- Colaborador aprobado ingresa al [[Pool de Colaboradores]] con [[Semáforo del Colaborador]] en estado **Blanco**.

## Requisiciones — recepción y asignación

| Paso | Acción | Responsable |
|---|---|---|
| 1 | Recibe la requisición autorizada por el [[Hotel/Manager del Hotel\|Manager del Hotel]] | [[Manager de Reclutamiento]] |
| 2 | Distribuye la requisición a una [[Reclutadora]] | [[Manager de Reclutamiento]] |
| 3 | La requisición pasa a **Amarillo** (En proceso) en el [[Core/Módulos/Semáforos/Semáforo de Requisición\|Semáforo de Requisición]] | Sistema |
| 4 | La [[Reclutadora]] consulta el [[Core/Módulos/Schedule\|Schedule]] del hotel para ver posiciones pendientes | [[Reclutadora]] |
| 5 | Si hay match → asigna al colaborador y lo registra en el Schedule | [[Reclutadora]] |
| 6 | Si no hay match → la requisición queda en espera | — |

> [!important] Las requisiciones **nunca** llegan directamente a las Reclutadoras. Siempre pasan por el [[Manager de Reclutamiento]].

## Cobertura de posiciones

Al asignar colaboradores del [[Pool de Colaboradores]] a las posiciones de una requisición, la [[Reclutadora]] afecta directamente el [[Core/Módulos/Semáforos/Semáforo de Posiciones de la Requisición|Semáforo de Posiciones de la Requisición]]:

| Color | Estado | Condición |
|---|---|---|
| Verde | 100% cubierta | Todos los colaboradores asignados a la posición están confirmados |
| Amarillo | Hasta 25% faltante | Falta hasta el 25% del personal requerido |
| Rojo | Más de 25% faltante | Falta más del 25% — requiere atención prioritaria |

> [!important] El resultado de las posiciones determina el estado final de la requisición: si **todas** llegan a Verde → la requisición pasa a **Azul claro** (cubierta totalmente). Si al menos una cierra en Amarillo o Rojo → la requisición pasa a **Rojo** (cubierta parcialmente).

## Asignación temporal (Café)

- La [[Reclutadora]] puede asignar temporalmente a un colaborador disponible (→ **Café** en el [[Semáforo del Colaborador]]).
- Al terminar la jornada temporal, el colaborador regresa a **Verde fuerte** o **Naranja** según su estado previo.

## Blacklist

| Acción | Rol | Tipo |
|---|---|---|
| Consultar la [[Core/Módulos/Blacklist\|Blacklist]] antes de reclutar | [[Reclutadora]] | Obligatoria |
| Revisar casos de Blacklist | [[Manager de Reclutamiento]] | Supervisión |

> [!note] Ningún rol de Reclutamiento puede enviar a un colaborador a Blacklist directamente. La entrada a Blacklist es automática (3 inasistencias) o ejecutada por el [[Inspector]] tras una disputa resuelta a favor del hotel.

## Supervisión interna

### Indicador de Lunch Extendido

- El [[Manager de Reclutamiento]] tiene visibilidad del Indicador de Lunch Extendido en el [[Timesheet]].
- Se activa cuando el tiempo de lunch de un colaborador excede 30 minutos.
- **No es visible** para el [[Hotel/Manager del Hotel|Manager del Hotel]] ni el [[Hotel/Supervisor|Supervisor]].
- Propósito: supervisión interna de Oranje; no es punitivo de forma automática.

### Jerarquía de supervisión

| Rol | Supervisa a | Reporta a |
|---|---|---|
| [[Manager de Reclutamiento]] | [[Reclutamiento/Líder de Grupo de Reclutadoras\|Líderes de Grupo]] | — |
| [[Reclutamiento/Líder de Grupo de Reclutadoras\|Líder de Grupo de Reclutadoras]] | [[Reclutadora\|Reclutadoras]] de su grupo | [[Manager de Reclutamiento]] |
| [[Reclutadora]] | — | [[Reclutamiento/Líder de Grupo de Reclutadoras\|Líder de Grupo]] |

## Resumen de responsabilidades por rol

| Acción | [[Reclutadora]] | [[Reclutamiento/Líder de Grupo de Reclutadoras\|Líder de Grupo]] | [[Manager de Reclutamiento]] |
|---|---|---|---|
| Entrevista inicial y captura de datos | Sí | Sí (hereda) | No |
| Validar y aprobar colaborador | Sí | Sí (hereda) | No |
| Habilitar acceso a paneles | Sí | Sí (hereda) | No |
| Recibir requisición autorizada | No | No | Sí |
| Distribuir requisiciones | No | No | Sí |
| Consultar Blacklist | Sí (obligatorio) | Sí (hereda) | — |
| Revisar casos de Blacklist | No | No | Sí |
| Asignación temporal (Café) | Sí | Sí (hereda) | No |
| Gestionar cobertura de posiciones | Sí | Sí (hereda) | No |
| Ver Indicador de Lunch Extendido | No | No | Sí |
| Supervisar Reclutadoras | No | Sí | No (supervisa Líderes) |

> [!info] La [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo de Reclutadoras]] ejecuta **todas** las responsabilidades operativas de una [[Reclutadora]], además de sus funciones de supervisión.

## Relacionado

- [[Reglas de Negocio]]
- [[Reclutadora]]
- [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo de Reclutadoras]]
- [[Manager de Reclutamiento]]
- [[Reclutamiento/Flujo de Reclutamiento|Flujo de Reclutamiento]]
- [[Core/Módulos/Requisicion/Flujo de Requisición|Flujo de Requisición]]
- [[Pool de Colaboradores]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Semáforo del Colaborador]]
- [[Core/Módulos/Semáforos/Semáforo de Requisición|Semáforo de Requisición]]
- [[Core/Módulos/Semáforos/Semáforo de Posiciones de la Requisición|Semáforo de Posiciones de la Requisición]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Timesheet]]
