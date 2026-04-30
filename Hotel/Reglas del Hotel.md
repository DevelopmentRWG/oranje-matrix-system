---
tags:
  - modulo/hotel
aliases:
  - Reglas del Hotel
---

# Reglas del Hotel

Consolidación de todas las reglas de negocio que aplican a los roles del Hotel dentro del sistema Oranje. Referencia cruzada con [[Reglas de Negocio]] (concentrado general del sistema).

## Jerarquías soportadas

La plataforma soporta dos modelos organizacionales para el hotel:

| Jerarquía | Estructura |
|---|---|
| **Simple** | [[Hotel/Manager del Hotel\|Manager del Hotel]] → [[Hotel/Supervisor\|SUP]] → Colaboradores de Oranje |
| **Extendida** | [[Hotel/Manager General\|Manager General]] → Gerente de Departamento → [[Hotel/Supervisor\|Supervisor]] → Colaboradores de Oranje |

- En la jerarquía extendida, el **Gerente de Departamento** tiene las mismas responsabilidades de plataforma que el [[Hotel/Manager del Hotel|Manager del Hotel]].
- Los departamentos del hotel son: **Housekeeping, Alimentos, Mantenimiento y Front Desk** (ver [[Core/Catálogos/Departamentos del Hotel|Departamentos del Hotel]]).
- En la jerarquía extendida, cada departamento tiene su propio Gerente y Supervisor(es).

## Habilitación del hotel

> [!important] El hotel solo puede generar requisiciones cuando alcanza el status **Naranja** en el [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]].

- Antes de alcanzar Naranja, el hotel es un prospecto comercial gestionado por Ventas.

## Requisiciones — creación y autorización

### Acceso al módulo

- Solo el [[Hotel/Manager del Hotel|Manager del Hotel]] y el [[Hotel/Supervisor|Supervisor]] tienen acceso al módulo de requisiciones.
- Usuarios sin acceso reciben el mensaje: **"No cuenta con acceso"**.

### Creación (Supervisor)

- El [[Hotel/Supervisor|Supervisor]] crea la requisición (estado **Verde manzana** — En elaboración en el [[Core/Módulos/Semáforos/Semáforo de Requisición|Semáforo de Requisición]]).
- El número de requisición se genera automáticamente: `Año (4) + Mes (2) + Día (2) + Hora (2, 24h) + Minutos (2) + Homoclave (2 alfanuméricos)`. Ejemplo: `202604081632V1`.

### Autorización (Manager del Hotel)

> [!important] **Solo** el [[Hotel/Manager del Hotel|Manager del Hotel]] puede autorizar una requisición. Si el [[Hotel/Supervisor|Supervisor]] intenta hacerlo, el sistema bloquea la acción con el mensaje: **"Solo el gerente del hotel puede autorizar la requisición"**.

- Para autorizar debe existir **al menos una posición** registrada. Si no: **"No tiene posiciones registradas, registre al menos una posición e intente nuevamente"**.
- El rechazo regresa la requisición al [[Hotel/Supervisor|Supervisor]] con observaciones (estado **En elaboración**).

> [!info] La autorización del [[Hotel/Manager del Hotel|Manager del Hotel]] es una **capa de seguridad** para evitar que lleguen requisiciones falsas o incorrectas a Reclutamiento.

## Efectos automáticos al autorizar

Al autorizar una requisición, el sistema ejecuta automáticamente:

| Efecto | Detalle |
|---|---|
| Cálculo de urgencia | Por posición, según la [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición\|fórmula de urgencia]]: `> 120h` → Verde fuerte (Normal), `72–120h` → Amarillo (Medio), `< 72h` → Rojo (Urgente) |
| Transición de posiciones | De Dorado (Gold) a Naranja (Orange) en el [[Core/Módulos/Semáforos/Semáforo de Posiciones de la Requisición\|Semáforo de Posiciones]] |
| Reflejo en Schedule | Las posiciones quedan en el [[Core/Módulos/Schedule\|Schedule]] de la semana correspondiente a su fecha de inicio |
| Asignación de Inspector | El [[Inspector]] se asigna automáticamente según la zona del hotel |

## Ciclo de vida de la posición

- Cada posición tiene **fecha de inicio pero no fecha de fin** definida.
- La posición termina cuando el [[Hotel/Manager del Hotel|Manager del Hotel]] pone al colaborador en **Stand-by** (estado Rosa en el [[Semáforo del Colaborador]]).

## Eliminación de requisición

- Al confirmar la eliminación, el sistema muestra: **"Al confirmar la eliminación de la requisición, las posiciones registradas y la requisición serán eliminadas físicamente"**.
- El estado **Morado** es transversal: se alcanza desde cualquier estado cuando se elimina la requisición.
- Si una requisición no tiene posiciones al salir del editor → **eliminación física automática**.
- Al eliminar una requisición con posiciones → cada posición también pasa a Morado con journal individual.

## Gestión de personal asignado

Responsabilidades exclusivas del [[Hotel/Manager del Hotel|Manager del Hotel]] sobre los colaboradores asignados:

