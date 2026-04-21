---
tags:
  - modulo/core
aliases:
  - Accidente Laboral
  - Reporte de Accidente
  - Tarjeta de Accidente
---

# Accidente Laboral

Entidad que registra un incidente donde un [[Colaborador]] sufre una lesión o accidente mientras está asignado a un [[Hotel/Hotel|Hotel]]. La tarjeta se origina desde la app por el propio colaborador o por el [[Hotel/Colaborador del Gerente del Hotel|Colaborador del Gerente del Hotel]] (GHC), y se completa entre el GHC y el [[Inspector|Inspector de zona]].

> [!important] Responsable del cierre
> El [[Inspector]] es siempre el responsable final del cierre de la tarjeta, una vez que la información presencial y de seguimiento médico está completa.

## Datos de la tarjeta

### Cabecera

| Campo | Descripción |
|---|---|
| Número de reporte | Automático (mismo patrón que [[Requisición]]: fecha/hora + homoclave) |
| Hotel | [[Hotel/Hotel\|Hotel]] donde ocurrió el incidente |
| Colaborador accidentado | [[Colaborador]] afectado |
| Reportado por | Quien origina el reporte: el Colaborador o el GHC |
| Fecha y hora del incidente | Momento en que ocurrió el accidente |
| Status | Estado actual de la tarjeta |

### Información presencial

Capturada por el [[Hotel/Colaborador del Gerente del Hotel|GHC]], quien acude físicamente al lugar del incidente:

| Campo | Descripción |
|---|---|
| Ubicación exacta | Lugar dentro de la propiedad donde ocurrió |
| Circunstancias | Descripción de cómo ocurrió el accidente |
| Testigos | Personas presentes al momento del incidente |
| Atención inmediata | Primeros auxilios o atención brindada en sitio |

### Información de seguimiento

Capturada por el [[Inspector|Inspector de zona]]:

| Campo | Descripción |
|---|---|
| Traslado a centro médico | Si fue trasladado y a qué centro |
| Diagnóstico | Diagnóstico médico recibido |
| Días de incapacidad | Días otorgados de incapacidad médica |
| Observaciones médicas | Notas adicionales del seguimiento médico |

## Efecto en el Semáforo del Colaborador

Al generarse un reporte de accidente laboral, el [[Colaborador]] transita a **Gris — Accidentado** en el [[Semáforo del Colaborador]]. Este estado lo protege de la regla de 3 inasistencias → [[Blacklist]] mientras dure su incapacidad. Al recibir el alta médica y cerrarse la tarjeta, transita a `Verde fuerte` (Disponible).

## Journal

Cada cambio de status en la tarjeta genera un registro en el journal con: Número de reporte, Hotel, Colaborador, Reportado por, Status, Nota, Fecha y hora del status.

## Relacionado

- [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]]
- [[Semáforo del Colaborador]]
- [[Hotel/Colaborador del Gerente del Hotel|Colaborador del Gerente del Hotel]]
- [[Inspector]]
- [[Colaborador]]
- [[Hotel/Hotel|Hotel]]
- [[Core/Módulos/Blacklist|Blacklist]]
