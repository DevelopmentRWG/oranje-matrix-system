---
tags:
  - modulo/hotel
aliases:
  - SUP
  - Supervisor
---

# Supervisor

Rol operativo del módulo de [[Hotel/Hotel|Hotel]], subordinado del [[Hotel/Manager de Área|Manager de Área]]. Responsable de crear las [[Requisición|requisiciones]] de personal que el hotel necesita cubrir.

> [!note] Jerarquía extendida
> En hoteles con jerarquía extendida, este rol corresponde al Supervisor del [[Departamentos del Hotel|departamento]], subordinado al [[Hotel/Manager de Área|Manager de Área]] de su departamento. Las responsabilidades en plataforma son las mismas.

## Responsabilidades

### Requisiciones

- Crea la [[Requisición]] desde la app, especificando:
  - [[Posiciones]] requeridas.
  - Cantidad de personas por posición.
  - Fecha de inicio.
  - Horario.
  - [[Modalidades de Contratación|Modalidad de contratación]].
  - Preferencia de [[Niveles de Inglés|nivel de inglés]].
  - Notas adicionales.
- Envía la requisición al [[Hotel/Manager de Área|Manager de Área]] para su aprobación.

> [!note] Sobre la autorización
> El Supervisor **no puede autorizar** una requisición. Toda requisición debe ser revisada y aprobada por el [[Hotel/Manager de Área|Manager de Área]] o el [[Hotel/Manager General|Manager General]] antes de llegar al equipo de [[Reclutamiento/Reclutamiento|Reclutamiento]].

### Gestión de personal asignado

- Manda a colaboradores a descansar (estado **Rosa — Stand-by** en el [[Semáforo del Colaborador]]).
- Reporta colaboradores (estado **Rojo — Reportado** en el [[Semáforo del Colaborador]]).
- Reporta [[Core/Módulos/Accidente Laboral/Accidente Laboral|accidentes laborales]] detectados en la propiedad (ver [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]]).
- Acude físicamente al lugar del incidente y captura la información presencial en la tarjeta de accidente: ubicación exacta, circunstancias, testigos y atención inmediata brindada.

## Relacionado

- [[Hotel/Manager de Área|Manager de Área]]
- [[Hotel/Manager General|Manager General]]
- [[Hotel/Hotel|Hotel]]
- [[Departamentos del Hotel]]
- [[Requisición]]
- [[Semáforo de Requisición]]
- [[Semáforo del Colaborador]]
- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]]
- [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]]
