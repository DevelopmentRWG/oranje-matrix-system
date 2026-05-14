---
tags:
  - simulación
  - módulo/reclutamiento
aliases:
  - Simulación de Reclutamiento
---

# Simulación de Reclutamiento

Narrativa operativa que recorre todos los procesos documentados del módulo de [[Reclutamiento/Reclutamiento|Reclutamiento]], desde la captación de candidatos hasta su entrada al sistema de pago. Cada acción referencia la regla de negocio que la respalda.

> [!info] Convenciones de la simulación
> - Los nombres de personas y hoteles son ficticios.
> - Las fechas están basadas en la semana del **lunes 19 de mayo al domingo 25 de mayo de 2026**.
> - Los números de requisición siguen el formato documentado en [[Core/Módulos/Requisicion/Flujo de Requisición|Flujo de Requisición]].
> - Cada transición de semáforo cita la regla correspondiente.

---

## Elenco de personajes

| Personaje | Rol | Módulo / Zona |
|---|---|---|
| Daniela Ríos | [[Reclutamiento/Reclutadora\|Reclutadora]] | Grupo A |
| Valeria Soto | [[Reclutamiento/Reclutadora\|Reclutadora]] | Grupo A |
| Lucía Méndez | [[Reclutamiento/Líder de Grupo de Reclutadoras\|Líder de Grupo]] | Grupo A |
| Fernando Ortiz | [[Reclutamiento/Manager de Reclutamiento\|Manager de Reclutamiento]] | Reclutamiento |
| Marco Duarte | [[Hotel/Supervisor\|Supervisor]] | Hotel Coral Bay · Zona Sur |
| Andrea Fuentes | [[Hotel/Manager de Área\|Manager de Área]] | Hotel Coral Bay · Zona Sur |
| Roberto Lara | [[Hotel/Manager General\|Manager General]] | Hotel Coral Bay · Zona Sur |
| Patricia Nava | [[Hotel/Supervisor\|Supervisor]] | Hotel Sierra Alta · Zona Centro |
| Carmen López | [[Hotel/Manager de Área\|Manager de Área]] | Hotel Sierra Alta · Zona Centro |
| Javier Torres | [[Inspección/Inspector\|Inspector]] | Zona Sur |
| Elena Rojas | [[Inspección/Inspector\|Inspector]] | Zona Centro |
| Sofía Cruz | Candidata nueva | — |
| Miguel Ángel Paredes | Candidato nuevo | — |
| Luis Gerardo Vega | Candidato en [[Core/Módulos/Blacklist\|Blacklist]] | — |
| Ana Belén Herrera | Colaboradora existente (Verde fuerte) | Zona Sur |
| Carlos Rivera | Colaborador existente (Amarillo) | Zona Centro |
| Diana Morales | Colaboradora existente (Naranja, fija) | Zona Sur |
| Pedro Jiménez | Colaborador existente (incidencia posterior) | Zona Sur |

---

## Estado inicial del sistema — Lunes 19 de mayo, 08:00

### Pool de Colaboradores

| Estado en [[Core/Módulos/Semáforos/Semáforo del Colaborador\|Semáforo del Colaborador]] | Cantidad | Ejemplo |
|---|---|---|
| Blanco (Pre-asignación) | 0 | — |
| Verde fuerte (Disponible) | 12 | Ana Belén Herrera + 11 más |
| Amarillo (Disponible voluntario) | 3 | Carlos Rivera + 2 más |
| Naranja (Fijo) | 8 | Diana Morales + 7 más |
| Rosa (Stand-by) | 2 | — |
| Café (Asignación temporal) | 1 | — |

### KPIs de la semana anterior

Todos dentro de meta según [[QA/Métricas y KPIs por Departamento|Métricas y KPIs por Departamento]].

| KPI | Meta | Resultado semana anterior |
|---|---|---|
| Cobertura total de requisiciones | ≥ 85% | 90% |
| Tiempo promedio de toma | ≤ 8h | 4h |
| Tasa de auto-asignación | ≤ 5% | 0% |
| Tasa de escalación | ≤ 10% | 5% |
| Consulta de Blacklist | 100% | 100% |
| Tasa de ingreso al Pool | ≥ 60% | 75% |

### Bandeja de requisiciones

Vacía. No hay requisiciones pendientes al inicio de la semana.

---

## Escenario A — Reclutamiento continuo (caso feliz)

**Protagonistas:** Daniela Ríos (Reclutadora) y Sofía Cruz (candidata nueva).

El [[Reclutamiento/Flujo de Reclutamiento|Flujo de Reclutamiento]] es continuo: siempre está activo, haya o no requisiciones abiertas.

### Lunes 19 mayo, 09:00 — Entrevista inicial (Fase 1)

Daniela recibe a Sofía Cruz como candidata. Antes de iniciar cualquier proceso:

1. Daniela **consulta la [[Core/Módulos/Blacklist|Blacklist]]** → Sofía **no aparece** (resultado negativo).

