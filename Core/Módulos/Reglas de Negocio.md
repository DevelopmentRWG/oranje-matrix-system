---
tags:
  - modulo/core
aliases:
  - Reglas de Negocio
  - Business Rules
  - Reglas del Sistema
---

# Reglas de Negocio

Documento centralizado con las reglas de negocio que gobiernan el sistema Oranje. Cada regla referencia el módulo donde se aplica y los roles involucrados.

> [!info] Las reglas aquí documentadas son la fuente de verdad. Los semáforos y flujos implementan estas reglas, pero este archivo las define.

## Colaborador

> [!tip] Para la referencia completa, ver [[Reglas del Colaborador]].

### Captura de datos en 3 fases
- **Fase 1 — Entrevista inicial:** la [[Reclutadora]] captura los datos básicos del candidato: nombre completo, edad, género, domicilio y teléfono
- **Fase 2 — Alta en la app:** el propio Colaborador completa su información personal (SSN, ITIN, Posición, Nivel de inglés, Nivel de experiencia, Tipo de transporte, Modalidad)
- **Fase 3 — Datos de emergencia:** el Colaborador completa desde la app: contacto de emergencia (nombre, teléfono, parentesco), tipo de sangre y alergias o condiciones médicas

### Progresión del colaborador (Semáforo)
- **Blanco → Verde manzana:** al ser asignado y asistir el Día 1. El [[Inspector]] verifica su llegada en sitio
- **Verde manzana → Azul claro:** cuando poncha en la propiedad al tercer día. El [[Inspector]] le entrega su uniforme
- **Azul claro → Naranja:** al completar 7 días (automático por sistema)
- **Naranja → Verde fuerte:** cuando el colaborador queda libre (fin de asignación fija o reincorporado)

### Estado Amarillo (Disponible voluntario)
- Lo activa el propio colaborador durante un descanso
- Es el único estado que el colaborador puede activar por sí mismo

### Asignación temporal (Café)
- La [[Reclutadora]] asigna temporalmente al colaborador (→ Café)
- Al terminar la jornada temporal, vuelve a Verde fuerte o Naranja según su estado previo

### Estado Rosa (Stand-by)
- Solo el hotel ([[Hotel/Manager del Hotel|Manager del Hotel]]) puede poner a un colaborador en estado Rosa
- Indica que el colaborador está en espera por decisión del hotel (vacaciones, temporada baja)
- La posición no tiene fecha de fin; termina cuando el Manager del Hotel pone al colaborador en Rosa

### Inasistencia (Morado)
- El sistema marca Morado cuando el colaborador no asiste sin justificación
- Cada inasistencia se registra individualmente

### Regla de 3 inasistencias
- 3 inasistencias acumuladas → [[Core/Módulos/Blacklist|Blacklist]] automático (estado Negro)
- Aplica al [[Semáforo del Colaborador]]
- Responsable: Sistema (automático)

### Resolución de Reportes (Rojo)
- El hotel ([[Hotel/Manager del Hotel|Manager del Hotel]]) activa el estado Rojo (reportado)
- El [[Inspector]] investiga el caso y resuelve hacia:
  - **Negro** ([[Core/Módulos/Blacklist|Blacklist]]), si la disputa es a favor del hotel
  - **Verde fuerte** (reincorporado), si la disputa es a favor del colaborador

### Protección por Accidente Laboral (Gris)
- Cualquier estado activo → Gris cuando se genera un reporte de accidente laboral
- Protege al colaborador de la regla de 3 inasistencias; las inasistencias durante incapacidad no cuentan
- Gris → Verde fuerte: requiere alta médica + cierre de tarjeta de accidente por el [[Inspector]]
- Referencia: [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]]

## Estructura organizacional del hotel

