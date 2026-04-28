---
tags:
  - modulo/core
aliases:
  - Semáforo del Colaborador
  - Status Colaborador Blanco
  - Status Colaborador Verde manzana
  - Status Colaborador Azul claro
  - Status Colaborador Naranja
  - Status Colaborador Verde fuerte
  - Status Colaborador Amarillo
  - Status Colaborador Café
  - Status Colaborador Rosa
  - Status Colaborador Morado
  - Status Colaborador Rojo
  - Status Colaborador Gris
  - Status Colaborador Negro
---

# Semáforo del Colaborador

Sistema de estados visuales que representa la situación actual de cada colaborador dentro de Oranje. Cada color corresponde a un estado con reglas propias de transición.

> [!info]
> Este semáforo describe al **colaborador**. Los estados de la requisición se manejan en otros semáforos: [[Semáforo de Requisición]], [[Semáforo de Urgencia de Requisición]] y [[Semáforo de Posiciones de la Requisición]].

## Estados

| Color         | Estado                                | Descripción                                                                                                                 |
| ------------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Blanco        | Pre-asignación                        | Apenas subió sus datos, aún no ha sido asignado a ningún hotel.                                                             |
| Verde manzana | Día 1-2                               | Colaborador nuevo, primeros días, siempre que esté asistiendo. El [[Inspector]] verifica su llegada el día 1. |
| Azul claro    | Día 3+                                | Ponchó en la propiedad al tercer día. El [[Inspector]] le entrega su uniforme.                                |
| Naranja       | Fijo                                  | Pasó una semana, listo para colaborar fijamente en el hotel.                                                                |
| Verde fuerte  | Disponible                            | Disponible para asignación (o reincorporado tras disputa a su favor).                                                       |
| Amarillo      | Disponible voluntario                 | En descanso de un hotel, se pone disponible para asignación temporal.                                                       |
| Café          | Asignación temporal                   | Asignado temporalmente a cubrir la jornada completa o una parte de la jornada.                                              |
| Rosa          | Stand-by                              | El hotel lo mandó a descansar (vacaciones, temporada baja).                                                                 |
| Morado        | No regresó                            | No asistió por causa propia.                                                                                                |
| Rojo          | Reportado                             | El hotel lo reportó; [[Inspector]] revisa el caso.                                                                          |
| Gris          | Accidentado                           | El colaborador sufrió un [[Core/Módulos/Accidente Laboral/Accidente Laboral\|accidente laboral]] y está en incapacidad médica. Protegido de [[Core/Módulos/Blacklist\|Blacklist]]. |
| Negro         | [[Core/Módulos/Blacklist\|Blacklist]] | Disputa resuelta a favor del hotel, colaborador bloqueado.                                                                  |

## Reglas clave

### Entradas al sistema

- **→ Blanco**: al registrarse el colaborador con sus datos, aún sin asignación.
- **Blanco → Verde manzana**: al ser asignado y asistir el día 1. El [[Inspector]] verifica su llegada en sitio.

### Progresión como fijo

- **Verde manzana → Azul claro**: cuando poncha en la propiedad al tercer día. En este momento el [[Inspector]] le entrega su uniforme.
- **Azul claro → Naranja**: al completar 7 días (fijo por sistema).

### Disponibilidad y asignaciones temporales

- **Naranja → Verde fuerte**: cuando el colaborador queda libre (fin de asignación fija o reincorporado).
- **Amarillo**: lo pone el colaborador (disponible voluntario durante un descanso).
- **Verde fuerte ↔ Café**: la [[Reclutadora]] lo asigna temporalmente (→ Café); al terminar la jornada temporal, vuelve a `Verde fuerte` o `Naranja` según su estado previo.

### Incidencias

- **→ Morado**: el sistema lo marca cuando el colaborador no asiste sin justificación.
- **3 inasistencias → Negro**: [[Core/Módulos/Blacklist|Blacklist]] automático por sistema.
- **Rosa**: lo pone el hotel ([[Hotel/Manager del Hotel]]) cuando manda al colaborador a descansar (vacaciones, temporada baja). Al reactivarlo, regresa a **Verde fuerte**.
- **Rojo**: lo pone el hotel ([[Hotel/Manager del Hotel]]). Luego [[Inspector]] investiga el caso y el resultado lo lleva a:
	- **Negro** ([[Core/Módulos/Blacklist|Blacklist]]), o
	- **Verde fuerte** (reincorporado).
- **Casos de [[Core/Módulos/Blacklist|Blacklist]]**: revisados por el [[Manager de Reclutamiento]].

### Accidente laboral

- **Cualquier estado activo → Gris**: cuando se genera un reporte de [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]]. El colaborador queda fuera de la operación por causa médica.
- **Gris → Verde fuerte**: al recibir el alta médica y cerrarse la tarjeta de accidente. El colaborador queda disponible para reasignación.
- **Protección de Blacklist**: mientras el colaborador esté en estado `Gris`, las inasistencias **no cuentan** para la regla de 3 inasistencias → Negro.

## Relacionado

- [[Semáforo de Requisición]]
- [[Semáforo de Urgencia de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
- [[Flujo de Reclutamiento]]
- [[Manager de Reclutamiento]]
- [[Reclutadora]]
- [[Inspector]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]]
