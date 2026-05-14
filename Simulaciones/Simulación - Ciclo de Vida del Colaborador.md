---
tags:
  - simulación
  - módulo/colaborador
aliases:
  - Simulación del Colaborador
  - Ciclo de Vida Completo
---

# Simulación — Ciclo de Vida del Colaborador

Este documento recorre todos los estados del [[Semáforo del Colaborador]] a través de la historia de un colaborador ficticio: Carlos Méndez. Cada acción, transición y regla de negocio respeta fielmente la documentación del vault. Cada wikilink apunta a un módulo real documentado en el sistema.

> [!info] Nota sobre wikilinks
> Todos los wikilinks de este documento apuntan a notas reales del vault. Si algún enlace aparece en color de "no resuelto", verifica que la nota correspondiente exista en su ruta esperada.

## Perfil del colaborador

| Campo | Valor |
|---|---|
| Nombre | Carlos Méndez |
| Edad | 28 años |
| Género | Masculino |
| Domicilio | Zona Centro |
| Teléfono | (555) 123-4567 |
| Posición | Housekeeper |
| Nivel de inglés | Intermedio |
| Experiencia | 2 años |
| Transporte | Vehículo propio |
| Modalidad | Tiempo completo |
| SSN/TaxID | No tiene al inicio |
| Tipo de sangre | O+ |
| Alergias | Ninguna |
| Contacto de emergencia | María Méndez (madre) |

---

## Acto 1 — Ingreso al sistema

**Semáforo: ⚪ Blanco — Pre-asignación**

### Fase 1 — Entrevista inicial

La [[Reclutadora]] contacta a Carlos tras identificarlo como candidato viable. Durante la entrevista inicial, captura los datos básicos: nombre, edad, género, domicilio y teléfono. Esta etapa corresponde al inicio del [[Flujo de Reclutamiento]].

### Fase 2 — Alta en la app

Carlos completa su perfil directamente desde la app de Oranje. Registra los siguientes datos:

- SSN: no tiene
- ITIN: no tiene
- Posición: [[Posiciones|Housekeeper]]
- Nivel de inglés: [[Niveles de Inglés|Intermedio]]
- Nivel de experiencia: 2 años
- Tipo de transporte: vehículo propio
- Modalidad: [[Modalidades de Contratación|Tiempo completo]]

### Fase 3 — Datos de emergencia

Carlos completa la sección de datos de emergencia y salud:

- Contacto de emergencia: María Méndez (madre)
- Tipo de sangre: O+
- Alergias: ninguna

### Fase 4 — Validación y aprobación

La [[Reclutadora]] revisa el perfil de Carlos, lo aprueba y habilita su acceso a los paneles del sistema. Antes de proceder, consulta la [[Blacklist]] — Carlos no aparece registrado.

Carlos ingresa al [[Pool de Colaboradores]] con semáforo en **⚪ Blanco**.

> [!warning] Regla
> La [[Reclutadora]] debe consultar la [[Blacklist]] antes de reclutar a cualquier candidato. Ver [[Reglas de Reclutamiento]].

> [!info] Sistema
> Como Carlos no tiene SSN ni TaxID, el sistema activa automáticamente la **retención del 16%** sobre su cheque. Ver [[Deducciones]].

---

## Acto 2 — Primera asignación y onboarding en hotel

**Semáforo: ⚪ Blanco → 🟢 Verde manzana → 🔵 Azul claro → 🟠 Naranja**

### La Requisición

El [[Supervisor]] del Hotel Riviera (zona Centro) crea una [[Requisición]] solicitando 2 Housekeepers, tiempo completo, con inicio el lunes próximo e inglés intermedio. El [[Manager de Área]] la autoriza.

El sistema calcula la urgencia: más de 120 horas antes del inicio = Verde (Normal). Las posiciones se reflejan en el [[Schedule]] de la semana. El [[Inspector]] de zona Centro se asigna automáticamente a la requisición.

### Match y asignación