### Dos jerarquías soportadas
- La plataforma soporta dos configuraciones jerárquicas para el hotel, según su tamaño y complejidad:
  - **Jerarquía simple:** [[Hotel/Manager del Hotel|Manager del Hotel]] → [[Hotel/Supervisor|SUP]] → Colaboradores de Oranje
  - **Jerarquía extendida:** [[Hotel/Manager General|Manager General]] → Gerente de Departamento → Supervisor → Colaboradores de Oranje
- En la jerarquía extendida, el Gerente de Departamento tiene las mismas responsabilidades de plataforma que el [[Hotel/Manager del Hotel|Manager del Hotel]], y el Supervisor las mismas que el [[Hotel/Supervisor|SUP]]

### Departamentos del hotel
- Los [[Departamentos del Hotel]] son: Housekeeping, Alimentos, Mantenimiento y Front Desk
- En la jerarquía extendida, cada departamento tiene su propio Gerente y Supervisor(es)
- Las [[Posiciones]] solicitadas en las requisiciones corresponden a un departamento específico del hotel

### Manager General
- El [[Hotel/Manager General|Manager General]] es la máxima autoridad del hotel en la jerarquía extendida
- No aprueba requisiciones directamente; esa responsabilidad recae en los Gerentes de Departamento
- Tiene visibilidad global del [[Core/Módulos/Schedule|Schedule]] y [[Timesheet]] de todos los departamentos

## Requisición y Autorización

### Acceso al sistema
- Solo el [[Hotel/Manager del Hotel|Manager del Hotel]] (GH) y el [[Hotel/Supervisor|Supervisor]] (SUP) tienen acceso al módulo de requisiciones
- Usuarios sin acceso reciben mensaje: "No cuenta con acceso"

### Creación y elaboración
- El SUP crea la requisición (estado Verde manzana — En elaboración)
- El número de requisición se genera automáticamente: Año (4 dígitos) + Mes (2) + Día (2) + Hora (2, formato 24h) + Minutos (2) + Homoclave (2 caracteres alfanuméricos aleatorios). Ejemplo: `202604081632V1`
- El mismo formato aplica para el número de posición

### Autorización de Requisición
- Solo el [[Hotel/Manager del Hotel|Manager del Hotel]] (GH) puede autorizar una requisición
- El SUP recibe mensaje de bloqueo: "Solo el gerente del hotel puede autorizar la requisición"
- Debe existir al menos una posición para poder autorizar; de lo contrario: "No tiene posiciones registradas, registre al menos una posición e intente nuevamente"
- El rechazo regresa la requisición al SUP con observaciones (estado "En elaboración")

### Al autorizar
- El sistema calcula automáticamente la urgencia de cada posición
- Cada posición pasa de Dorado a Naranja y el sistema calcula su prioridad
- Las posiciones autorizadas quedan reflejadas en el [[Core/Módulos/Schedule|Schedule]] de la semana correspondiente a su fecha de inicio
- El [[Inspector]] en la cabecera se asigna automáticamente según la [[Core/Catálogos/Zonas|zona]] del hotel

### Fórmula de Urgencia
- Se calcula por posición: `fecha de autorización de la requisición` vs `fecha de inicio de la posición`
- `> 120 horas` → Verde fuerte (Normal)
- `72 – 120 horas` → Amarillo (Medio)
- `< 72 horas` → Rojo (Urgente)
- El sistema reevalúa automáticamente y ajusta el color conforme avanza el tiempo
- Referencia: [[Semáforo de Urgencia de Requisición]]

### Cobertura de Posiciones
- Requisición = Azul claro solo si TODAS las posiciones están en Verde (100% cubierta)
- Posición en Amarillo: hasta 25% faltante
- Posición en Rojo: más del 25% faltante
- Si alguna posición está en Amarillo o Rojo → Requisición en Rojo
- Referencia: [[Semáforo de Posiciones de la Requisición]]

### Asignación
- El [[Manager de Reclutamiento]] recibe la requisición autorizada y la asigna a una [[Reclutadora]] → la requisición pasa a Amarillo (En proceso)
- Si no hay match en el [[Pool de Colaboradores]], la requisición queda en espera; el Flujo de Reclutamiento ya está siempre activo

