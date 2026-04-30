---
tags:
  - modulo/colaborador
aliases:
  - Reglas del Colaborador
---

# Reglas del Colaborador

Consolidación de todas las reglas de negocio que aplican al Colaborador dentro del sistema Oranje. Referencia cruzada con [[Reglas de Negocio]] (concentrado general del sistema).

## Captura de datos en 3 fases

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

## Semáforo y transiciones

El [[Semáforo del Colaborador]] define 12 estados. A continuación se documentan las reglas de transición que gobiernan el ciclo de vida del colaborador.

### Progresión estándar

| Transición | Condición | Responsable |
|---|---|---|
| → Blanco | Al registrarse con sus datos, sin asignación aún | Sistema |
| Blanco → Verde manzana | Al ser asignado y asistir el Día 1 | [[Inspector]] (verifica en sitio) |
| Verde manzana → Azul claro | Al ponchar en la propiedad el tercer día | Sistema + [[Inspector]] (entrega uniforme) |
| Azul claro → Naranja | Al completar 7 días | Sistema (automático) |
| Naranja → Verde fuerte | Al quedar libre (fin de asignación fija o reincorporado) | Sistema |

### Disponibilidad y asignaciones

- **Amarillo (Disponible voluntario):** lo activa el propio colaborador **desde la app, sin aprobación de nadie**. Es autoservicio y el **único estado que el colaborador puede activar por sí mismo**.
- **Café (Asignación temporal):** la [[Reclutadora]] asigna temporalmente al colaborador y define la duración (días asignados) al momento de la asignación. El estado se cierra automáticamente al vencer esos días; al cerrarse, vuelve a Verde fuerte o Naranja según su estado previo.

### Stand-by (Rosa)

- El [[Hotel/Manager del Hotel|Manager del Hotel]] o el [[Hotel/Supervisor|Supervisor]] pueden poner a un colaborador en Rosa.
- Indica espera por decisión del hotel (vacaciones, temporada baja).
- La posición no tiene fecha de fin; termina cuando el Manager del Hotel o el Supervisor retira al colaborador del estado Rosa. Al salir, regresa a Verde fuerte.

## Reglas de incidencia

### Inasistencia (Morado)

- El sistema marca Morado cuando el colaborador no asiste sin justificación.
- Cada inasistencia se registra individualmente.

### Regla de 3 inasistencias

- 3 inasistencias acumuladas → [[Core/Módulos/Blacklist|Blacklist]] automático (estado Negro).
- Responsable: Sistema (no requiere acción manual).

### Reporte del hotel (Rojo)

- El [[Hotel/Manager del Hotel|Manager del Hotel]] activa el estado Rojo (reportado).
- El [[Inspector]] investiga el caso y resuelve hacia:
  - **Negro** ([[Core/Módulos/Blacklist|Blacklist]]), si la disputa es a favor del hotel.
  - **Verde fuerte** (reincorporado), si la disputa es a favor del colaborador.
- Los casos de Blacklist son revisados por el [[Manager de Reclutamiento]].

## Protección por Accidente Laboral (Gris)

- Cualquier estado activo → **Gris** cuando se genera un reporte de [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]].
- Mientras el colaborador esté en Gris, las inasistencias **no cuentan** para la regla de 3 inasistencias → Negro.
- **Gris → Verde fuerte** requiere: alta médica + cierre de tarjeta de accidente por el [[Inspector]].
- Referencia: [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]].

## Ponchado y Timesheet

> [!info] Las reglas de ponchado y deducción de Lunch también se documentan en [[Hotel/Reglas del Hotel|Reglas del Hotel]] desde la perspectiva del hotel.

### Mecanismo de ponchado

- El colaborador poncha vía **QR** generado por el [[Hotel/Manager del Hotel|Manager del Hotel]].
- Los ponches se registran por pares de entrada/salida para cada periodo (exactamente seis):
  - **Entrada** — inicio de jornada
  - **Salida Lunch** — sale a comer
  - **Entrada Lunch** — regresa de comer
  - **Salida Break** — sale a descanso
  - **Entrada Break** — regresa de descanso
  - **Salida** — fin de jornada
- El [[Timesheet]] se crea a partir del [[Core/Módulos/Schedule|Schedule]]; no puede existir de forma independiente.

### Deducción de Lunch

> [!important] Esta regla aplica a **todos** los colaboradores sin excepción, en cada jornada.

| Escenario | Deducción aplicada |
|---|---|
| Lunch < 30 min | 30 min (mínimo obligatorio) |
| Lunch ≥ 30 min | Tiempo real tomado |
| Sin ponche de Lunch | 30 min (auto-deducción) |

- **Horas brutas** = Salida − Entrada
- **Horas netas** = Horas brutas − Deducción de Lunch − Breaks reales
- Después de 6 horas continuas de trabajo, el colaborador debe tomar su lunch.

### Indicador de Lunch Extendido

- El sistema marca automáticamente a los colaboradores cuyo lunch excede 30 minutos.
- **Visible para:** [[Inspector]], [[Inspección/Coordinador|Coordinador]], [[Manager de Reclutamiento]].
- **No visible para:** [[Hotel/Manager del Hotel|Manager del Hotel]], [[Hotel/Supervisor|Supervisor]].
- Propósito: supervisión interna de Oranje; no es punitivo de forma automática.

## Elegibilidad y Pool

- Solo entran al [[Pool de Colaboradores]] los colaboradores que pasaron el filtro y fueron aprobados por Reclutamiento.
- La [[Reclutadora]] debe consultar la [[Core/Módulos/Blacklist|Blacklist]] antes de reclutar a un candidato.
- Colaborador aprobado ingresa al Pool con [[Semáforo del Colaborador]] en estado Blanco.

## Relacionado

- [[Semáforo del Colaborador]]
- [[Reglas de Negocio]]
- [[Pool de Colaboradores]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Timesheet]]
- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]]
- [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]]
- [[Reclutamiento/Flujo de Reclutamiento|Flujo de Reclutamiento]]
- [[Core/Módulos/Requisicion/Flujo de Requisición|Flujo de Requisición]]
- [[Reclutadora]]
- [[Manager de Reclutamiento]]
- [[Hotel/Manager del Hotel|Manager del Hotel]]
- [[Hotel/Supervisor|Supervisor]]
- [[Inspector]]
- [[Inspección/Coordinador|Coordinador]]
