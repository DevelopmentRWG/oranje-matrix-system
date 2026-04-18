---
tags:
  - modulo/colaborador
aliases:
  - Colaborador
---

# Colaborador

Entidad central del sistema Oranje. Representa a la persona que es reclutada, asignada y gestionada operativamente en los hoteles. Su registro vive en el [[Pool de Colaboradores]] y su ciclo de vida se refleja en el [[Semáforo del Colaborador]].

> [!info]
> El Colaborador no es solo un registro estático: su estado cambia a lo largo del tiempo según el [[Semáforo del Colaborador]], que define en qué fase operativa se encuentra en cada momento.

## Datos del Colaborador

Los datos del colaborador se capturan en tres fases.

### Fase 1 — Entrevista inicial

Capturada por la [[Reclutadora]] durante el primer contacto:

| Campo | Capturado por |
|---|---|
| Nombre completo | Reclutadora |
| Edad | Reclutadora |
| Género | Reclutadora |
| Domicilio | Reclutadora |
| Teléfono | Reclutadora |

### Fase 2 — Alta en la app

Completada por el propio Colaborador:

| Campo | Catálogo asociado |
|---|---|
| SSN | — |
| ITIN | — |
| Posición | [[Posiciones]] |
| Nivel de inglés | [[Niveles de Inglés]] |
| Nivel de experiencia | — |
| Tipo de transporte | — |
| Modalidad | [[Modalidades de Contratación]] |

### Fase 3 — Datos de emergencia

Completada por el propio Colaborador desde la app:

| Campo | Descripción |
|---|---|
| Contacto de emergencia — nombre | Persona a contactar en caso de emergencia |
| Contacto de emergencia — teléfono | Teléfono del contacto |
| Contacto de emergencia — parentesco | Relación con el colaborador |
| Tipo de sangre | Grupo sanguíneo |
| Alergias o condiciones médicas | Información médica relevante |

## Ciclo de vida

El estado del Colaborador se gestiona a través del [[Semáforo del Colaborador]], que define 12 estados posibles desde su ingreso al [[Pool de Colaboradores]] hasta su eventual salida o bloqueo en la [[Blacklist]].

## Roles que interactúan con el Colaborador

- [[Reclutadora]] — lo recluta, valida documentos y lo asigna a un hotel.
- [[Manager de Reclutamiento]] — supervisa el proceso y revisa casos de Blacklist.
- [[Hotel/Manager del Hotel|Manager del Hotel]] — genera su QR de acceso, gestiona descansos y reportes.
- [[QA Inspector]] — verifica su llegada el Día 1, entrega uniforme en Día 3+, investiga casos Rojo.

## Operación diaria

- Su asignación semanal se registra en el [[Schedule]].
- Sus horas trabajadas se registran en el [[Timesheet]] mediante ponches vía QR (Entrada, Lunch, Salida).

## Relacionado

- [[Pool de Colaboradores]]
- [[Semáforo del Colaborador]]
- [[Blacklist]]
- [[Schedule]]
- [[Timesheet]]
- [[Flujo de Reclutamiento]]
- [[Requisición]]
- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]]
