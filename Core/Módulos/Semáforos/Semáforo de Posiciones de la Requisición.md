---
tags:
  - modulo/core
aliases:
  - Semáforo de Posiciones de la Requisición
  - Semáforo de Posiciones
  - Status Posiciones Dorado
  - Status Posiciones Naranja
  - Status Posiciones Verde
  - Status Posiciones Amarillo
  - Status Posiciones Rojo
  - Status Posiciones Morado
  - Status Posiciones Gold
  - Status Posiciones Orange
  - Status Posiciones Green
  - Status Posiciones Yellow
  - Status Posiciones Red
  - Status Posiciones Purple
---

# Semáforo de Posiciones de la Requisición

Estado visual del porcentaje de cobertura de cada posición dentro de una [[Requisición]]. Indica qué tan cerca está cada posición de haber sido completamente cubierta por la [[Reclutadora]].

> [!info]
> Este es uno de los semáforos de la requisición. Ver también: [[Semáforo de Requisición]], [[Semáforo de Urgencia de Requisición]] y el [[Semáforo del Colaborador]].

> [!note] Equivalencia con el sistema técnico
> La documentación usa colores en español, mientras que el sistema interno los nombra en inglés: Dorado=Gold · Naranja=Orange · Verde=Green · Amarillo=Yellow · Rojo=Red · Morado=Purple. Ambos nombres son alias válidos.

## Estados

| Color    | Estado              | Responsable                                                           | Descripción                                                                                         |
| -------- | ------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Dorado   | En preparación      | [[Hotel/Colaborador del Gerente del Hotel\|GHC]] o [[Hotel/Manager del Hotel\|GH]] | Posición en preparación por el hotel.                                                               |
| Naranja  | Autorizada          | [[Hotel/Manager del Hotel\|GH]]                                       | Posición autorizada por el gerente del hotel. El sistema calcula prioridad ([[Semáforo de Urgencia de Requisición]]). |
| Verde    | 100% cubierta       | [[Reclutadora]]                                                       | Posición cubierta al 100%.                                                                          |
| Amarillo | Hasta 25% faltante  | [[Reclutadora]]                                                       | Hasta 25% de personal faltante.                                                                     |
| Rojo     | Más de 25% faltante | [[Reclutadora]]                                                       | Más del 25% de personal faltante.                                                                   |
| Morado   | Eliminada           | —                                                                     | Posición eliminada físicamente.                                                                     |

## Detalle por estado

### Dorado — En preparación
**Responsable:** [[Hotel/Colaborador del Gerente del Hotel|GHC]] o [[Hotel/Manager del Hotel|GH]]

La posición se crea junto con la requisición y se prepara con sus datos (perfil, cantidad, fecha de inicio).

**Avance →** cuando el [[Hotel/Manager del Hotel|GH]] autoriza la requisición completa, cada posición pasa a [[#Naranja — Autorizada|Naranja]] y el sistema calcula su prioridad.

---

### Naranja — Autorizada
**Responsable:** [[Hotel/Manager del Hotel|GH]]

La posición queda lista para asignación. El sistema asocia automáticamente un nivel de urgencia (ver [[Semáforo de Urgencia de Requisición]]).

**Avance →** según la cobertura gestionada por la [[Reclutadora]]:
- 100% cubierta → [[#Verde — 100% cubierta|Verde]]
- Hasta 25% faltante → [[#Amarillo — Hasta 25% faltante|Amarillo]]
- Más del 25% faltante → [[#Rojo — Más de 25% faltante|Rojo]]

---

### Verde — 100% cubierta
**Responsable:** [[Reclutadora]]

Todos los colaboradores asignados a esta posición están confirmados.

---

### Amarillo — Hasta 25% faltante
**Responsable:** [[Reclutadora]]

Falta hasta 25% del personal. La reclutadora sigue buscando coberturas.

---

### Rojo — Más de 25% faltante
**Responsable:** [[Reclutadora]]

Falta más del 25%. Requiere atención prioritaria.

---

### Morado — Eliminada

Estado transversal. Se alcanza desde cualquier estado cuando la posición se elimina físicamente; el sistema registra journal.

## Reglas clave

- **Relación con [[Semáforo de Requisición]]:**
  - La requisición queda **Azul claro** cuando **todas** sus posiciones llegan a `Verde`.
  - La requisición queda **Rojo** si al menos una posición cierra en `Amarillo` o `Rojo`.
- **La prioridad** (Urgencia) se calcula automáticamente al pasar a `Naranja`.
- **Eliminación**: puede suceder en cualquier estado (→ `Morado`).

## Relacionado

- [[Requisición]]
- [[Posiciones]]
- [[Semáforo de Requisición]]
- [[Semáforo de Urgencia de Requisición]]
- [[Reclutadora]]
