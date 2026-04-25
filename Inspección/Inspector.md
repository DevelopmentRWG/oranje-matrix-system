---
tags:
  - departamento/inspeccion
aliases:
  - Inspector
  - Inspector de zona
---

# Inspector

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
- Recibe notificación de [[Core/Módulos/Accidente Laboral/Accidente Laboral|accidente laboral]] en su zona (ver [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]]).
- Complementa la tarjeta de accidente con información de seguimiento médico: traslado, diagnóstico, días de incapacidad, observaciones.
- Es el **responsable final del cierre** de la tarjeta de accidente, una vez que la información está completa.
- Al cierre, gestiona la transición del colaborador de `Gris → Verde fuerte` en el [[Semáforo del Colaborador]] cuando recibe el alta médica.
- Consulta el **Indicador de Lunch Extendido** en el [[Timesheet]] para identificar colaboradores cuyo lunch excede los 30 minutos en su zona.

## Relacionado

- [[Semáforo del Colaborador]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Hotel/Manager del Hotel]]
- [[Manager de Reclutamiento]]
- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]]
- [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]]
- [[Timesheet]]
