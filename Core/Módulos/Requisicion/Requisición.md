---
tags:
  - modulo/core
aliases:
  - Requisición
  - Requisiciones
---

# Requisición

Solicitud que el [[Hotel/Supervisor|Supervisor]] envía al equipo de [[Reclutamiento/Reclutamiento|Reclutamiento]] para cubrir una o más [[Posiciones]]. Una requisición está compuesta por **una cabecera** y **una o más posiciones solicitadas**.

## Estructura

Una requisición se compone de:

- **Cabecera**: datos generales de la requisición (hotel, roles asignados, estado).
- **Posiciones solicitadas**: una o varias posiciones, cada una con su propio detalle (cantidad, fecha, horario, etc.).

## Cabecera

Datos generales que identifican la requisición:

| Campo                | Descripción                                                                                  |
| -------------------- | -------------------------------------------------------------------------------------------- |
| Número de requisición | Identificador único de la requisición.                                                      |
| Hotel                | Hotel que solicita el personal.                                                              |
| SUP                  | [[Hotel/Supervisor\|Supervisor]] que creó la requisición.              |
| HM (Hotel Manager)   | [[Hotel/Manager del Hotel\|Manager del Hotel]] responsable. También conocido como Gerente de Hotel. |
| Reclutador           | [[Reclutadora]] asignada a atender la requisición.                                           |
| Inspector            | [[Inspector]] correspondiente a la [[Zonas\|zona]] del hotel.                             |
| Status (color)       | Estado actual según el [[Semáforo de Requisición]].                                          |

> [!note] Sobre el Inspector en la cabecera
> Cada hotel pertenece a una [[Zonas|zona]] y a cada zona le corresponde un [[Inspector]]. Por cualquier disputa que suceda, el inspector de la zona del hotel debe enterarse y darle seguimiento — por eso queda registrado desde la cabecera.

## Posiciones solicitadas

Cada requisición puede incluir una o más posiciones. Cada posición registra:

| Campo                    | Descripción                                                                          |
| ------------------------ | ------------------------------------------------------------------------------------ |
| Número de requisición    | Referencia a la requisición a la que pertenece.                                      |
| Número de posición       | Identificador de la posición dentro de la requisición.                               |
| Posición                 | Tipo de puesto solicitado (ver [[Posiciones]]: Housekeeper, Houseman, etc.).         |
| Modalidad                | Modalidad de contratación (ver [[Modalidades de Contratación]]).                     |
| Cantidad de personas     | Cuántos colaboradores se necesitan para esta posición.                               |
| Fecha de inicio          | Fecha en que se requiere el personal.                                                |
| Horario                  | Horario de la posición.                                                              |
| Preferencia de idioma    | Nivel de inglés preferido. Ver [[Niveles de Inglés]].                                |
| Notas                    | Aclaraciones adicionales del hotel.                                                  |

> [!note] Sobre la fecha de fin
> La posición tiene **fecha de inicio** pero **no fecha de fin** definida. La posición termina cuando el [[Hotel/Manager del Hotel|Manager del Hotel]] manda al colaborador a descansar (estado **Rosa - Stand-by** en el [[Semáforo del Colaborador]]).

## Niveles de urgencia

El nivel de urgencia se clasifica según el [[Semáforo de Urgencia de Requisición]], basado en el tiempo hasta la fecha de inicio.

## Estados

Una requisición tiene varios estados visuales que aplican a distintas dimensiones:

- **[[Semáforo de Requisición]]** — estado general del ciclo de vida (en elaboración, autorizada, en proceso, cubierta).
- **[[Semáforo de Urgencia de Requisición]]** — nivel de urgencia basado en el tiempo.
- **[[Semáforo de Posiciones de la Requisición]]** — porcentaje de cobertura por cada posición solicitada.

## Flujo

Ver [[Flujo de Requisición]].

## Relacionado

- [[Flujo de Requisición]]
- [[Semáforo de Requisición]]
- [[Semáforo de Urgencia de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
- [[Flujo de Reclutamiento]]
- [[Posiciones]]
- [[Modalidades de Contratación]]
- [[Niveles de Inglés]]
- [[Zonas]]
- [[Inspector]]
- [[Hotel/Manager del Hotel|Manager del Hotel]]
- [[Hotel/Supervisor|Supervisor]]
- [[Reclutadora]]
- [[Manager de Reclutamiento]]
