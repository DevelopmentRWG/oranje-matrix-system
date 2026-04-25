---
tags:
  - modulo/hotel
aliases:
  - SUP
  - Supervisor
---

# Supervisor

Rol operativo del módulo de [[Hotel/Hotel|Hotel]], subordinado del [[Hotel/Manager del Hotel|Manager del Hotel]]. Responsable de crear las [[Requisición|requisiciones]] de personal que el hotel necesita cubrir.

> [!note] Jerarquía extendida
> En hoteles con jerarquía extendida, este rol corresponde al Supervisor del [[Departamentos del Hotel|departamento]], subordinado al [[Hotel/Manager del Hotel|Gerente de Departamento]]. Las responsabilidades en plataforma son las mismas.

## Responsabilidades

- Crea la [[Requisición]] desde la app, especificando:
  - [[Posiciones]] requeridas.
  - Cantidad de personas por posición.
  - Fecha de inicio.
  - Horario.
  - [[Modalidades de Contratación|Modalidad de contratación]].
  - Preferencia de [[Niveles de Inglés|nivel de inglés]].
  - Notas adicionales.
- Envía la requisición al [[Hotel/Manager del Hotel|Manager del Hotel]] para su aprobación.
- Reporta [[Core/Módulos/Accidente Laboral/Accidente Laboral|accidentes laborales]] detectados en la propiedad (ver [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]], escenario B).
- Acude físicamente al lugar del incidente y captura la información presencial en la tarjeta de accidente: ubicación exacta, circunstancias, testigos y atención inmediata brindada.

> [!note] Sobre la autorización
> El Supervisor **no puede enviar** una requisición directamente a [[Reclutamiento/Reclutamiento|Reclutamiento]]. Toda requisición debe ser revisada y aprobada por el [[Hotel/Manager del Hotel|Manager del Hotel]] antes de llegar al equipo de reclutamiento.

## Relacionado

- [[Hotel/Manager del Hotel|Manager del Hotel]]
- [[Hotel/Hotel|Hotel]]
- [[Departamentos del Hotel]]
- [[Requisición]]
- [[Semáforo de Requisición]]
- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]]
- [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]]
