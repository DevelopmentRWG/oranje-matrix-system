---
tags:
  - modulo/core
aliases:
  - Semáforo del Colaborador
  - Semáforo
---

# Semáforo del Colaborador

Sistema de estados visuales que representa la situación actual de cada colaborador dentro de Oranje. Cada color corresponde a un estado con reglas propias de transición.

> [!info]
> Este semáforo describe al **colaborador**. Los estados de la requisición se manejan en otros semáforos: [[Semáforo de Requisición]], [[Semáforo de Urgencia de Requisición]] y [[Semáforo de Posiciones de la Requisición]].

## Estados

| Color         | Estado                                | Descripción                                                                                     |
| ------------- | ------------------------------------- | --------------------------------------------------------------------------------- |
| Blanco        | Pre-asignación                        | Apenas subió sus datos, aún no ha sido asignado a ningún hotel.                                 |
| Verde manzana | Día 1-2                               | Colaborador nuevo, primeros días, siempre que esté asistiendo.                                  |
| Azul claro    | Día 3+                                | Ponchó en la propiedad al tercer día.                                                           |
| Naranja       | Fijo                                  | Pasó una semana, listo para colaborar fijamente en el hotel.                                    |
| Verde fuerte  | Disponible                            | Disponible para asignación (o reincorporado tras disputa a su favor).                           |
| Amarillo      | Disponible voluntario                 | En descanso de un hotel, se pone disponible para asignación temporal.                           |
| Café          | Asignación temporal                   | Asignado temporalmente a cubrir la jornada completa o una parte de la jornada.                  |
| Rosa          | Stand-by                              | El hotel lo mandó a descansar (vacaciones, temporada baja).                                     |
| Morado        | No regresó                            | No asistió por causa propia.                                                                    |
| Rojo          | Reportado                             | El hotel lo reportó (o acumuló 3 inasistencias); [[QA Inspector]] revisa el caso.               |
| Negro         | [[Core/Módulos/Blacklist\|Blacklist]] | Disputa resuelta a favor del hotel, colaborador bloqueado.                                      |

## Reglas clave

- **Blanco → Verde manzana**: al ser asignado y asistir el día 1.
- **3 inasistencias → Negro**: [[Core/Módulos/Blacklist|Blacklist]] automático por sistema.
- **Rojo**: lo pone el hotel. Luego [[QA Inspector]] investiga el caso y el resultado lo lleva a:
	- **Negro** ([[Core/Módulos/Blacklist|Blacklist]]), o
	- **Verde fuerte** (reincorporado).
- **Rosa**: lo pone el hotel.
- **Amarillo**: lo pone el colaborador.
- **Casos de [[Core/Módulos/Blacklist|Blacklist]]**: revisados por el [[Manager de Reclutamiento]].

## Relacionado

- [[Semáforo de Requisición]]
- [[Semáforo de Urgencia de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
- [[Flujo de Reclutamiento]]
- [[Manager de Reclutamiento]]
- [[Reclutadora]]
- [[QA Inspector]]
- [[Core/Módulos/Blacklist|Blacklist]]
