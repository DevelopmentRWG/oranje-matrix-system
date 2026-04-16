---
tags:
  - modulo/inspector
aliases:
  - QA Inspector
  - Inspector
---

# QA Inspector

Rol operativo encargado de la supervisión en sitio de los colaboradores asignados a un hotel, de la verificación de llegadas, de la entrega del uniforme y de la investigación de casos reportados.

## Responsabilidades

- **Verifica la llegada del colaborador el día 1** en la propiedad (transición `Blanco → Verde manzana` en el [[Semáforo del Colaborador]]).
- **Entrega del uniforme** al colaborador cuando transita a `Azul claro` (Día 3+) en el [[Semáforo del Colaborador]].
- Supervisa en sitio la operación de los colaboradores en el hotel.
- Investiga los casos de colaboradores en estado `Rojo` (reportados por el [[Hotel/Manager del Hotel]] o por 3 inasistencias) en el [[Semáforo del Colaborador]].
- Emite el resultado de la investigación, que lleva al colaborador a:
  - `Negro` ([[Core/Módulos/Blacklist|Blacklist]]), o
  - `Verde fuerte` (reincorporado).
- Apoya la operación del hotel cliente activo ([[Semáforo Onboarding#Naranja — Acuerdo firmado, hotel cliente activo|Naranja del Onboarding]]).

## Relacionado

- [[Semáforo del Colaborador]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Hotel/Manager del Hotel]]
- [[Manager de Reclutamiento]]