| Acción | Efecto en [[Semáforo del Colaborador]] | Descripción |
|---|---|---|
| Generar código QR | — | Permite a los colaboradores ponchar en el [[Timesheet]] |
| Poner en Stand-by | → **Rosa** | Espera por decisión del hotel (vacaciones, temporada baja). Sin fecha de fin; termina cuando el Manager del Hotel o el Supervisor cambia el estado |
| Reportar colaborador | → **Rojo** | Inicia investigación por parte del [[Inspector]] |
| Gestionar Schedule semanal | — | Administra las asignaciones del [[Core/Módulos/Schedule\|Schedule]] del hotel |

> [!important] El [[Hotel/Manager del Hotel|Manager del Hotel]] o el [[Hotel/Supervisor|Supervisor]] pueden poner a un colaborador en estado Rosa (Stand-by).

## Timesheet y deducción de Lunch

> [!info] Las reglas de ponchado y deducción de Lunch también se documentan en [[Colaborador/Reglas del Colaborador|Reglas del Colaborador]] desde la perspectiva del colaborador.

### Dependencia

- El [[Timesheet]] se crea a partir del [[Core/Módulos/Schedule|Schedule]]; no puede existir de forma independiente.
- La semana del hotel está definida por el contrato (inicio y fin de semana).

### Ponchado

- El colaborador poncha vía **QR** generado por el [[Hotel/Manager del Hotel|Manager del Hotel]].
- Los ponches se registran por pares de entrada/salida para cada periodo (exactamente seis):
  - **Entrada** — inicio de jornada
  - **Salida Lunch** — sale a comer
  - **Entrada Lunch** — regresa de comer
  - **Salida Break** — sale a descanso
  - **Entrada Break** — regresa de descanso
  - **Salida** — fin de jornada

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

## Indicador de Lunch Extendido

> [!note] El [[Hotel/Manager del Hotel|Manager del Hotel]] y el [[Hotel/Supervisor|Supervisor]] **no tienen acceso** al Indicador de Lunch Extendido. Es exclusivo de roles internos de Oranje ([[Inspector]], [[Inspección/Coordinador|Coordinador]], [[Manager de Reclutamiento]]).

## Accidente Laboral — responsabilidades del Supervisor

El [[Hotel/Supervisor|Supervisor]] tiene un rol activo en el reporte y captura de accidentes laborales:

### Escenario A — Colaborador reporta desde la app

1. El colaborador genera el reporte desde la app.
2. La señal llega **simultáneamente** al [[Hotel/Supervisor|SUP]] y al [[Inspector]] de zona asignado.
3. El SUP acude físicamente y captura: ubicación exacta, circunstancias, testigos y atención inmediata brindada.

### Escenario B — Supervisor detecta primero

1. El [[Hotel/Supervisor|SUP]] detecta el accidente en la propiedad.
2. Crea la tarjeta de accidente desde la app.
3. La señal llega al [[Inspector]] de zona.

- En ambos escenarios, el colaborador pasa a estado **Gris** en el [[Semáforo del Colaborador]] (protección contra la regla de 3 inasistencias).
- Referencia: [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]].

## Manager General (jerarquía extendida)

El [[Hotel/Manager General|Manager General]] es la máxima autoridad del hotel en la jerarquía extendida:

- Tiene **visibilidad global** del [[Core/Módulos/Schedule|Schedule]] y [[Timesheet]] de todos los departamentos.
- **No aprueba requisiciones** directamente; esa responsabilidad recae en los Gerentes de Departamento.

## Resumen de responsabilidades por rol

| Acción | [[Hotel/Manager del Hotel\|Manager del Hotel]] | [[Hotel/Supervisor\|Supervisor]] | [[Hotel/Manager General\|Manager General]] |
|---|---|---|---|
| Crear requisición | No | Sí | No |
| Autorizar requisición | Sí (exclusivo) | No | No (Gerente Depto.) |
| Rechazar requisición con observaciones | Sí | No | No |
| Generar QR para ponchado | Sí | — | — |
| Poner en Stand-by (Rosa) | Sí | Sí | No |
| Reportar colaborador (Rojo) | Sí | — | — |
| Gestionar Schedule semanal | Sí | — | Visibilidad global |
| Reportar accidente laboral | — | Sí | No |
| Ver Indicador de Lunch Extendido | No | No | No |
| Visibilidad global Schedule/Timesheet | No | No | Sí |

> [!info] En la jerarquía extendida, el **Gerente de Departamento** hereda las responsabilidades de plataforma del [[Hotel/Manager del Hotel|Manager del Hotel]] para su departamento.

## Relacionado

- [[Reglas de Negocio]]
- [[Hotel/Manager del Hotel|Manager del Hotel]]
- [[Hotel/Supervisor|Supervisor]]
- [[Hotel/Manager General|Manager General]]
- [[Core/Módulos/Requisicion/Flujo de Requisición|Flujo de Requisición]]
- [[Core/Módulos/Semáforos/Semáforo de Requisición|Semáforo de Requisición]]
- [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición|Semáforo de Urgencia de Requisición]]
- [[Core/Módulos/Semáforos/Semáforo de Posiciones de la Requisición|Semáforo de Posiciones de la Requisición]]
- [[Semáforo del Colaborador]]
- [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Timesheet]]
- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]]
- [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Core/Catálogos/Departamentos del Hotel|Departamentos del Hotel]]
- [[Pool de Colaboradores]]