La [[Reclutadora]] toma la requisición de la bandeja compartida ([[Self-Pick de Requisiciones|Self-Pick]]). Busca en el [[Pool de Colaboradores]]: Housekeeper, Intermedio, zona Centro, Tiempo completo. Encuentra a Carlos (⚪ Blanco). Lo asigna al Hotel Riviera y lo registra en el [[Schedule]].

### Día 1 — Verde manzana

Carlos llega al Hotel Riviera. El [[Inspector]] verifica su llegada en sitio.

Transición: **⚪ Blanco → 🟢 Verde manzana**.

El [[Timesheet]] se crea a partir del [[Schedule]]. Carlos poncha su primera Entrada vía QR generado por el [[Manager de Área]].

### Día 3 — Azul claro

Carlos poncha en la propiedad al tercer día. El [[Inspector]] le entrega su uniforme.

Transición: **🟢 Verde manzana → 🔵 Azul claro**.

> [!info] Sistema
> Se genera una [[Deducciones|deducción]] de **$15 USD** por uniforme, que se aplicará en el próximo [[Consolidado Semanal del Colaborador|Consolidado Semanal]].

### Día 7+ — Naranja

Carlos completa 7 días consecutivos. El sistema lo transiciona automáticamente.

Transición: **🔵 Azul claro → 🟠 Naranja (Fijo)**.

Carlos ahora es un colaborador fijo en Hotel Riviera.

---

## Acto 3 — Operación diaria

**Semáforo: 🟠 Naranja — Fijo**

Un día típico de Carlos en Hotel Riviera. Poncha vía QR generado por el [[Manager de Área]].

### Registro de ponches

| Ponche | Hora | Evento |
|---|---|---|
| Entrada | 7:00 AM | Inicio de jornada |
| Salida Lunch | 12:00 PM | Sale a comer |
| Entrada Lunch | 12:35 PM | Regresa de comer |
| Salida Break | 3:00 PM | Sale a descanso |
| Entrada Break | 3:15 PM | Regresa de descanso |
| Salida | 5:00 PM | Fin de jornada |

### Cálculo de horas

| Concepto | Cálculo | Resultado |
|---|---|---|
| Horas brutas | 5:00 PM − 7:00 AM | 10h 00min |
| Lunch real | 12:35 PM − 12:00 PM | 35 min |
| Deducción de lunch | Lunch real (35 min) ≥ 30 min → se deduce tiempo real | 35 min |
| Break real | 3:15 PM − 3:00 PM | 15 min |
| **Horas netas** | 10h 00min − 35min − 15min | **9h 10min** |

> [!warning] Indicador de Lunch Extendido
> El lunch de Carlos (35 min) excede los 30 minutos. El sistema activa el **Indicador de Lunch Extendido**, visible únicamente para [[Inspector]], [[Coordinador]] y [[Manager de Reclutamiento]]. El hotel **no tiene acceso** a este indicador. No es punitivo de forma automática.

### Escenario alternativo — Lunch de 25 minutos

Si Carlos hubiera tomado solo 25 minutos de lunch:

| Concepto | Cálculo | Resultado |
|---|---|---|
| Lunch real | 25 min | 25 min |
| Deducción de lunch | Lunch real (25 min) < 30 min → se deduce el **mínimo de 30 min** | 30 min |
| **Horas netas** | 10h 00min − 30min − 15min | **9h 15min** |

> [!info] Regla de Lunch
> La deducción de lunch aplica a todos sin excepción:
> - Lunch < 30 min → se deducen 30 min (mínimo obligatorio)
> - Lunch ≥ 30 min → se deduce el tiempo real tomado
> - Sin ponche de lunch → auto-deducción de 30 min
>
> Después de 6 horas continuas de trabajo, el colaborador debe tomar su lunch. Ver [[Reglas del Colaborador]].

---

## Acto 4 — Primera semana de pago

**Semáforo: 🟠 Naranja — Fijo**

Al cierre de la semana, el sistema genera automáticamente el [[Consolidado Semanal del Colaborador|Consolidado Semanal]] de Carlos. Como trabajó solo en Hotel Riviera, el consolidado contiene un único [[Timesheet]].

