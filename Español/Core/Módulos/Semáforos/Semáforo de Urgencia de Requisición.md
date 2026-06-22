---
tags:
  - modulo/core
aliases:
  - Semáforo de Urgencia de Requisición
  - Semáforo de Urgencia
  - Status Urgencia Rojo
  - Status Urgencia Amarillo
  - Status Urgencia Verde fuerte
---

# Semáforo de Urgencia de Requisición

Clasificación visual del nivel de urgencia con el que una [[Requisición]] necesita ser cubierta, basada en el tiempo disponible antes de la fecha de inicio.

> [!info]
> Este es uno de los semáforos de la requisición. Ver también: [[Semáforo de Requisición]], [[Semáforo de Posiciones de la Requisición]] y el [[Semáforo del Colaborador]].

## Estados

| Color        | Nivel   | Tiempo       |
| ------------ | ------- | ------------ |
| Rojo         | Urgente | < 72 hrs     |
| Amarillo     | Medio   | 72 – 120 hrs |
| Verde fuerte | Normal  | > 120 hrs    |

## Reglas clave

- **Cálculo automático por sistema** al autorizar la requisición ([[Semáforo de Requisición#Verde — Autorizada|Verde]]).
- **Parámetros:** `fecha de autorización de la requisición` vs `fecha de inicio de la posición`.
- **Fórmula:**
	- `> 120 hrs` → **Verde fuerte** (Normal)
	- `72 – 120 hrs` → **Amarillo** (Medio)
	- `< 72 hrs` → **Rojo** (Urgente)
- **Sin intervención humana**: el sistema reevalúa automáticamente y ajusta el color conforme avanza el tiempo.

## Relacionado

- [[Requisición]]
- [[Semáforo de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
- [[Reclutadora]]