> [!important] Regla
> [[Reclutamiento/Reglas de Reclutamiento|Reglas de Reclutamiento]] — "La Reclutadora debe consultar la Blacklist antes de reclutar a cualquier candidato."

2. Daniela procede con la entrevista inicial y captura los datos de la Fase 1:

| Campo | Valor |
|---|---|
| Nombre completo | Sofía Cruz Mendoza |
| Edad | 24 años |
| Género | Femenino |
| Domicilio | Zona Sur |
| Teléfono | (555) 012-3456 |

> [!note] Regla
> [[Reclutamiento/Flujo de Reclutamiento|Flujo de Reclutamiento]] — Fase 1: Entrevista inicial. Responsable: Reclutadora.

### Lunes 19 mayo, 09:30 — Alta en la app (Fase 2)

Sofía descarga la app y completa sus datos:

| Campo | Valor | Catálogo |
|---|---|---|
| SSN | XXX-XX-1234 | — |
| ITIN | — | — |
| Posición | Housekeeper | [[Core/Catálogos/Posiciones\|Posiciones]] |
| Nivel de inglés | Intermedio | [[Core/Catálogos/Niveles de Inglés\|Niveles de Inglés]] |
| Nivel de experiencia | 2 años | — |
| Tipo de transporte | Auto propio | — |
| Modalidad | Tiempo completo | [[Core/Catálogos/Modalidades de Contratación\|Modalidades de Contratación]] |

> [!note] Regla
> [[Reclutamiento/Flujo de Reclutamiento|Flujo de Reclutamiento]] — Fase 2: Alta en la app. Responsable: el propio Colaborador.

### Lunes 19 mayo, 10:00 — Datos de emergencia (Fase 3)

Sofía completa desde la app:

| Campo | Valor |
|---|---|
| Contacto de emergencia | María Cruz (madre), (555) 098-7654 |
| Tipo de sangre | O+ |
| Alergias o condiciones | Ninguna |

> [!note] Regla
> [[Colaborador/Reglas del Colaborador|Reglas del Colaborador]] — Fase 3: Datos de emergencia. Responsable: el propio Colaborador desde la app.

### Lunes 19 mayo, 10:15 — Validación y aprobación (Fase 4)

Daniela revisa toda la información capturada en las tres fases. Todo es correcto.

- Daniela **aprueba** a Sofía Cruz.
- Habilita el acceso de Sofía a los paneles del sistema.
- **Sofía Cruz ingresa al [[Core/Módulos/Pool de Colaboradores|Pool de Colaboradores]].**

> [!note] Regla
> [[Reclutamiento/Flujo de Reclutamiento|Flujo de Reclutamiento]] — Fase 4: Validación, aprobación y habilitación. Responsable: Reclutadora.

**Transición de semáforo:**

```
Sofía Cruz: — → Blanco (Pre-asignación)
```

> [!note] Regla
> [[Core/Módulos/Semáforos/Semáforo del Colaborador|Semáforo del Colaborador]] — "Al ser aprobado e ingresar al Pool, el colaborador entra en estado Blanco."

---

## Escenario B — Candidato en Blacklist

**Protagonistas:** Daniela Ríos (Reclutadora) y Luis Gerardo Vega (candidato vetado).

### Lunes 19 mayo, 11:00 — Consulta de Blacklist (resultado positivo)

Luis Gerardo Vega se presenta como candidato. Daniela inicia el protocolo estándar:

1. **Consulta la [[Core/Módulos/Blacklist|Blacklist]]** → Luis Gerardo **aparece en estado Negro**.
   - Motivo registrado: 3 inasistencias (Blacklist automático por sistema).

> [!warning] Resultado
> Luis Gerardo Vega está en la Blacklist. El proceso se detiene. No es posible reclutarlo.

- Luis Gerardo no aparece en búsquedas activas de la [[Core/Módulos/Pool de Colaboradores|Pool de Colaboradores]].
- Su historial se conserva para consulta interna.

> [!important] Reglas
> - [[Core/Módulos/Blacklist|Blacklist]] — "3 inasistencias → Blacklist automático por sistema."
> - [[Core/Módulos/Blacklist|Blacklist]] — "Negro es PERMANENTE. No existe proceso de rehabilitación ni apelación."
> - [[Reclutamiento/Reglas de Reclutamiento|Reglas de Reclutamiento]] — "La Reclutadora debe consultar la Blacklist antes de reclutar."

**No hay transición de semáforo. El candidato no entra al sistema.**

---

## Escenario C — Self-Pick de requisición (cobertura 100%)

**Protagonistas:** Daniela Ríos (Reclutadora), Andrea Fuentes (GH Hotel Coral Bay), Marco Duarte (SUP).

### Lunes 19 mayo, 14:00 — Creación de requisición por el hotel

Marco Duarte (Supervisor) crea una requisición en el sistema:

| Campo | Valor |
|---|---|
| Número de requisición | `202605191400K3` |
| Hotel | Coral Bay |
| Zona | Sur |
| Estado | Verde manzana (En elaboración) |

Posición solicitada:

| Posición | Modalidad | Cantidad | Fecha de inicio | Preferencia de idioma |
|---|---|---|---|---|
| Housekeeper | Tiempo completo | 4 | Miércoles 21 de mayo | Intermedio |

> [!note] Regla
> [[Core/Módulos/Requisicion/Flujo de Requisición|Flujo de Requisición]] — "GM, GH o SUP crea la requisición con al menos una posición."

**Transiciones de semáforo:**

```
Requisición 202605191400K3: — → Verde manzana (En elaboración)
Posición Housekeeper x4:   — → Dorado (En preparación)
```

### Lunes 19 mayo, 14:30 — Autorización

Andrea Fuentes (Manager de Área) revisa y **autoriza** la requisición.

El sistema calcula la urgencia automáticamente:
- Fecha de autorización: 19 mayo, 14:30
- Fecha de inicio de la posición: 21 mayo
- Diferencia: ≈ 42 horas → **Rojo** (Urgente, < 72h)

El Inspector de la zona se asigna automáticamente: **Javier Torres** (Zona Sur).

> [!important] Reglas
> - [[Core/Módulos/Requisicion/Flujo de Requisición|Flujo de Requisición]] — "Solo GM o GH pueden autorizar; el SUP no puede."
> - [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición|Semáforo de Urgencia de Requisición]] — "< 72 horas = Rojo (Urgente)."
> - [[Core/Módulos/Requisicion/Flujo de Requisición|Flujo de Requisición]] — "Al autorizar, el Inspector de la zona del hotel se asigna automáticamente."

**Transiciones de semáforo:**

```
Requisición 202605191400K3: Verde manzana → Verde (Autorizada)
Posición Housekeeper x4:   Dorado → Naranja (Autorizada)
Urgencia:                  Rojo (< 72h)
```

### Lunes 19 mayo, 14:35 — Self-Pick

La requisición aparece en la bandeja compartida "Autorizadas", visible a todo el departamento de Reclutamiento. Está priorizada en la parte superior por su urgencia Roja.

Daniela Ríos la ve y **la toma** (primera en confirmar).

> [!note] Regla
> [[Reclutamiento/Self-Pick de Requisiciones|Self-Pick de Requisiciones]] — "Concurrencia: primera en confirmar gana. Si dos Reclutadoras toman la misma al mismo tiempo, el sistema la bloquea para la primera en confirmar."

**Transición de semáforo:**

```
Requisición 202605191400K3: Verde → Amarillo (En proceso)
```

### Lunes 19 mayo, 14:40 — Búsqueda en Pool y asignación

Daniela consulta el [[Core/Módulos/Schedule|Schedule]] del Hotel Coral Bay y busca en la [[Core/Módulos/Pool de Colaboradores|Pool de Colaboradores]] con los siguientes filtros:

| Filtro | Valor |
|---|---|
| Posición | Housekeeper |
| Zona | Sur |
| Idioma | Intermedio o superior |
| Disponibilidad | Verde fuerte o Blanco |

Resultados del match:

| # | Colaborador | Estado actual | Zona | Idioma |
|---|---|---|---|---|
| 1 | Ana Belén Herrera | Verde fuerte | Sur | Intermedio |
| 2 | Sofía Cruz | Blanco | Sur | Intermedio |
| 3 | Laura Estrada | Verde fuerte | Sur | Avanzado |
| 4 | Fernanda Ríos | Verde fuerte | Sur | Intermedio |

Daniela asigna a las 4 colaboradoras al Hotel Coral Bay y las registra en el [[Core/Módulos/Schedule|Schedule]].

> [!note] Regla
> [[Reclutamiento/Reclutadora|Reclutadora]] — "Asigna al colaborador al hotel y lo registra en su Schedule."

**Transiciones de semáforo:**

```
Posición Housekeeper x4:      Naranja → Verde (100% cubierta)
Requisición 202605191400K3:   Amarillo → Azul claro (Cubierta totalmente)
```

> [!important] Regla
> [[Core/Módulos/Semáforos/Semáforo de Posiciones de la Requisición|Semáforo de Posiciones de la Requisición]] — "Verde: 100% cubierta. Todos los colaboradores asignados confirmados."
> [[Core/Módulos/Semáforos/Semáforo de Requisición|Semáforo de Requisición]] — "Azul claro: Cubierta totalmente. Solo si TODAS las posiciones llegan a Verde."

---

## Escenario D — Progresión del colaborador + Inspección

**Protagonistas:** Sofía Cruz (colaboradora nueva), Javier Torres (Inspector Zona Sur).

Se narra la progresión de Sofía Cruz tras ser asignada al Hotel Coral Bay.

### Miércoles 21 mayo — Día 1: Verificación de llegada

Sofía Cruz se presenta en el Hotel Coral Bay a las 06:45.

**Javier Torres** (Inspector Zona Sur) se presenta en el hotel y verifica la llegada de Sofía y las demás colaboradoras nuevas asignadas.

**Transición de semáforo:**

```
Sofía Cruz: Blanco → Verde manzana (Día 1-2)
```

