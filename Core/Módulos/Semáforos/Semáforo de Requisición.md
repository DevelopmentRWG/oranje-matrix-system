---
tags:
  - modulo/core
aliases:
  - Semáforo de Requisición
---

# Semáforo de Requisición

Sistema de estados visuales que representa el ciclo de vida de una [[Requisición]], desde que el [[Hotel/Solicitante del Hotel|Solicitante del Hotel]] comienza a elaborarla hasta que queda cubierta.

> [!info]
> Este semáforo describe el **ciclo de vida general** de la requisición. Las otras dimensiones se manejan en semáforos separados: [[Semáforo de Urgencia de Requisición]] (clasificación por tiempo) y [[Semáforo de Posiciones de la Requisición]] (porcentaje de cobertura por posición). Para el estado del colaborador ver [[Semáforo del Colaborador]].

## Estados

| Color         | Estado                | Descripción                                                                        |
| ------------- | --------------------- | ---------------------------------------------------------------------------------- |
| Verde manzana | En elaboración        | Requisición en elaboración por el hotel (GHC o GH).                                |
| Verde         | Autorizada            | Requisición autorizada por el [[Hotel/Manager del Hotel\|Gerente del Hotel]] (GH). |
| Amarillo      | En proceso            | En proceso de asignación de personal por el reclutador.                            |
| Azul claro    | Cubierta totalmente   | Requisición cubierta totalmente por el reclutador.                                 |
| Rojo          | Cubierta parcialmente | Requisición cubierta parcialmente por el reclutador.                               |
| Morado        | Eliminada             | Requisición eliminada físicamente.                                                 |

## Relacionado

- [[Requisición]]
- [[Semáforo de Urgencia de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
- [[Semáforo del Colaborador]]
- [[Flujo de Reclutamiento]]
- [[Reclutadora]]
- [[Manager de Reclutamiento]]
- [[Hotel/Solicitante del Hotel|Solicitante del Hotel]]
- [[Hotel/Manager del Hotel|Manager del Hotel]]