### Ciclo de vida de la posición
- La posición tiene fecha de inicio pero no fecha de fin definida
- Termina cuando el [[Hotel/Manager del Hotel|Manager del Hotel]] pone al colaborador en Stand-by (estado Rosa en el [[Semáforo del Colaborador]])

### Eliminación (Morado)
- Estado transversal: se alcanza desde cualquier estado cuando se elimina la requisición
- Requisición sin posiciones al salir del editor → eliminación física automática
- El sistema ejecuta RUTINA Journal Requisición en toda eliminación
- Al eliminar una requisición con posiciones → cada posición también pasa a Morado con journal individual

### Journals automáticos
- **RUTINA Journal Requisición:** registra Requisición, Hotel, Gerente Hotel, Reclutador, Inspector, Status, Nota, Fecha y hora del status
- **RUTINA Journal Posición:** registra Número de requisición, Número de posición, Posición, Cantidad de personas, Fecha de inicio, Fecha fin, Status, Fecha y hora del status

## Blacklist

### Blacklist automático
- Disparado por regla de 3 inasistencias
- Estado: Negro en [[Semáforo del Colaborador]]

### Blacklist manual
- Disparado por disputa resuelta a favor del hotel (estado Rojo → investigación del [[Inspector]])
- El [[Manager de Reclutamiento]] revisa los casos de blacklist

### Consulta obligatoria
- La [[Reclutadora]] debe consultar la [[Core/Módulos/Blacklist|Blacklist]] antes de reclutar a un candidato, para evitar volver a reclutar a alguien vetado

## Accidente Laboral

### Activación de estado Gris
- El reporte de accidente activa estado Gris en [[Semáforo del Colaborador]] desde cualquier estado activo
- **Escenario A:** el Colaborador reporta desde la app; la señal llega simultáneamente al SUP y al [[Inspector]] de zona asignado
- **Escenario B:** el SUP ([[Hotel/Supervisor|Supervisor]]) reporta; la señal llega al Inspector
- Se genera un número de reporte automático (mismo patrón que requisición: fecha/hora + homoclave)

### Cierre de tarjeta
- El [[Inspector]] es siempre el responsable final del cierre de la tarjeta de accidente
- Gris → Verde fuerte: requiere alta médica + cierre de tarjeta por el Inspector
- El colaborador queda disponible para reasignación tras el cierre

### Journal de accidente
- Cada cambio de status genera registro con: Número de reporte, Hotel, Colaborador, Reportado por, Status, Nota, Fecha y hora del status

## Onboarding y Ventas

### Habilitación del hotel
- El hotel solo puede generar requisiciones cuando alcanza el Status Naranja en el [[Semáforo Onboarding]]
- Antes de Naranja, el hotel es un prospecto comercial gestionado por [[Ventas/Ventas|Ventas]]

### Conversión de prospecto a cliente
- Solo el [[Ventas/Roles/Business Developer Coordinator|Business Developer Coordinator]] (BDC) puede aprobar la conversión
- **Precondición:** creación del [[Ventas/Onboarding-Hotel/Conceptos/Usuario del Hotel|Usuario del Hotel]] en el sistema
- Al aprobar, se dispara el [[Ventas/Onboarding-Hotel/Conceptos/Trigger Automático de Conversión|Trigger Automático de Conversión]] con acciones en paralelo:
  - Sistema envía email de bienvenida al hotel
  - Sistema notifica al Business Developer asignado
  - Hotel desaparece de la lista de prospectos

### Documento de Términos y Condiciones
- Se crea en Status Onboarding Amarillo por el BD o el BDC
- Se negocia en Status Onboarding Rosa
- Contenido: Pay rate, Bill rate, Overtime, Festivos, Calendario
- Validación final: [[Ventas/Roles/Business Developer Coordinator|Business Developer Coordinator]] antes del cierre del [[Contrato]]