> [!note] Regla
> [[Core/Módulos/Semáforos/Semáforo del Colaborador|Semáforo del Colaborador]] — "Blanco → Verde manzana: al ser asignado y asistir el Día 1. El Inspector verifica su llegada en sitio."

Sofía poncha por primera vez vía QR generado por Andrea Fuentes (GH):

| Evento | Hora |
|---|---|
| Entrada | 07:00 |
| Salida Lunch | 12:00 |
| Entrada Lunch | 12:28 |
| Salida Break | 15:00 |
| Entrada Break | 15:15 |
| Salida | 15:30 |

Cálculo del día:
- Horas brutas: 8h 30min
- Lunch real: 28 min → deducción mínima de **30 min**
- Break: 15 min
- **Horas netas: 7h 45min**

> [!note] Regla
> [[Core/Módulos/Timesheet|Timesheet]] — "6 eventos de ponchado por jornada."
> [[Core/Módulos/Reglas de Negocio|Reglas de Negocio]] — "Deducción de lunch: mínimo 30 minutos siempre, incluso si se toma menos."

### Viernes 23 mayo — Día 3: Entrega de uniforme

Sofía poncha su tercer día consecutivo en el Hotel Coral Bay.

Javier Torres se presenta nuevamente y **entrega el uniforme** a Sofía Cruz.

**Transición de semáforo:**

```
Sofía Cruz: Verde manzana → Azul claro (Día 3+)
```

> [!note] Regla
> [[Core/Módulos/Semáforos/Semáforo del Colaborador|Semáforo del Colaborador]] — "Verde manzana → Azul claro: cuando poncha en la propiedad al tercer día. El Inspector le entrega su uniforme."

### Miércoles 28 mayo — Día 7: Fijo

Sofía completa 7 días en el Hotel Coral Bay. El sistema ejecuta la transición automáticamente.

**Transición de semáforo:**

```
Sofía Cruz: Azul claro → Naranja (Fijo)
```

> [!note] Regla
> [[Core/Módulos/Semáforos/Semáforo del Colaborador|Semáforo del Colaborador]] — "Azul claro → Naranja: al completar 7 días. Transición automática por sistema."

**Resumen de progresión de Sofía Cruz:**

```
— → Blanco → Verde manzana → Azul claro → Naranja
     (Pool)    (Día 1)         (Día 3)      (Día 7)
```

---

## Escenario E — Cobertura parcial + escalación por timeout

**Protagonistas:** Valeria Soto (Reclutadora), Lucía Méndez (Líder de Grupo), Patricia Nava (SUP Hotel Sierra Alta), Carmen López (GH).

### Martes 20 mayo, 10:00 — Creación de requisición con múltiples posiciones

Patricia Nava (Supervisor) crea una requisición para el Hotel Sierra Alta (Zona Centro):

| Campo | Valor |
|---|---|
| Número de requisición | `202605201000M7` |
| Hotel | Sierra Alta |
| Zona | Centro |

Posiciones solicitadas:

| Posición | Modalidad | Cantidad | Fecha de inicio |
|---|---|---|---|
| Housekeeper | Tiempo completo | 6 | Viernes 23 mayo |
| Houseman | Tiempo completo | 2 | Viernes 23 mayo |
| Chef | Tiempo completo | 1 | Sábado 24 mayo |

### Martes 20 mayo, 10:30 — Autorización

Carmen López (Manager de Área) autoriza la requisición.

Cálculo de urgencia por posición:
- Housekeeper y Houseman: 20 mayo 10:30 → 23 mayo = ≈ 62h → **Rojo** (< 72h)
- Chef: 20 mayo 10:30 → 24 mayo = ≈ 86h → **Amarillo** (72–120h)

Inspector asignado automáticamente: **Elena Rojas** (Zona Centro).

**Transiciones de semáforo:**

```
Requisición 202605201000M7:   Verde manzana → Verde (Autorizada)
Housekeeper x6:               Dorado → Naranja   | Urgencia: Rojo
Houseman x2:                  Dorado → Naranja   | Urgencia: Rojo
Chef x1:                      Dorado → Naranja   | Urgencia: Amarillo
```

### Martes 20 mayo, 10:35 — Self-Pick por Valeria

Valeria Soto toma la requisición de la bandeja compartida.

```
Requisición 202605201000M7: Verde → Amarillo (En proceso)
```

### Martes 20 mayo, 11:00 — Búsqueda en Pool (match parcial)

Valeria busca en la [[Core/Módulos/Pool de Colaboradores|Pool de Colaboradores]] filtrando por Zona Centro:

| Posición | Requeridos | Encontrados en Pool | Asignados | Cobertura |
|---|---|---|---|---|
| Housekeeper | 6 | 4 | 4 | 67% |
| Houseman | 2 | 2 | 2 | 100% |
| Chef | 1 | 0 | 0 | 0% |

Valeria asigna a los 6 colaboradores encontrados y **busca activamente fuera del sistema** (redes sociales, grupos de WhatsApp) para cubrir las 2 posiciones de Housekeeper y 1 de Chef faltantes.

