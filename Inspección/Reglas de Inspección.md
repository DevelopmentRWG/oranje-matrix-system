---
tags:
  - modulo/inspeccion
aliases:
  - Reglas de Inspección
---

# Reglas de Inspección

Consolidación de todas las reglas de negocio que aplican al departamento de Inspección dentro del sistema Oranje. Referencia cruzada con [[Reglas de Negocio]] (concentrado general del sistema).

## Jerarquía del departamento

| Rol | Función |
|---|---|
| [[Inspección/Coordinador\|Coordinador]] | Jefe de los Inspectores. Enlace interdepartamental y escalamiento de casos especiales |
| [[Inspector]] | Ejecutor operativo en campo, asignado por zona geográfica |

## Asignación de zonas

- El [[Inspección/Coordinador\|Coordinador]] asigna Inspectores a las [[Core/Catálogos/Zonas|Zonas]] geográficas.
- A cada zona le corresponde un [[Inspector]] responsable.
- Zonas existentes: **Centro, Sur, Este, Oeste, Noroeste, Sureste**.
- Al autorizarse una requisición, el [[Inspector]] se asigna automáticamente en la cabecera según la zona del hotel.

> [!important] El [[Inspector]] de la zona del hotel es el responsable de darle seguimiento a cualquier disputa, accidente o verificación que ocurra en ese hotel.

## Verificación de llegada y entrega de uniforme

El [[Inspector]] participa en dos transiciones clave del [[Semáforo del Colaborador]]:

| Evento | Transición | Responsable |
|---|---|---|
| Verificación de llegada en sitio — Día 1 | Blanco → **Verde manzana** | [[Inspector]] (verifica en sitio) |
| Entrega de uniforme — Día 3 | Verde manzana → **Azul claro** | [[Inspector]] (entrega uniforme) + Sistema (ponche del colaborador) |

## Investigación de reportes (estado Rojo)

### Origen del estado Rojo

- El [[Hotel/Manager del Hotel\|Manager del Hotel]] activa el estado **Rojo** (Reportado) en el [[Semáforo del Colaborador]].
- La acumulación de 3 inasistencias **no** pasa por Rojo; va directo a **Negro** ([[Core/Módulos/Blacklist|Blacklist]]) de forma automática.

### Investigación y resolución

El [[Inspector]] investiga los casos de colaboradores en estado Rojo y emite el resultado:

| Resultado | Estado destino | Consecuencia |
|---|---|---|
| Disputa a favor del hotel | → **Negro** ([[Core/Módulos/Blacklist\|Blacklist]]) | Colaborador vetado del sistema |
| Disputa a favor del colaborador | → **Verde fuerte** | Colaborador reincorporado |

> [!note] Los casos de Blacklist resultantes son revisados por el [[Manager de Reclutamiento]]. El [[Inspector]] es el **único rol** que puede ejecutar la entrada manual a Blacklist.

## Accidente Laboral

El [[Inspector]] es el responsable final de la gestión de accidentes laborales en su zona.

### Escenario A — Colaborador reporta desde la app

1. El colaborador genera el reporte desde la app.
2. La señal llega **simultáneamente** al [[Hotel/Supervisor\|SUP]] y al [[Inspector]] de zona asignado.
3. Ambos acuden físicamente al lugar del incidente.

### Escenario B — Supervisor detecta primero

1. El [[Hotel/Supervisor\|SUP]] detecta el accidente en la propiedad.
2. Crea la tarjeta de accidente desde la app.
3. La señal llega al [[Inspector]] de zona.

### Seguimiento médico (Inspector)

El [[Inspector]] complementa la tarjeta de accidente con:

| Campo | Descripción |
|---|---|
| Traslado al centro médico | Si aplica, cuál centro |
| Diagnóstico recibido | Diagnóstico médico |
| Días de incapacidad | Cantidad de días |
| Observaciones médicas | Información adicional relevante |

### Cierre de tarjeta

> [!important] El [[Inspector]] es **siempre** el responsable final del cierre de la tarjeta de accidente.

- **Gris → Verde fuerte** requiere: alta médica + cierre de tarjeta de accidente por el [[Inspector]].
- Mientras el colaborador esté en estado **Gris**, las inasistencias **no cuentan** para la regla de 3 inasistencias → Blacklist.
- Tras el cierre, el colaborador queda disponible para reasignación.
- Referencia: [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]].

## Indicador de Lunch Extendido

- **Visible para:** [[Inspector]] y [[Inspección/Coordinador\|Coordinador]].
- **No visible para:** [[Hotel/Manager del Hotel\|Manager del Hotel]] ni [[Hotel/Supervisor\|Supervisor]].
- Muestra: colaborador, hotel, fecha, tiempo de lunch real.
- Se activa automáticamente cuando el tiempo de lunch excede 30 minutos.
- Propósito: supervisión interna de Oranje; no es punitivo de forma automática.

> [!info] También es visible para el [[Manager de Reclutamiento]]. Ver [[Reclutamiento/Reglas de Reclutamiento\|Reglas de Reclutamiento]].

## Supervisión del hotel activo

Una vez que el hotel alcanza el status **Naranja** en el [[Core/Módulos/Semáforos/Semáforo Onboarding\|Semáforo Onboarding]] (acuerdo firmado, hotel cliente activo), el [[Inspector]] figura como responsable operativo junto con las Reclutadoras.

## Supervisión de Calidad (QA)

- Un [[QA/Operador de QA\|Operador de QA]] está asignado de forma fija al departamento de Inspección.
- QA **no ejecuta** la operación de Inspección; solo observa, mide y retroalimenta.
- Si el [[Core/Módulos/Semáforos/Indicador de Calidad\|Indicador de Calidad]] del departamento alcanza estado **Rojo** sin mejora tras notificación, el Manager de QA escala a dirección.

## Resumen de responsabilidades por rol

| Acción | [[Inspector]] | [[Inspección/Coordinador\|Coordinador]] |
|---|---|---|
| Verificar llegada Día 1 | Sí | No |
| Entregar uniforme Día 3 | Sí | No |
| Investigar reportes (Rojo) | Sí | No |
| Ejecutar Blacklist manual | Sí | No |
| Recibir notificación de accidente | Sí | No |
| Complementar y cerrar tarjeta de accidente | Sí | No |
| Gestionar transición Gris → Verde fuerte | Sí | No |
| Ver Indicador de Lunch Extendido | Sí | Sí |
| Asignar Inspectores a zonas | No | Sí |
| Supervisar Inspectores | No | Sí |
| Enlace interdepartamental | No | Sí |
| Escalar casos especiales | No | Sí |

## Relacionado

- [[Reglas de Negocio]]
- [[Inspector]]
- [[Inspección/Coordinador|Coordinador]]
- [[Core/Catálogos/Zonas|Zonas]]
- [[Semáforo del Colaborador]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]]
- [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]]
- [[Timesheet]]
- [[Core/Módulos/Requisicion/Requisición|Requisición]]
- [[Core/Módulos/Requisicion/Flujo de Requisición|Flujo de Requisición]]
- [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Core/Módulos/Semáforos/Indicador de Calidad|Indicador de Calidad]]
- [[Manager de Reclutamiento]]
- [[Hotel/Manager del Hotel|Manager del Hotel]]
- [[Hotel/Supervisor|Supervisor]]
- [[Pool de Colaboradores]]