### Detalle de la semana

| Día | Horas brutas | Lunch | Break | Horas netas |
|---|---|---|---|---|
| Lunes | 10h 00min | 35 min | 15 min | 9h 10min |
| Martes | 8h 00min | 30 min | 15 min | 7h 15min |
| Miércoles | 8h 00min | 30 min | 15 min | 7h 15min |
| Jueves | 8h 00min | 30 min | 15 min | 7h 15min |
| Viernes | 8h 00min | 30 min | 15 min | 7h 15min |
| **Total** | **42h 00min** | — | — | **38h 10min** |

Las 42 horas brutas exceden el umbral de 40 horas semanales → **2 horas de overtime** en Hotel Riviera.

### Cálculo de pago

Pay rate de Carlos en Hotel Riviera: **$14.00/hr**.

| Concepto | Cálculo | Monto |
|---|---|---|
| Horas regulares (netas − OT ajustado) | 36h 10min × $14.00 | $506.33 |
| Overtime | 2h 00min × $21.00 (1.5×) | $42.00 |
| **Subtotal bruto** | | **$548.33** |

### Deducciones aplicadas

| Deducción | Monto | Condición |
|---|---|---|
| Uniforme | $15.00 | Entregado el Día 3 por el [[Inspector]] |
| Comida | $15.00 | $3.00 × 5 días laborados (configurado en el [[Contrato]]) |
| Retención 16% | $87.73 | 16% de $548.33 (sin SSN/TaxID) |
| **Total deducciones** | **$117.73** | |

### Cheque final

| Concepto | Monto |
|---|---|
| Subtotal bruto | $548.33 |
| Total deducciones | −$117.73 |
| **Cheque neto** | **$430.60** |

> [!info] Sistema
> El [[Consolidado Semanal del Colaborador|Consolidado Semanal]] es de uso exclusivo de Contabilidad. Carlos no tiene acceso a este documento. La [[Contadora]] revisa y el [[Manager de Contabilidad]] aprueba antes de liberar el pago (ver [[Flujo de Nómina]]).

---

## Acto 5 — Stand-by y disponibilidad voluntaria

**Semáforo: 🟠 Naranja → 🩷 Rosa → 🟡 Amarillo → 🤎 Café**

### Rosa — Stand-by

Semanas después, el Hotel Riviera entra en temporada baja. El [[Supervisor]] pone a Carlos en estado **🩷 Rosa (Stand-by)**.

Carlos ya no tiene [[Schedule]] ni [[Timesheet]].

> [!warning] Regla de ponchado
> En estado Rosa el colaborador **no puede ponchar**. La cadena es: Asignación activa → [[Schedule]] → [[Timesheet]] → Ponchado. Sin asignación activa, no hay Schedule; sin Schedule, no hay Timesheet; sin Timesheet, no puede ponchar. Ver [[Reglas del Colaborador]].

### Amarillo — Disponible voluntario

Carlos decide que quiere seguir trabajando. Desde la app, activa el estado **🟡 Amarillo (Disponible voluntario)** por cuenta propia. No requiere aprobación de nadie.

> [!info] Sistema
> Amarillo es el **único estado** que el colaborador puede activar por sí mismo. Es una declaración de disponibilidad, no una asignación. Carlos sigue sin [[Schedule]] ni [[Timesheet]] y **no puede ponchar** hasta ser asignado (→ Café).

### Café — Asignación temporal

La [[Reclutadora]] detecta que el Hotel Playa Sol (zona Sur) necesita cobertura por 3 días. Busca en el [[Pool de Colaboradores]], encuentra a Carlos en Amarillo. Lo asigna temporalmente y define la duración: **3 días**.

Transición: **🟡 Amarillo → 🤎 Café (Asignación temporal)**.

Se genera el [[Schedule]] y [[Timesheet]] de Carlos en Hotel Playa Sol. Ahora puede ponchar.

### Retorno