> [!note] Regla
> [[Reclutamiento/Reglas de Reclutamiento|Reglas de Reclutamiento]] — "Si no hay match en Pool → busca activamente fuera del sistema (redes, grupos externos)."

**Transiciones de semáforo de posiciones:**

```
Housekeeper x6:   Naranja → Rojo (> 25% faltante: 4/6 = 67%)
Houseman x2:      Naranja → Verde (100%: 2/2)
Chef x1:          Naranja → Rojo (> 25% faltante: 0/1 = 0%)
```

### Miércoles 21 mayo, 10:35 — Escalación por timeout

Han pasado **24 horas** sin cubrir las posiciones pendientes. La urgencia de esas posiciones es **Rojo** (< 72h), por lo que el plazo de escalación es de **24 horas**.

El sistema escala a **Lucía Méndez** (Líder de Grupo).

> [!warning] Escalación activada
> Timeout de 24h sin cubrir posiciones con urgencia Roja.

> [!important] Regla
> [[Reclutamiento/Self-Pick de Requisiciones|Self-Pick de Requisiciones]] — Tabla de escalación:
> - Rojo (< 72h): 24h sin cubrir → escala al Líder de Grupo.
> - Amarillo (72–120h): 48h sin cubrir.
> - Verde fuerte (> 120h): 72h sin cubrir.

La requisición permanece en **Amarillo** (En proceso) durante toda la escalación.

### Miércoles 21 mayo – Viernes 23 mayo — Lucía asume la búsqueda

Lucía Méndez asume la búsqueda. Logra reclutar 1 Housekeeper adicional a través de un grupo externo (Miguel Ángel Paredes, que pasa por las 4 fases del [[Reclutamiento/Flujo de Reclutamiento|Flujo de Reclutamiento]] y entra al Pool en Blanco antes de ser asignado).

Estado actualizado de posiciones al cierre del viernes 23:

| Posición | Asignados / Requeridos | Cobertura | Estado |
|---|---|---|---|
| Housekeeper | 5 / 6 | 83% | Amarillo (≤ 25% faltante) |
| Houseman | 2 / 2 | 100% | Verde |
| Chef | 0 / 1 | 0% | Rojo (> 25% faltante) |

**La requisición cierra en estado Rojo** (Cubierta parcialmente) porque al menos una posición (Chef) no llegó a Verde.

> [!important] Regla
> [[Core/Módulos/Semáforos/Semáforo de Requisición|Semáforo de Requisición]] — "Rojo: Cubierta parcialmente. La requisición solo cierra en Azul claro si TODAS las posiciones llegan a Verde."

**Transiciones de semáforo finales:**

```
Requisición 202605201000M7:   Amarillo → Rojo (Cubierta parcialmente)
Housekeeper x6:               Rojo → Amarillo (5/6)
Houseman x2:                  Verde (sin cambio)
Chef x1:                      Rojo (sin cambio, 0/1)
```

---

## Escenario F — Auto-asignación por sistema

### Martes 20 mayo, 16:00 — Requisición sin tomar

Hotel Coral Bay crea otra requisición:

| Campo | Valor |
|---|---|
| Número de requisición | `202605201600P2` |
| Posición | Houseman x2 |
| Fecha de inicio | Lunes 26 mayo |

Andrea Fuentes (GH) la autoriza a las 16:00.

Urgencia: 20 mayo 16:00 → 26 mayo = ≈ 152h → **Verde fuerte** (Normal, > 120h).

La requisición queda en la bandeja compartida. Ninguna Reclutadora la toma — todas están enfocadas en las requisiciones con urgencia Roja.

```
Requisición 202605201600P2: — → Verde manzana → Verde (Autorizada)
```

### Miércoles 21 mayo, 16:00 — Auto-asignación

Han pasado exactamente **24 horas** desde la autorización sin que nadie tome la requisición.

El sistema la asigna automáticamente a la Reclutadora con **menor carga de requisiciones activas**:
- Valeria Soto: 1 requisición activa
- Daniela Ríos: 2 requisiciones activas
- → Se asigna a **Valeria Soto**.

> [!important] Reglas
> - [[Reclutamiento/Self-Pick de Requisiciones|Self-Pick de Requisiciones]] — "Si una requisición lleva más de 24 horas sin ser tomada, el sistema la asigna automáticamente a la Reclutadora con menor carga."
> - [[Reclutamiento/Reglas de Reclutamiento|Reglas de Reclutamiento]] — "El Manager de Reclutamiento no recibe notificación; el proceso es transparente."

**Transición de semáforo:**

```
Requisición 202605201600P2: Verde → Amarillo (En proceso, auto-asignada)
```

Valeria cubre la requisición con 2 colaboradores del Pool en Verde fuerte. La requisición cierra en **Azul claro**.

---

## Escenario G — Asignación temporal (Café)

**Protagonistas:** Daniela Ríos, Carlos Rivera (colaborador en Amarillo), Diana Morales (colaboradora en Naranja).

