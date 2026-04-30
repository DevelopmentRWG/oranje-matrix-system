---
tags:
  - modulo/core
aliases:
  - Pool de Colaboradores
  - Pool
---

# Pool de Colaboradores

Alberca donde [[Reclutamiento/Reclutamiento|Reclutamiento]] manda a todos los reclutados que pasaron el filtro y fueron aprobados. Es el lugar donde se va ordenando la información de los colaboradores aprobados y del que las [[Reclutadora|reclutadoras]] pueden tomar candidatos para asignarlos a un hotel.

> [!info] Punto de encuentro entre flujos
> La pool es el punto de encuentro entre el [[Flujo de Reclutamiento]] (que la **alimenta** con colaboradores nuevos) y el [[Flujo de Requisición]] (que la **consume** para cubrir hoteles).

## Qué contiene

- Solo entran los reclutados que **pasaron el filtro y fueron aprobados** por [[Reclutamiento/Reclutamiento|Reclutamiento]].
- Contiene el **registro del colaborador**.

## Dinámica

- El **registro del colaborador queda guardado** en la pool.
- Lo que **va cambiando es su estatus**, que corresponde a su estado en el [[Semáforo del Colaborador]].
- El estatus es **dinámico**.

## Uso por Reclutamiento

- Las [[Reclutadora|reclutadoras]] toman colaboradores de la pool para asignarlos a un hotel cuando hay match con una [[Requisición]].

## Búsqueda y filtros

La [[Reclutadora]] puede filtrar colaboradores en la pool combinando los siguientes criterios:

| Filtro | Descripción |
|---|---|
| Posición | Housekeeper, Houseman, etc. Permite encontrar colaboradores con el perfil que la requisición requiere |
| Zona | Zona geográfica del colaborador. Facilita la asignación a hoteles cercanos |
| Idioma | Preferencia de idioma del colaborador |
| Modalidad de contratación | Temporal o Permanente |
| Disponibilidad | Estado actual del [[Semáforo del Colaborador]]: solo los colaboradores en estado disponible son candidatos para asignación |

> [!info] El filtro de disponibilidad se basa directamente en el estado del [[Semáforo del Colaborador]] de cada registro en la pool.

## Relacionado

- [[Semáforo del Colaborador]]
- [[Reclutadora]]
- [[Flujo de Reclutamiento]]
- [[Flujo de Requisición]]
- [[Requisición]]