Al vencer los 3 días, el sistema cierra automáticamente el estado Café. Como Carlos sigue en periodo de descanso del Hotel Riviera (Rosa), regresa a **🟡 Amarillo**.

> [!info] Sistema
> El camino completo para que un colaborador en descanso pueda trabajar es: **Rosa → Amarillo → Café**. Si el periodo de descanso hubiera terminado, Carlos regresaría a **🟢 Verde fuerte** en lugar de Amarillo.

---

## Acto 6 — Trabajo en múltiples hoteles

**Semáforo: 🟠 Naranja (Hotel Riviera) + 🤎 Café (Hotel Playa Sol)**

### Contexto

Semanas después, Carlos ya regresó del descanso y está como **🟠 Naranja** (fijo) en Hotel Riviera. El Hotel Playa Sol necesita cobertura extra y la [[Reclutadora]] lo asigna temporalmente (**🤎 Café**) para cubrir 2 días adicionales esa semana.

### Horas por hotel

| Hotel | Tipo | Días | Horas brutas | Horas netas | OT (brutas > 40) |
|---|---|---|---|---|---|
| Hotel Riviera | Fijo | 5 | 42h | 38h 10min | 2h OT |
| Hotel Playa Sol | Temporal | 2 | 16h | 14h 30min | 0h OT |

> [!warning] Regla de Overtime
> El overtime se calcula **por hotel**, no de forma global entre hoteles. Hotel Riviera tiene 42h brutas (2h OT). Hotel Playa Sol tiene 16h brutas (sin OT, por debajo de 40h). Ver [[Consolidado Semanal del Colaborador]].

### Rate interno vs. contractual

Carlos, por su experiencia y desempeño, tiene un **rate interno** de $15.00/hr acordado con Oranje, aunque el [[Contrato]] del Hotel Riviera pacta un pay rate de $14.00/hr.

- El sistema usa **$15.00/hr** para calcular el pago a Carlos.
- La [[Facturación al Hotel]] siempre usa el **bill rate contractual**, no el rate interno.
- La diferencia la absorbe Oranje.

> [!info] Sistema
> El rate interno solo es visible para Contabilidad ([[Manager de Contabilidad]] y [[Contadora]]). Ni Carlos ni el hotel conocen esta diferencia.

### Asignación del cheque

Como Carlos trabajó más horas en Hotel Riviera (42h brutas vs. 16h brutas), el cheque se asigna a **Hotel Riviera** para efectos de impresión y entrega.

---

## Acto 7 — Primera inasistencia

**Semáforo: 🟠 Naranja → 🟣 Morado → 🟠 Naranja**

Un día, Carlos no se presenta al Hotel Riviera sin justificación. El sistema lo marca automáticamente como **🟣 Morado (No regresó)**.

Es su **primera inasistencia**. Le quedan 2 antes del Blacklist automático.

> [!danger] Regla de 3 inasistencias
> Cada inasistencia se registra individualmente. Al acumular **3 inasistencias**, el sistema aplica [[Blacklist]] automático (estado Negro). No requiere acción manual de ningún rol. Ver [[Reglas del Colaborador]].

Al día siguiente, Carlos regresa y sigue trabajando normalmente. Su semáforo regresa a **🟠 Naranja**.

---

## Acto 8 — Accidente laboral

**Semáforo: 🟠 Naranja → Gris (Accidentado) → 🟢 Verde fuerte**

### El accidente

Carlos se lesiona mientras limpia una habitación en Hotel Riviera: resbala con piso mojado. Reporta desde la app (Escenario A del [[Flujo de Accidente Laboral]]).

### Generación de tarjeta

Se genera la tarjeta de [[Accidente Laboral]] con número de reporte automático. Carlos transita inmediatamente a **Gris — Accidentado**.

La señal llega simultáneamente al [[Supervisor|SUP]] y al [[Inspector]] de zona Centro.

### Captura presencial (SUP)

El [[Supervisor|SUP]] acude al lugar y captura:

| Campo | Detalle |
|---|---|
| Ubicación | Habitación 307, piso 3 |
| Circunstancias | Resbaló con piso mojado durante limpieza |
| Testigos | María González (compañera de turno) |
| Atención inmediata | Hielo y vendaje en sitio |

### Seguimiento médico (Inspector)

El [[Inspector]] complementa la tarjeta:

| Campo | Detalle |
|---|---|
| Traslado | Clínica local zona Centro |
| Diagnóstico | Esguince de tobillo grado 2 |
| Días de incapacidad | 10 días |
| Observaciones | Reposo absoluto, anti-inflamatorios |

> [!warning] Protección durante estado Gris
> Mientras Carlos esté en estado **Gris**, sus inasistencias **no cuentan** para la regla de 3 → Negro. Está protegido de [[Blacklist]]. La inasistencia previa (Acto 7) sigue contando, pero las que ocurran durante Gris no se acumulan. Ver [[Reglas del Colaborador]].

### Alta médica y reintegro

Tras 10 días, Carlos recibe alta médica. El [[Inspector]] cierra la tarjeta de accidente.

Transición: **Gris → 🟢 Verde fuerte (Disponible)**.

Carlos queda disponible para nueva asignación.

---

## Acto 9 — Reporte del hotel

**Semáforo: 🟢 Verde fuerte → 🟠 Naranja → 🔴 Rojo**

### Nueva asignación

Tras recuperarse, Carlos es asignado al Hotel Costa Azul (zona Este) a través de una nueva [[Requisición]]. Completa su progresión y llega a **🟠 Naranja (Fijo)**.

### El reporte

El [[Supervisor]] del Hotel Costa Azul reporta a Carlos por una queja de un huésped. Carlos transita a **🔴 Rojo (Reportado)**.

### Investigación

El [[Inspector]] de zona Este investiga el caso. Entrevista a Carlos, al Supervisor y recaba evidencia. El Inspector tiene **autoridad propia** para decidir el resultado, sin necesidad de escalamiento al [[Manager de Reclutamiento]].

### Escenario A — Resolución a favor de Carlos

El [[Inspector]] determina que la queja no estaba justificada.

Transición: **🔴 Rojo → 🟢 Verde fuerte (Reincorporado)**.

> [!success] Resultado
> Carlos es reincorporado. Disputa resuelta a favor del colaborador.

### Escenario B — Resolución a favor del hotel (hipotético)

Si el [[Inspector]] hubiera determinado que la falta era grave:

Transición hipotética: **🔴 Rojo → ⚫ Negro (Blacklist)**.

> [!danger] Escenario alternativo
> En este escenario hipotético, Carlos habría quedado vetado **permanentemente**. El estado Negro no tiene rehabilitación ni apelación. El registro se conserva pero el colaborador no aparece en búsquedas activas. La 3ra inasistencia también lo habría llevado al mismo destino por otra vía. Ver [[Blacklist]].

---

## Acto 10 — Entrega de documentos fiscales

Carlos obtiene su SSN y lo entrega a través del proceso correspondiente.

La [[Contadora]] desactiva manualmente la **retención del 16%** en el sistema.

> [!info] Sistema
> La retención 16% es **reembolsable**. El monto acumulado retenido durante todas las semanas previas puede ser devuelto a Carlos. Ver [[Deducciones]].

A partir de este momento, los cheques de Carlos ya no incluyen la retención del 16%.

---

## Acto 11 — Vacaciones

**Semáforo: 🩷 Rosa — Stand-by**

El Hotel Costa Azul programa vacaciones para Carlos. Lo pone en **🩷 Rosa**.

### Cálculo de pago de vacaciones

La [[Contadora]] solicita el cálculo al sistema. La fórmula es:

```
Promedio de horas = Suma de horas netas pagadas (últimas 52 semanas) / 52
```

Como Carlos trabajó en múltiples hoteles con diferentes rates, el sistema separa por hotel:

| Hotel | Semanas trabajadas | Promedio horas/semana | Rate |
|---|---|---|---|
| Hotel Riviera | 30 | 37.5 hrs | $15.00/hr |
| Hotel Playa Sol | 3 | 36.0 hrs | $13.00/hr |
| Hotel Costa Azul | 19 | 37.0 hrs | $14.50/hr |

