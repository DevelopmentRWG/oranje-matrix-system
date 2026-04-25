---
tags:
  - modulo/core
aliases:
  - Semáforo de Requisición
  - Status Requisición Verde manzana
  - Status Requisición Verde
  - Status Requisición Amarillo
  - Status Requisición Azul claro
  - Status Requisición Rojo
  - Status Requisición Morado
  - Status Requisición Apple Green
  - Status Requisición Green
  - Status Requisición Yellow
  - Status Requisición Light Blue
  - Status Requisición Red
  - Status Requisición Purple
---

# Semáforo de Requisición

Sistema de estados visuales que representa el ciclo de vida de una [[Requisición]], desde que el [[Hotel/Supervisor|Supervisor]] comienza a elaborarla hasta que queda cubierta.

> [!info]
> Este semáforo describe el **ciclo de vida general** de la requisición. Las otras dimensiones se manejan en semáforos separados: [[Semáforo de Urgencia de Requisición]] (clasificación por tiempo) y [[Semáforo de Posiciones de la Requisición]] (porcentaje de cobertura por posición). Para el estado del colaborador ver [[Semáforo del Colaborador]].

> [!note] Paralelismo con [[Semáforo de Posiciones de la Requisición]]
> Cada estado de la requisición tiene su espejo a nivel posición: `Verde manzana`↔`Dorado` · `Verde`↔`Naranja` · `Azul claro`↔`Verde` · `Rojo`↔`Amarillo/Rojo` · `Morado`↔`Morado`.

## Estados

| Color         | Estado                | Responsable                                                            | Descripción                                              |
| ------------- | --------------------- | ---------------------------------------------------------------------- | -------------------------------------------------------- |
| Verde manzana | En elaboración        | [[Hotel/Supervisor\|SUP]] o [[Hotel/Manager del Hotel\|GH]] | En elaboración por el hotel.                             |
| Verde         | Autorizada            | [[Hotel/Manager del Hotel\|GH]]                                        | Autorizada por el gerente del hotel.                     |
| Amarillo      | En proceso            | [[Reclutadora]] (asignada por [[Manager de Reclutamiento]])            | En proceso de asignación de personal.                    |
| Azul claro    | Cubierta totalmente   | [[Reclutadora]]                                                        | Requisición cubierta totalmente.                         |
| Rojo          | Cubierta parcialmente | [[Reclutadora]]                                                        | Requisición cubierta parcialmente.                       |
| Morado        | Eliminada             | —                                                                      | Requisición eliminada físicamente.                       |

## Detalle por estado

### Verde manzana — En elaboración
**Responsable:** [[Hotel/Supervisor|SUP]] o [[Hotel/Manager del Hotel|GH]]

El hotel inicia la creación de la requisición y sus posiciones.

**Avance →** cuando el [[Hotel/Manager del Hotel|GH]] autoriza la requisición, pasa a [[#Verde — Autorizada|Verde]]. Solo el GH puede autorizar; si lo intenta el SUP, el sistema bloquea la acción.

---

### Verde — Autorizada
**Responsable:** [[Hotel/Manager del Hotel|GH]]

La requisición queda lista para asignación. El sistema calcula automáticamente la urgencia (ver [[Semáforo de Urgencia de Requisición]]).

**Avance →** el [[Manager de Reclutamiento]] recibe la requisición y la asigna a una [[Reclutadora]]; pasa a [[#Amarillo — En proceso|Amarillo]].

---

### Amarillo — En proceso
**Responsable:** [[Reclutadora]]

La reclutadora busca y asigna colaboradores a las posiciones (ver [[Semáforo de Posiciones de la Requisición]] y [[Semáforo del Colaborador]]).

### Decisión

**¿Se cubren todas las posiciones?**

- **SÍ →** [[#Azul claro — Cubierta totalmente|Azul claro]]
- **NO →** [[#Rojo — Cubierta parcialmente|Rojo]]

---

### Azul claro — Cubierta totalmente
**Responsable:** [[Reclutadora]]

Todas las posiciones llegaron a 100% (ver `Verde` en [[Semáforo de Posiciones de la Requisición]]).

**Fin del ciclo activo** — la requisición queda cerrada satisfactoriamente.

---

### Rojo — Cubierta parcialmente
**Responsable:** [[Reclutadora]]

La requisición cerró con al menos una posición en `Amarillo` o `Rojo` a nivel [[Semáforo de Posiciones de la Requisición|posición]].

**Fin del ciclo activo** — con cobertura incompleta.

---

### Morado — Eliminada

Estado transversal: se alcanza desde cualquier estado anterior cuando se elimina físicamente la requisición. El sistema registra journal.

## Relacionado

- [[Requisición]]
- [[Semáforo de Urgencia de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
- [[Semáforo del Colaborador]]
- [[Flujo de Reclutamiento]]
- [[Reclutadora]]
- [[Manager de Reclutamiento]]
- [[Hotel/Supervisor|Supervisor]]
- [[Hotel/Manager del Hotel|Manager del Hotel]]