### Jueves 22 mayo, 07:30 — Inasistencia de Diana Morales

Diana Morales (Housekeeper fija en Hotel Coral Bay, estado Naranja) no se presenta a trabajar. El sistema la marca como **Morado** (No regresó).

> [!note] Regla
> [[Core/Módulos/Semáforos/Semáforo del Colaborador|Semáforo del Colaborador]] — "Morado: el sistema lo marca cuando el colaborador no asiste sin justificación."

El Hotel Coral Bay necesita cubrir esa posición temporalmente.

### Jueves 22 mayo, 08:00 — Búsqueda de reemplazo temporal

Daniela busca en la Pool colaboradores disponibles para asignación temporal:
- Carlos Rivera está en estado **Amarillo** (Disponible voluntario).
  - Carlos activó este estado él mismo desde la app durante su periodo de descanso del Hotel Sierra Alta.

> [!note] Regla
> [[Core/Módulos/Semáforos/Semáforo del Colaborador|Semáforo del Colaborador]] — "Amarillo: lo activa el propio colaborador desde la app. Es el único estado de autoservicio, sin aprobación de nadie."

### Jueves 22 mayo, 08:15 — Asignación temporal

Daniela asigna a Carlos Rivera **temporalmente** al Hotel Coral Bay por **3 días** (jueves 22, viernes 23 y sábado 24).

**Transición de semáforo:**

```
Carlos Rivera: Amarillo → Café (Asignación temporal, 3 días)
```

> [!note] Regla
> [[Core/Módulos/Semáforos/Semáforo del Colaborador|Semáforo del Colaborador]] — "Amarillo → Café: la Reclutadora lo asigna temporalmente con duración definida en días."

Efectos de la asignación:
- Se genera [[Core/Módulos/Schedule|Schedule]] para Carlos en Hotel Coral Bay.
- El Schedule genera [[Core/Módulos/Timesheet|Timesheet]].
- Carlos **puede ponchar**.

> [!important] Regla
> [[Colaborador/Reglas del Colaborador|Reglas del Colaborador]] — "Sin asignación activa no hay Schedule; sin Schedule no hay Timesheet; sin Timesheet no es posible ponchar."

### Domingo 25 mayo — Fin de asignación temporal

Vencen los 3 días asignados. Carlos Rivera **no** ha terminado su periodo de descanso del Hotel Sierra Alta.

**Transición de semáforo:**

```
Carlos Rivera: Café → Amarillo (regresa porque sigue en periodo de descanso)
```

> [!note] Regla
> [[Core/Módulos/Semáforos/Semáforo del Colaborador|Semáforo del Colaborador]] — "Al vencer los días asignados: regresa a Amarillo si sigue en periodo de descanso, o a Verde fuerte si ya no."

---

## Escenario H — Incidencias: no regresó + reportado

### Caso 1: Diana Morales — 3 inasistencias → Blacklist

**Jueves 22 mayo** — Diana no se presentó (1.ª inasistencia). Sistema la marca **Morado**.

**Viernes 23 mayo** — Diana no se presenta de nuevo (2.ª inasistencia). Se mantiene en **Morado**.

**Lunes 26 mayo** — Diana no se presenta por tercera vez (3.ª inasistencia).

> [!warning] Blacklist automático
> 3 inasistencias acumuladas → el sistema ejecuta la transición a **Negro** (Blacklist) de forma automática.

**Transición de semáforo:**

```
Diana Morales: Naranja → Morado (1.ª) → Morado (2.ª) → Morado (3.ª) → Negro (Blacklist)
```

> [!important] Reglas
> - [[Core/Módulos/Blacklist|Blacklist]] — "3 inasistencias → Blacklist automático por sistema."
> - [[Core/Módulos/Blacklist|Blacklist]] — "Negro es PERMANENTE. No existe proceso de rehabilitación ni apelación."
> - [[Core/Módulos/Semáforos/Semáforo del Colaborador|Semáforo del Colaborador]] — "Negro: colaborador bloqueado. No aparece en búsquedas activas. Historial conservado."

Fernando Ortiz (Manager de Reclutamiento) **revisa el caso de Blacklist** como parte de su función de supervisión.

> [!note] Regla
> [[Reclutamiento/Manager de Reclutamiento|Manager de Reclutamiento]] — "Revisar casos de Blacklist: responsabilidad del Manager de Reclutamiento."

### Caso 2: Pedro Jiménez — Reportado por el hotel

**Viernes 23 mayo** — Andrea Fuentes (GH del Hotel Coral Bay) **reporta** a Pedro Jiménez por conducta inapropiada.

**Transición de semáforo:**

```
Pedro Jiménez: [estado previo] → Rojo (Reportado)
```

> [!note] Regla
> [[Core/Módulos/Semáforos/Semáforo del Colaborador|Semáforo del Colaborador]] — "Rojo: lo pone el hotel (GM, GH o SUP). El Inspector investiga y resuelve."

**Investigación del Inspector:**