### Propuesta Personalizada
- Se elabora y envía en Status Onboarding Verde
- Se ajusta/retoma desde Status Onboarding Café cuando hay estancamiento

### Reactivación de estados
- Rojo, Negro y Café siempre reactivan hacia Azul Claro
- Café no es un status terminal: es un puente de desbloqueo operado por el BDC

### Trazabilidad
- Todo cambio de status en Onboarding queda registrado con fecha, responsable y comentario

## Indicador de Calidad / QA

### Principio fundamental
- [[QA/QA|QA]] no ejecuta la operación de ningún departamento; solo observa, mide y retroalimenta

### Estructura del equipo
- Existen 5 [[QA/Operador de QA|Operadores de QA]], uno por cada departamento supervisado: Inspección, Hotel, Colaborador, Ventas y Reclutamiento
- Cada operador está asignado de forma fija a un único departamento

### Actualización del Indicador
- El [[QA/Operador de QA|Operador de QA]] propone el cambio de estado con base en métricas
- El [[QA/Manager de QA|Manager de QA]] valida y aprueba la actualización
- Solo el Manager de QA puede actualizar formalmente el [[Indicador de Calidad]] de cada departamento
- Cada departamento tiene su propio Indicador independiente; estado inicial es Verde

### Transiciones del Indicador
- **→ Verde:** estado inicial cuando QA comienza a supervisar un departamento
- **Verde → Amarillo:** cuando el Operador detecta métricas fuera de rango o emite observaciones no atendidas
- **Amarillo → Rojo:** cuando las observaciones persisten sin atención o las métricas se deterioran significativamente
- **Rojo → Amarillo:** cuando el departamento comienza a atender observaciones y muestra mejora
- **Amarillo → Verde:** cuando todas las observaciones están resueltas y las métricas regresan a parámetros

### Escalamiento
- Departamento en Rojo sin mejora tras notificación → el [[QA/Manager de QA|Manager de QA]] escala a dirección

## Reclutamiento y Pool

### Naturaleza del flujo
- El [[Reclutamiento/Flujo de Reclutamiento|Flujo de Reclutamiento]] es continuo: Reclutamiento siempre está contratando, haya o no requisiciones abiertas
- Las requisiciones sin match pueden acelerar o priorizar ciertas posiciones/zonas, pero no son condición para iniciar el flujo

### Distribución de requisiciones
- El [[Manager de Reclutamiento]] distribuye las requisiciones a las [[Reclutadora|reclutadoras]]
- Las requisiciones no llegan directamente a las reclutadoras

### Aprobación del colaborador
- La [[Reclutadora]] valida y aprueba al colaborador después de que completa su alta en la app
- La Reclutadora habilita el acceso del colaborador a los paneles
- Colaborador aprobado ingresa al [[Pool de Colaboradores]] con [[Semáforo del Colaborador]] en estado Blanco

### Elegibilidad del Pool
- Solo entran al Pool colaboradores que pasaron el filtro y fueron aprobados por Reclutamiento

## Schedule y Timesheet

### Configuración del Schedule
- La semana del hotel está definida por el contrato (inicio y fin de semana)
- Al crearse una requisición con fecha de inicio dentro de la semana, sus posiciones quedan reflejadas en el [[Core/Módulos/Schedule|Schedule]] de esa semana

### Asignación en Schedule
- Al asignar un colaborador desde el [[Pool de Colaboradores]], queda registrado en el schedule del hotel

### Dependencia del Timesheet
- El [[Timesheet]] se crea a partir del [[Core/Módulos/Schedule|Schedule]]; no puede existir de forma independiente

### Mecanismo de ponchado
- El colaborador poncha vía QR que genera el [[Hotel/Manager del Hotel|Manager del Hotel]]
- Los ponches válidos son exactamente tres: **Entrada**, **Lunch**, **Salida**
- Esto contabiliza el tiempo trabajado del colaborador

### Deducción de Lunch

> [!important] Esta regla aplica a **todos** los colaboradores sin excepción, en cada jornada.