> [!info] Sistema
> Si el colaborador tiene menos de 52 semanas de antigüedad, se promedia sobre las semanas disponibles. Ver [[Vacaciones]].

---

## Epílogo — Resumen del recorrido

### Los 12 estados del Semáforo

| # | Estado | Color | Acto | Evento |
|---|---|---|---|---|
| 1 | Blanco | ⚪ Pre-asignación | 1 | Ingreso al Pool tras aprobación |
| 2 | Verde manzana | 🟢 Día 1-2 | 2 | Inspector verifica llegada al hotel |
| 3 | Azul claro | 🔵 Día 3+ | 2 | Poncha Día 3, recibe uniforme |
| 4 | Naranja | 🟠 Fijo | 2 | Completa 7 días |
| 5 | Rosa | 🩷 Stand-by | 5 | Hotel lo manda a descansar |
| 6 | Amarillo | 🟡 Disponible voluntario | 5 | Carlos se declara disponible |
| 7 | Café | 🤎 Asignación temporal | 5 | Reclutadora lo asigna temporalmente |
| 8 | Verde fuerte | 🟢 Disponible | 8 | Alta médica, reincorporado |
| 9 | Morado | 🟣 No regresó | 7 | Inasistencia sin justificación |
| 10 | Rojo | 🔴 Reportado | 9 | Hotel lo reporta |
| 11 | Gris | Accidentado | 8 | Accidente laboral reportado |
| 12 | Negro | ⚫ Blacklist | 9 | (Escenario alternativo) |

### Módulos referenciados

| Módulo | Actos |
|---|---|
| [[Pool de Colaboradores]] | 1 |
| [[Flujo de Reclutamiento]] | 1 |
| [[Requisición]] / [[Flujo de Requisición]] | 2, 9 |
| [[Schedule]] | 2, 3, 5, 6 |
| [[Timesheet]] | 3, 4, 6 |
| [[Consolidado Semanal del Colaborador]] | 4, 6 |
| [[Deducciones]] | 4, 10 |
| [[Flujo de Nómina]] | 4 |
| [[Facturación al Hotel]] | 6 |
| [[Accidente Laboral]] / [[Flujo de Accidente Laboral]] | 8 |
| [[Blacklist]] | 7, 9 |
| [[Vacaciones]] | 11 |
| [[Contrato]] | 4, 6 |
| [[Self-Pick de Requisiciones]] | 2 |

### Roles que interactuaron con Carlos

| Rol | Actos |
|---|---|
| [[Reclutadora]] | 1, 2, 5, 6 |
| [[Inspector]] | 2, 3, 8, 9 |
| [[Supervisor]] | 2, 5, 8, 9 |
| [[Manager de Área]] | 2, 3 |
| [[Contadora]] | 4, 10, 11 |
| [[Manager de Contabilidad]] | 4 |
| [[Manager de Reclutamiento]] | (supervisión de Blacklist) |
| [[Coordinador]] | (supervisión de Inspector) |

---

## Relacionado

- [[Semáforo del Colaborador]]
- [[Reglas del Colaborador]]
- [[Reglas de Negocio]]
- [[Colaborador]]

---

## Simulaciones relacionadas

- [[Simulación - Punto de Vista del Hotel]] — Narra el ciclo del hotel donde opera el colaborador, incluyendo requisiciones, facturación y Stand-by.
- [[Simulación de Reclutamiento]] — Detalla el proceso de reclutamiento y asignación al Pool por el que pasa el colaborador antes de ser asignado a un hotel.
- [[Simulación - Punto de Vista de Inspección]] — Muestra cómo el Inspector verifica, investiga reportes y gestiona accidentes que afectan directamente al colaborador.
- [[Simulación - Punto de Vista de Ventas]] — Cubre el proceso comercial que convierte al hotel en cliente activo, habilitando la asignación de colaboradores.