Javier Torres (Inspector Zona Sur) investiga el caso. Entrevista a Pedro, al Supervisor del hotel y revisa los registros.

**Resultado:** la disputa se resuelve **a favor del colaborador**. No hubo conducta inapropiada, fue un malentendido.

**Transición de semáforo:**

```
Pedro Jiménez: Rojo → Verde fuerte (Reincorporado)
```

> [!important] Regla
> [[Core/Módulos/Semáforos/Semáforo del Colaborador|Semáforo del Colaborador]] — "Disputa resuelta a favor del colaborador → regresa a Verde fuerte."
> [[Inspección/Inspector|Inspector]] — "El Inspector tiene autoridad propia para resolver la disputa, sin validación del Manager de Reclutamiento."

---

## Entrada al sistema de pago

Se narra cómo la semana laboral de Sofía Cruz y Carlos Rivera llega al sistema de pago.

### Domingo 25 mayo — Cierre de semana

El sistema genera automáticamente el [[Contabilidad/Consolidado Semanal del Colaborador|Consolidado Semanal]] para cada colaborador que tuvo actividad durante la semana.

#### Sofía Cruz (1 hotel)

| Campo | Valor |
|---|---|
| Hotel | Coral Bay |
| Días trabajados | 5 (miércoles 21 – domingo 25) |
| Horas brutas | 40h |
| Deducción lunch | 2.5h (30 min × 5 jornadas) |
| Horas netas | 37.5h |
| Pay rate | Según [[Core/Módulos/Contrato|Contrato]] del Hotel Coral Bay |

> [!note] Nota
> Sofía ingresó a media semana (miércoles 21). El sistema prorratea automáticamente: los días previos al alta (lunes 19 y martes 20) se marcan en Gris en el [[Core/Módulos/Semáforos/Indicador de Cumplimiento del Timesheet|Indicador de Cumplimiento del Timesheet]].

> [!note] Regla
> [[Core/Módulos/Reglas de Negocio|Reglas de Negocio]] — "Ingreso a media semana: el sistema prorratea automáticamente los días restantes del ciclo; los días previos al alta se marcan en Gris."

#### Carlos Rivera (2 hoteles)

Carlos trabajó en 2 hoteles durante la semana:

| Hotel | Días | Horas netas | Pay rate |
|---|---|---|---|
| Sierra Alta (antes de descanso) | 2 | 15h | Según contrato Sierra Alta |
| Coral Bay (asignación temporal) | 3 | 22.5h | Según contrato Coral Bay |

El overtime se calcula **por hotel**, no de forma global:
- Sierra Alta: 15h (no excede 40h → sin overtime)
- Coral Bay: 22.5h (no excede 40h → sin overtime)

> [!important] Regla
> [[Contabilidad/Consolidado Semanal del Colaborador|Consolidado Semanal del Colaborador]] — "El overtime se calcula por hotel según política de cada contrato."

### Lunes 26 mayo — Pre-Payroll

El sistema genera el Pre-Payroll aplicando:
- Pay rate del [[Core/Módulos/Contrato|Contrato]] de cada hotel.
- [[Contabilidad/Deducciones|Deducciones]] activas del colaborador (uniforme, comida, retención del 16%).

> [!note] Regla
> [[Contabilidad/Flujo de Nómina|Flujo de Nómina]] — Paso 2: "Cálculo del Pre-Payroll: aplica pay rate, deducciones activas, overtime autorizado."

### Martes 27 mayo — Validación por Contabilidad

La [[Contadora]] revisa y el [[Manager de Contabilidad]] aprueba el Pre-Payroll.

> [!note] Regla
> [[Contabilidad/Flujo de Nómina|Flujo de Nómina]] — Paso 3: "Validación del Pre-Payroll por Contabilidad. Requiere aprobación."

### Miércoles 28 mayo — Pago ejecutado

Se libera la nómina y se ejecuta el pago.

> [!note] Regla
> [[Contabilidad/Flujo de Nómina|Flujo de Nómina]] — Paso 7: "Autorización final y ejecución del pago."

---

## Resumen consolidado de transiciones de semáforo