- El sistema deduce tiempo de lunch del [[Timesheet]] del colaborador:
- Después de 6 horas continuas de trabajo, el colaborador debe tomar su lunch.
  - **Lunch menor a 30 min:** se deducen 30 minutos (mínimo obligatorio)
  - **Lunch mayor a 30 min:** se deduce el tiempo real tomado
  - **Sin ponche de Lunch:** se auto-deducen 30 minutos
- La deducción de lunch impacta directamente el cómputo de horas pagables en el [[Timesheet]]

> [!note] El mecanismo de ponchado actual registra un único ponche de **Lunch**. Para calcular la duración del lunch, el sistema debe capturar el inicio y fin del periodo de lunch (ya sea con dos ponches separados o con lógica de cálculo automático). Esto queda como consideración para el equipo de desarrollo.

### Indicador de Lunch Extendido

- El sistema identifica automáticamente a los colaboradores cuyo tiempo de lunch excede los 30 minutos
- **Visibilidad restringida** — solo roles internos de Oranje:
  - [[Inspector]]
  - [[Inspección/Coordinador|Coordinador]]
  - [[Manager de Reclutamiento]]
- **No visible para el hotel:** el [[Hotel/Manager del Hotel|Manager del Hotel]] y el [[Hotel/Supervisor|Supervisor]] no tienen acceso a este indicador
- **Propósito:** herramienta de supervisión interna para detectar patrones y tomar acciones operativas; no es punitivo de forma automática

## Inspección y Zonas

### Asignación por zona
- Cada hotel pertenece a una [[Core/Catálogos/Zonas|zona]] geográfica
- A cada zona le corresponde un [[Inspector]] asignado por el [[Inspección/Coordinador|Coordinador]]
- El Inspector de la zona del hotel es responsable de darle seguimiento a cualquier disputa en ese hotel

### Responsabilidades del Inspector
- **Día 1:** verifica la llegada del colaborador en la propiedad (transición Blanco → Verde manzana)
- **Día 3:** entrega el uniforme al colaborador (transición → Azul claro)
- **Reportes:** investiga disputas (estado Rojo) y resuelve hacia Negro o Verde fuerte
- **Accidentes:** responsable final del cierre de la tarjeta de accidente; gestiona transición Gris → Verde fuerte

### Coordinador
- El [[Inspección/Coordinador|Coordinador]] asigna inspectores a las zonas geográficas y supervisa su trabajo en campo

## Relacionado

- [[Semáforo del Colaborador]]
- [[Semáforo de Requisición]]
- [[Semáforo de Urgencia de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
- [[Semáforo Onboarding]]
- [[Indicador de Calidad]]
- [[Core/Módulos/Requisicion/Flujo de Requisición|Flujo de Requisición]]
- [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]]
- [[Reclutamiento/Flujo de Reclutamiento|Flujo de Reclutamiento]]
- [[Ventas/Onboarding-Hotel/Flujo de Onboarding|Flujo de Onboarding]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Pool de Colaboradores]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Timesheet]]
- [[Hotel/Manager del Hotel|Manager del Hotel]]
- [[Hotel/Supervisor|Supervisor]]
- [[Inspector]]
- [[Inspección/Coordinador|Coordinador]]
- [[Reclutadora]]
- [[Manager de Reclutamiento]]
- [[QA/QA|QA]]
- [[QA/Manager de QA|Manager de QA]]
- [[QA/Operador de QA|Operador de QA]]
- [[Ventas/Roles/Business Developer Coordinator|Business Developer Coordinator]]
- [[Ventas/Onboarding-Hotel/Conceptos/Usuario del Hotel|Usuario del Hotel]]
- [[Ventas/Onboarding-Hotel/Conceptos/Trigger Automático de Conversión|Trigger Automático de Conversión]]
- [[Ventas/Onboarding-Hotel/Conceptos/Documento de Términos y Condiciones|Documento de Términos y Condiciones]]
- [[Core/Catálogos/Zonas|Zonas]]