| Entidad | Semáforo | Transición | Día | Regla fuente |
|---|---|---|---|---|
| Sofía Cruz | Colaborador | — → Blanco | Lun 19 | [[Reclutamiento/Flujo de Reclutamiento\|Flujo de Reclutamiento]] |
| Sofía Cruz | Colaborador | Blanco → Verde manzana | Mié 21 | [[Core/Módulos/Semáforos/Semáforo del Colaborador\|Semáforo del Colaborador]] |
| Sofía Cruz | Colaborador | Verde manzana → Azul claro | Vie 23 | [[Core/Módulos/Semáforos/Semáforo del Colaborador\|Semáforo del Colaborador]] |
| Sofía Cruz | Colaborador | Azul claro → Naranja | Mié 28 | [[Core/Módulos/Semáforos/Semáforo del Colaborador\|Semáforo del Colaborador]] |
| REQ 202605191400K3 | Requisición | Vm → V → Am → Ac | Lun 19 | [[Core/Módulos/Semáforos/Semáforo de Requisición\|Semáforo de Requisición]] |
| REQ 202605191400K3 | Urgencia | Rojo | Lun 19 | [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición\|Semáforo de Urgencia]] |
| REQ 202605201000M7 | Requisición | Vm → V → Am → Rojo | Mar 20 – Vie 23 | [[Core/Módulos/Semáforos/Semáforo de Requisición\|Semáforo de Requisición]] |
| REQ 202605201600P2 | Requisición | V → Am (auto) → Ac | Mar – Mié | [[Reclutamiento/Self-Pick de Requisiciones\|Self-Pick]] |
| Carlos Rivera | Colaborador | Am → Café → Am | Jue 22 – Dom 25 | [[Core/Módulos/Semáforos/Semáforo del Colaborador\|Semáforo del Colaborador]] |
| Diana Morales | Colaborador | Na → Mo ×3 → Negro | Jue 22 – Lun 26 | [[Core/Módulos/Blacklist\|Blacklist]] |
| Pedro Jiménez | Colaborador | [previo] → Rojo → Vf | Vie 23 – Lun 26 | [[Core/Módulos/Semáforos/Semáforo del Colaborador\|Semáforo del Colaborador]] |
| Luis G. Vega | Blacklist | Consulta: Negro (bloqueado) | Lun 19 | [[Core/Módulos/Blacklist\|Blacklist]] |

**Abreviaturas:** Vm = Verde manzana, V = Verde, Am = Amarillo, Ac = Azul claro, Na = Naranja, Mo = Morado, Vf = Verde fuerte.

---

## Verificación contra KPIs de QA

Evaluación de la semana simulada según [[QA/Métricas y KPIs por Departamento|Métricas y KPIs por Departamento]]:

| # | KPI | Meta | Resultado | Estado |
|---|---|---|---|---|
| 1 | Cobertura total de requisiciones (Azul claro / cerradas) | ≥ 85% | 2 de 3 = 67% | Crítico (< 70%) |
| 2 | Tiempo promedio de toma de requisición | ≤ 8h | ≈ 3h promedio | En meta |
| 3 | Tasa de auto-asignación por timeout | ≤ 5% | 1 de 3 = 33% | Crítico (> 15%) |
| 4 | Tasa de escalación por timeout al Líder | ≤ 10% | 1 de 3 = 33% | Crítico (> 20%) |
| 5 | Cumplimiento de consulta de Blacklist | 100% | 2 de 2 = 100% | En meta |
| 6 | Tasa de ingreso al Pool (aprobados / entrevistados) | ≥ 60% | 2 de 3 = 67% | En meta |

> [!warning] Nota sobre los resultados
> Los KPIs 1, 3 y 4 están fuera de meta intencionalmente. La simulación incluye escenarios adversos (cobertura parcial, auto-asignación, escalación) para demostrar cómo operan estos mecanismos. En una semana operativa normal, estos indicadores deberían estar dentro de meta.

---

## Relacionado

- [[Reclutamiento/Reclutamiento|Reclutamiento]]
- [[Reclutamiento/Flujo de Reclutamiento|Flujo de Reclutamiento]]
- [[Reclutamiento/Self-Pick de Requisiciones|Self-Pick de Requisiciones]]
- [[Reclutamiento/Reglas de Reclutamiento|Reglas de Reclutamiento]]
- [[Core/Módulos/Requisicion/Flujo de Requisición|Flujo de Requisición]]
- [[Core/Módulos/Semáforos/Semáforo del Colaborador|Semáforo del Colaborador]]
- [[Core/Módulos/Semáforos/Semáforo de Requisición|Semáforo de Requisición]]
- [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición|Semáforo de Urgencia de Requisición]]
- [[Core/Módulos/Semáforos/Semáforo de Posiciones de la Requisición|Semáforo de Posiciones de la Requisición]]
- [[Core/Módulos/Pool de Colaboradores|Pool de Colaboradores]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[QA/Métricas y KPIs por Departamento|Métricas y KPIs por Departamento]]
- [[Contabilidad/Flujo de Nómina|Flujo de Nómina]]
- [[Contabilidad/Consolidado Semanal del Colaborador|Consolidado Semanal del Colaborador]]

---

## Simulaciones relacionadas

- [[Simulación - Punto de Vista del Hotel]] — Muestra el ciclo completo del hotel como cliente, incluyendo la creación de requisiciones que Reclutamiento atiende.
- [[Simulación - Punto de Vista de Ventas]] — Narra cómo los hoteles llegan a status Naranja, habilitando las requisiciones que inician el flujo de reclutamiento.
- [[Simulación - Punto de Vista de Inspección]] — Detalla la verificación de campo (Día 1, Día 3) que el Inspector realiza sobre los colaboradores que Reclutamiento asigna.
- [[Simulación - Ciclo de Vida del Colaborador]] — Recorre todos los estados del colaborador desde su ingreso al Pool hasta Blacklist, cruzando con los procesos de asignación aquí narrados.
