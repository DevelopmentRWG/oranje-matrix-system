---
tipo: simulación
perspectiva: ventas
hotel_ficticio: Hotel Costa Esmeralda
zona: Noroeste
jerarquía: comercial
tags:
  - simulación
  - ventas
  - ciclo-completo
aliases:
  - Simulación Ventas
---

# Simulación completa — Punto de vista de Ventas

> [!abstract] Propósito
> Esta simulación narra el ciclo comercial completo de un hotel dentro del sistema Oranje, desde la perspectiva del equipo de Ventas: el [[Business Developer]] (BD) y el [[Business Developer Coordinator]] (BDC). Recorre todas las etapas del [[Semáforo Onboarding]], incluyendo una rama de rechazo y reactivación, hasta el handoff operativo. Todos los datos son ficticios, pero cada acción, transición y regla respeta fielmente la documentación del vault.

## Personajes de la simulación

| Personaje | Rol | Departamento |
|---|---|---|
| Sofía Méndez | [[Business Developer]] (BD) | Ventas — Oranje |
| Ricardo Fuentes | [[Business Developer Coordinator]] (BDC) | Ventas — Oranje |
| Operador 4 | [[Operador de QA]] (asignado fijo a Ventas) | QA — Oranje |
| Daniel Ortega | [[Inspector]] (zona Noroeste) | Inspección — Oranje |
| Mariana Vega | Gerente de Operaciones | Hotel Costa Esmeralda |
| Carlos Navarro | Director General (nuevo) | Hotel Costa Esmeralda |

---

## Fase 1 — Prospección

> Referencia: [[Flujo de Onboarding]] · [[Semáforo Onboarding]]

### 1.1 — Identificación del hotel (Gris)

Es lunes 2 de junio de 2026. Sofía Méndez, [[Business Developer]] asignada a la zona Noroeste, revisa su ruta de territorio. Identifica al **Hotel Costa Esmeralda** como un hotel de 120 habitaciones con alta ocupación en temporada y sin proveedor de staffing externo.

Sofía crea el registro del hotel como prospecto en el sistema.

> [!info] Semáforo Onboarding
> → **Gris** — Hotel identificado
> **Fecha:** 2026-06-02 · **Responsable:** Sofía Méndez (BD) · **Comentario:** "Hotel identificado en ruta de Zona Noroeste. 120 habitaciones, sin proveedor de staffing actual."

> [!tip] QA — Operador 4 observa
> El Operador 4 registra el inicio del ciclo de onboarding para el Hotel Costa Esmeralda. A partir de este momento comienza a contar el **Ciclo promedio de onboarding** (meta: ≤ 45 días). — [[Métricas y KPIs por Departamento#Ventas|KPI 2]]

---

## Fase 2 — Contacto y recopilación de datos

> Referencia: [[Semáforo Onboarding#Azul Claro — Contacto y recopilación de datos]] · [[Flujo de Onboarding]]

### 2.1 — Primer contacto telefónico

Martes 3 de junio. Sofía llama al Hotel Costa Esmeralda. Habla con Mariana Vega, Gerente de Operaciones, quien confirma que el departamento de Housekeeping está subdimensionado para la temporada alta que comienza en julio. Agenda una visita presencial para el jueves 5.

### 2.2 — Visita en frío

Jueves 5 de junio. Sofía se presenta en el hotel. Recorre las instalaciones con Mariana, visita las áreas de Housekeeping y Lavandería, conoce al equipo actual y evalúa la operación.

**Necesidad identificada:** el hotel requiere 5 Housekeepers y 2 Housemen para cubrir la temporada alta, bajo modalidad de tiempo completo.

Sofía crea el perfil del hotel en el sistema con los datos recopilados:

| Campo | Valor |
|---|---|
| Nombre del hotel | Hotel Costa Esmeralda |
| Zona | [[Zonas\|Noroeste]] |
| Email | operaciones@costaesmeralda.com |
| Teléfono | +52 311 555 0200 |
| Contacto principal | Mariana Vega |
| Cargo | Gerente de Operaciones |
| Necesidad | Personal de [[Departamentos del Hotel\|Housekeeping]]: 5 [[Posiciones\|Housekeeper]], 2 [[Posiciones\|Houseman]] |

> [!info] Semáforo Onboarding
> Gris → **Azul Claro** — Contacto y recopilación de datos
> **Fecha:** 2026-06-05 · **Responsable:** Sofía Méndez (BD) · **Comentario:** "Visita en frío realizada. Perfil creado. Necesidad: 5 HK + 2 HM para temporada alta."

> [!warning] Regla de negocio
> Acciones obligatorias en Azul Claro: crear perfil del hotel, recopilar datos (nombre, email, teléfono, contacto, necesidad), realizar visita en frío. — [[Semáforo Onboarding#Azul Claro — Contacto y recopilación de datos]]

---

## Fase 3 — Primera propuesta

> Referencia: [[Semáforo Onboarding#Verde — Propuesta enviada]] · [[Propuesta Personalizada]]

### 3.1 — Elaboración de la Propuesta Personalizada

Viernes 6 de junio. Sofía elabora la [[Propuesta Personalizada]] para el Hotel Costa Esmeralda:

| Componente | Detalle |
|---|---|
| Servicios ofrecidos | Staffing de Housekeeping: Housekeepers y Housemen |
| Modelo de operación | Oranje recluta, asigna y supervisa. Inspector de zona presente en Día 1 y Día 3 |
| Precios tentativos (pay rate) | $12.00/hr (HK), $10.50/hr (HM) |
| Precios tentativos (bill rate) | $18.00/hr (HK), $16.00/hr (HM) |
| Condiciones generales | Overtime a 1.5x, festivos a 2x, uniformes incluidos |

Sofía envía la propuesta por email a Mariana Vega y entrega una copia física durante una breve visita al hotel.

### 3.2 — Seguimiento

Sofía registra cada intento de contacto en el sistema:

| Fecha | Tipo | Resultado |
|---|---|---|
| 9 junio | Llamada | Mariana dice "lo estoy revisando con el director" |
| 10 junio | Email de seguimiento | Sin respuesta |
| 11 junio | Llamada | Mariana informa que el director rechazó la propuesta |

> [!info] Semáforo Onboarding
> Azul Claro → **Verde** — Propuesta enviada
> **Fecha:** 2026-06-06 · **Responsable:** Sofía Méndez (BD) · **Comentario:** "Propuesta Personalizada enviada por email y entregada en persona."

> [!warning] Regla de negocio
> Acciones en Verde: elaborar propuesta personalizada (servicios, precios, condiciones), enviar al hotel, registrar intentos de contacto y respuestas, hacer seguimiento. — [[Semáforo Onboarding#Verde — Propuesta enviada]]

---

## Fase 4 — Rechazo (rama alterna)

> Referencia: [[Semáforo Onboarding#Rojo — Rechazo o no interés]] · [[Reglas de Ventas#Reactivaciones]]

### 4.1 — El hotel rechaza la propuesta

Miércoles 11 de junio. Mariana Vega comunica a Sofía que el Director General del hotel decidió no contratar servicio externo por el momento — considera que el presupuesto no lo permite durante este trimestre.

Sofía evalúa el caso: el hotel mostró interés genuino durante la visita, la necesidad operativa es real. El rechazo proviene de una decisión presupuestaria del director, no de falta de necesidad. Sofía decide marcar el prospecto como rechazado pero con potencial de reactivación.

> [!info] Semáforo Onboarding
> Verde → **Rojo** — Rechazo o no interés
> **Fecha:** 2026-06-11 · **Responsable:** Sofía Méndez (BD) · **Comentario:** "Director del hotel rechazó por presupuesto. Necesidad operativa confirmada. Potencial de reactivación alto."

> [!warning] Regla de negocio
> El [[Business Developer]] gestiona el status Rojo. Evalúa si el hotel se archiva o se reactiva. — [[Semáforo Onboarding#Rojo — Rechazo o no interés]]

> [!tip] QA — Operador 4 observa
> Transición a Rojo registrada. Alimenta el KPI de **Tasa de pérdida** (hoteles en Rojo o Negro sin reactivación / total gestionados). Meta: ≤ 20%. Este hotel aún no cuenta como pérdida definitiva porque Sofía registró potencial de reactivación. — [[Métricas y KPIs por Departamento#Ventas|KPI 4]]

---

## Fase 5 — Reactivación

> Referencia: [[Reglas de Ventas#Reactivaciones]] · [[Semáforo Onboarding#Azul Claro — Contacto y recopilación de datos]]

### 5.1 — Cambio de circunstancias

Miércoles 25 de junio. Han pasado 14 días. Sofía recibe información por un contacto en la zona de que el Director General del Hotel Costa Esmeralda fue reemplazado. El nuevo director, **Carlos Navarro**, viene de una cadena hotelera que ya trabajaba con servicios de staffing y está abierto a explorar la propuesta.

Sofía decide reactivar el prospecto.

> [!info] Semáforo Onboarding
> Rojo → **Azul Claro** — Reactivación
> **Fecha:** 2026-06-25 · **Responsable:** Sofía Méndez (BD) · **Comentario:** "Nuevo director (Carlos Navarro) abierto a servicios de staffing. Reiniciando contacto."

> [!warning] Regla de negocio
> Rojo, Negro y Café **siempre** reactivan hacia Azul Claro. Responsable de la reactivación desde Rojo: [[Business Developer]]. — [[Reglas de Ventas#Reactivaciones]]

> [!tip] QA — Operador 4 observa
> Reactivación desde Rojo iniciada. Al avanzar más allá de Verde, alimentará el KPI de **Tasa de reactivación exitosa** (meta: ≥ 40%). — [[Métricas y KPIs por Departamento#Ventas|KPI 5]]

---

## Fase 6 — Segundo ciclo: contacto y propuesta

> Referencia: [[Semáforo Onboarding#Azul Claro — Contacto y recopilación de datos]] · [[Semáforo Onboarding#Verde — Propuesta enviada]] · [[Propuesta Personalizada]]

### 6.1 — Nuevo contacto (Azul Claro)

Jueves 26 de junio. Sofía llama al hotel y habla directamente con Carlos Navarro. Él confirma interés inmediato. Sofía agenda una visita para el viernes 27.

Viernes 27 de junio. Sofía visita el hotel con Carlos y Mariana. Las necesidades han crecido: ahora requieren **8 Housekeepers, 3 Housemen y 2 personal de Lavandería** para cubrir la temporada alta completa.

Sofía actualiza el perfil del hotel con el nuevo contacto (Carlos Navarro, Director General) y las necesidades ampliadas.

> [!info] Semáforo Onboarding
> Azul Claro (mantiene) — Segundo contacto y visita
> **Fecha:** 2026-06-27 · **Responsable:** Sofía Méndez (BD) · **Comentario:** "Segunda visita realizada. Nuevo director confirma interés. Necesidades actualizadas: 8 HK, 3 HM, 2 LN."

### 6.2 — Segunda propuesta (Verde)

Sábado 28 de junio. Sofía elabora una nueva [[Propuesta Personalizada]] con la demanda actualizada:

| Componente | Detalle |
|---|---|
| Servicios ofrecidos | Staffing de Housekeeping y Lavandería |
| Posiciones | 8 [[Posiciones\|Housekeeper]], 3 [[Posiciones\|Houseman]], 2 [[Posiciones\|Laundry]] |
| Modelo de operación | Reclutamiento, asignación, supervisión por Oranje |
| Precios tentativos (pay rate) | $12.50/hr (HK), $11.00/hr (HM), $11.50/hr (LN) |
| Precios tentativos (bill rate) | $19.00/hr (HK), $16.50/hr (HM), $17.00/hr (LN) |
| Condiciones generales | Overtime a 1.5x, festivos a 2x, uniformes incluidos |

Sofía envía la propuesta. Carlos responde el martes 1 de julio: **"Nos interesa. Avancemos con los términos formales."**

> [!info] Semáforo Onboarding
> Azul Claro → **Verde** — Segunda propuesta enviada
> **Fecha:** 2026-06-28 · **Responsable:** Sofía Méndez (BD) · **Comentario:** "Segunda Propuesta Personalizada con demanda actualizada enviada a nuevo director."

> [!info] Semáforo Onboarding
> Verde → avance por interés confirmado
> **Fecha:** 2026-07-01 · **Responsable:** Sofía Méndez (BD) · **Comentario:** "Director acepta propuesta en principio. Solicita negociar términos específicos."

---

## Fase 7 — Seguimiento y Documento de T&C

> Referencia: [[Semáforo Onboarding#Amarillo — En seguimiento tras propuesta]] · [[Documento de Términos y Condiciones]]

### 7.1 — Creación del Documento de Términos y Condiciones (Amarillo)

Miércoles 2 de julio. Sofía, con apoyo de Ricardo Fuentes ([[Business Developer Coordinator]]), crea el [[Documento de Términos y Condiciones]] con los parámetros comerciales propuestos:

| Campo | Valor propuesto |
|---|---|
| Pay rate (Housekeeper) | $12.50/hr |
| Pay rate (Houseman) | $11.00/hr |
| Pay rate (Laundry) | $11.50/hr |
| Bill rate (Housekeeper) | $19.00/hr |
| Bill rate (Houseman) | $16.50/hr |
| Bill rate (Laundry) | $17.00/hr |
| Overtime | 1.5x bill rate después de 40 horas brutas semanales |
| Festivos | 2x bill rate en días festivos federales |
| Inicio de semana | Lunes |
| Fin de semana | Domingo |
| Fecha tentativa de inicio | 21 julio 2026 |

> [!info] Semáforo Onboarding
> Verde → **Amarillo** — En seguimiento tras propuesta
> **Fecha:** 2026-07-02 · **Responsable:** Sofía Méndez (BD) · **Comentario:** "Documento de T&C elaborado con apoyo del BDC. Pendiente presentar al hotel."

> [!warning] Regla de negocio
> En Amarillo, el BD o BDC crea el [[Documento de Términos y Condiciones]] con los campos obligatorios: pay rate, bill rate, overtime, festivos, calendario. El BDC apoya pero aún no tiene el rol decisorio exclusivo — ese llega en Rosa. — [[Semáforo Onboarding#Amarillo — En seguimiento tras propuesta]]

---

## Fase 8 — Negociación de términos

> Referencia: [[Semáforo Onboarding#Rosa — Negociación de términos]] · [[Reglas de Ventas#Conversión de prospecto a cliente]] · [[Trigger Automático de Conversión]] · [[Contrato]]

### 8.1 — Inicio de la negociación formal (Rosa)

Lunes 7 de julio. Sofía y Ricardo (BDC) se reúnen con Carlos Navarro y Mariana Vega en el Hotel Costa Esmeralda para presentar y negociar el Documento de T&C.

> [!info] Semáforo Onboarding
> Amarillo → **Rosa** — Negociación de términos
> **Fecha:** 2026-07-07 · **Responsable:** Sofía Méndez (BD) · **Comentario:** "Documento de T&C presentado al hotel. Inicia negociación formal."

### 8.2 — Rondas de negociación

**Ronda 1 — 7 de julio:**
Carlos objeta el bill rate de Housekeepers: $19.00/hr le parece alto comparado con su presupuesto. Solicita $17.00/hr. Los demás rates son aceptados.

**Análisis interno — 8 de julio:**
Ricardo (BDC) analiza los márgenes. Con un pay rate de $12.50/hr, el bill rate mínimo viable para Housekeepers es $18.00/hr. Ricardo prepara una contra-oferta.

**Ronda 2 — 9 de julio:**
Sofía y Ricardo presentan la contra-oferta: $18.25/hr para Housekeepers. Carlos acepta. Todos los términos quedan acordados.

### 8.3 — Términos definitivos

| Campo | Valor final |
|---|---|
| Pay rate (Housekeeper) | $12.50/hr |
| Pay rate (Houseman) | $11.00/hr |
| Pay rate (Laundry) | $11.50/hr |
| Bill rate (Housekeeper) | $18.25/hr |
| Bill rate (Houseman) | $16.50/hr |
| Bill rate (Laundry) | $17.00/hr |
| Overtime | 1.5x bill rate después de 40 hrs brutas semanales |
| Festivos | 2x bill rate en días festivos federales |
| Inicio de semana | Lunes |
| Fin de semana | Domingo |
| Vigencia | 21 julio 2026 — 20 julio 2027 (1 año) |
| Renovación | Automática por periodos anuales salvo aviso 30 días previos |

Ricardo (BDC) valida el Documento de T&C: todos los campos obligatorios están completos, los márgenes son viables.

> [!warning] Regla de negocio
> El [[Business Developer Coordinator]] valida los términos del [[Documento de Términos y Condiciones]] antes del cierre. — [[Reglas de Ventas#Documento de Términos y Condiciones]]

### 8.4 — Creación del Usuario del Hotel

Jueves 10 de julio. Antes de aprobar la conversión, Ricardo (BDC) crea el [[Usuario del Hotel]] en el sistema:

| Campo | Valor |
|---|---|
| Hotel | Hotel Costa Esmeralda |
| Zona | Noroeste |
| Director General | Carlos Navarro |
| Gerente de Operaciones | Mariana Vega |
| Email de acceso | operaciones@costaesmeralda.com |

> [!warning] Regla de negocio — Precondición obligatoria
> El [[Usuario del Hotel]] **debe** crearse en el sistema **antes** de disparar la conversión. Sin este paso, el Trigger Automático no puede ejecutarse. — [[Reglas de Ventas#Conversión de prospecto a cliente]]

### 8.5 — Aprobación de conversión por el BDC

Viernes 11 de julio. Ricardo Fuentes (BDC) da el **sí final**. Aprueba la conversión del Hotel Costa Esmeralda de prospecto a cliente activo.

> [!warning] Regla de negocio — Exclusividad del BDC
> **Solo** el [[Business Developer Coordinator]] puede aprobar la conversión de prospecto a cliente. Ningún otro rol tiene esta autoridad. — [[Reglas de Ventas#Conversión de prospecto a cliente]]

### 8.6 — Trigger Automático de Conversión

Al aprobar la conversión, el sistema ejecuta el [[Trigger Automático de Conversión]] — tres acciones en paralelo:

> [!tip] Acciones automáticas del sistema — [[Trigger Automático de Conversión]]
> 1. **Email de bienvenida** enviado a operaciones@costaesmeralda.com
> 2. **Notificación al BD:** Sofía Méndez recibe alerta "Hotel Costa Esmeralda convertido a cliente activo"
> 3. **Lista de prospectos:** Hotel Costa Esmeralda desaparece de la lista de prospectos

### 8.7 — Formalización del Contrato

El [[Contrato]] se formaliza a partir del Documento de T&C. Cada campo tiene un efecto directo en el sistema:

| Campo del Contrato | Valor | Efecto en el sistema |
|---|---|---|
| Pay rate | $12.50 / $11.00 / $11.50 | Cálculo de pagos al colaborador |
| Bill rate | $18.25 / $16.50 / $17.00 | Cálculo de [[Facturación al Hotel]] |
| Overtime | 1.5x bill rate | Reglas de tiempo extra en [[Timesheet]] |
| Festivos | 2x bill rate | Calendario de días festivos |
| Inicio/fin de semana | Lunes — Domingo | Estructura del [[Schedule]] semanal |
| Vigencia | 21 jul 2026 — 20 jul 2027 | Período de validez |
| Renovación | Automática anual, aviso 30 días | Términos de renovación |

> [!info] Semáforo Onboarding
> Rosa → **Naranja** — Acuerdo firmado, hotel cliente activo
> **Fecha:** 2026-07-11 · **Responsable:** Ricardo Fuentes (BDC) · **Comentario:** "Conversión aprobada. Usuario del Hotel creado. Trigger automático ejecutado. Contrato formalizado."

---

## Fase 9 — Hotel activo y handoff a operaciones

> Referencia: [[Semáforo Onboarding#Naranja — Acuerdo firmado, hotel cliente activo]] · [[Reglas de Ventas#Transición a Operaciones (Naranja)]] · [[Flujo de Requisición]]

### 9.1 — Cambio de responsabilidad (Naranja)

Con el Hotel Costa Esmeralda en status **Naranja**, la responsabilidad se redistribuye:

| Ámbito | Responsable | Rol |
|---|---|---|
| Operativo | Daniel Ortega | [[Inspector]] de zona Noroeste |
| Operativo | Reclutadoras | [[Reclutadora\|Reclutadoras]] (asignación de personal) |
| Comercial (referente) | Sofía Méndez | [[Business Developer]] asignada |
| Comercial (referente) | Ricardo Fuentes | [[Business Developer Coordinator]] supervisor |

Sofía y Ricardo ya no ejecutan operaciones para este hotel. Su rol es mantener la relación comercial y estar disponibles ante renegociaciones o disputas contractuales.

> [!warning] Regla de negocio
> **Naranja es el único status del [[Semáforo Onboarding]] que habilita al hotel para generar [[Requisición\|requisiciones]].** Antes de este status, el hotel es un prospecto comercial sin acceso operativo. — [[Reglas de Ventas#Transición a Operaciones (Naranja)]]

### 9.2 — La primera requisición

Lunes 14 de julio. Mariana Vega, ahora con acceso al sistema como [[Supervisor]] del hotel, crea la primera requisición de personal:

| # Posición | Posición | Cantidad | Modalidad | Fecha de inicio | Horario | Inglés |
|---|---|---|---|---|---|---|
| 1 | [[Posiciones\|Housekeeper]] | 5 | [[Modalidades de Contratación\|Tiempo completo]] | 21 jul 2026 | 07:00–15:00 | Básico |
| 2 | [[Posiciones\|Houseman]] | 3 | [[Modalidades de Contratación\|Tiempo completo]] | 21 jul 2026 | 07:00–15:00 | Básico |
| 3 | [[Posiciones\|Laundry]] | 2 | [[Modalidades de Contratación\|Tiempo completo]] | 21 jul 2026 | 06:00–14:00 | No requerido |

> [!tip] Acciones automáticas del sistema
> - Se genera el número de requisición: **202607141015A3**
> - Carlos Navarro (Director General) autoriza la requisición
> - **Cálculo de urgencia:** fecha de autorización (14 jul 10:30) vs fecha de inicio (21 jul 07:00) ≈ 165 horas → **Verde fuerte** (Normal, >120h) — [[Semáforo de Urgencia de Requisición]]
> - **Inspector asignado:** Daniel Ortega — automático según zona Noroeste
> - La requisición aparece en la bandeja de [[Self-Pick de Requisiciones]], priorizada por urgencia

> [!info] Conexión con el ciclo operativo
> La requisición ahora sigue el [[Flujo de Requisición]]. Una [[Reclutadora]] la tomará de la bandeja vía [[Self-Pick de Requisiciones]] y cubrirá las posiciones con colaboradores del [[Pool de Colaboradores]].
>
> **El ciclo de Ventas ha cumplido su función: el hotel está activo y generando requisiciones.**

---

## Fase 10 — Supervisión QA: cierre del ciclo

> Referencia: [[Métricas y KPIs por Departamento#Ventas]] · [[Indicador de Calidad]] · [[Reglas de Ventas#Supervisión de Calidad (QA)]]

El [[Operador de QA]] (Operador 4), asignado de forma fija al departamento de [[Ventas/Ventas|Ventas]], ha observado todo el ciclo sin ejecutar ninguna acción operativa. Su rol es exclusivamente de observación, medición y retroalimentación.

### Resumen de KPIs medidos

| # | KPI | Resultado en esta simulación | Meta | Estado |
|---|---|---|---|---|
| 1 | **Tasa de conversión** | +1 hotel convertido en el periodo | ≥ 25% | ✓ Contribuye a meta |
| 2 | **Ciclo promedio de onboarding** | 39 días (2 jun — 11 jul), incluye 14 días en Rojo | ≤ 45 días | ✓ Dentro de meta |
| 3 | **Tasa de estancamiento** | 0 días en Café | ≤ 10% | ✓ Sin estancamiento |
| 4 | **Tasa de pérdida** | Hotel reactivado desde Rojo — no cuenta como pérdida definitiva | ≤ 20% | ✓ Recuperado |
| 5 | **Tasa de reactivación exitosa** | Hotel reactivado desde Rojo y convertido a Naranja (superó Verde) | ≥ 40% | ✓ Reactivación exitosa |

> [!warning] Regla de negocio
> QA no ejecuta la operación de Ventas; solo observa, mide y retroalimenta. Si el [[Indicador de Calidad]] del departamento alcanza Rojo sin mejora, el [[Manager de QA]] escala a dirección. — [[Reglas de Ventas#Supervisión de Calidad (QA)]]

El [[Indicador de Calidad]] del departamento de Ventas se mantiene en **Verde** (Calidad óptima). No se emiten observaciones formales.

---

## Resumen de transiciones del Semáforo Onboarding

| Fecha | Status | Acción | Responsable |
|---|---|---|---|
| 2 jun 2026 | **Gris** | Hotel identificado en zona Noroeste | Sofía (BD) |
| 5 jun 2026 | **Azul Claro** | Visita en frío, perfil creado | Sofía (BD) |
| 6 jun 2026 | **Verde** | Propuesta Personalizada enviada | Sofía (BD) |
| 11 jun 2026 | **Rojo** | Hotel rechaza propuesta | Sofía (BD) |
| 25 jun 2026 | **Azul Claro** | Reactivación por cambio de director | Sofía (BD) |
| 28 jun 2026 | **Verde** | Segunda propuesta enviada | Sofía (BD) |
| 2 jul 2026 | **Amarillo** | Documento de T&C elaborado | Sofía (BD) + Ricardo (BDC) |
| 7 jul 2026 | **Rosa** | Negociación formal inicia | Sofía (BD) + Ricardo (BDC) |
| 11 jul 2026 | **Naranja** | Conversión aprobada, hotel activo | Ricardo (BDC) |

```mermaid
graph LR
    Gris -->|BD identifica| AC1[Azul Claro]
    AC1 -->|Propuesta enviada| V1[Verde]
    V1 -->|Hotel rechaza| Rojo
    Rojo -->|Reactivación| AC2[Azul Claro]
    AC2 -->|2da propuesta| V2[Verde]
    V2 -->|Hotel interesado| Amarillo
    Amarillo -->|Negociación formal| Rosa
    Rosa -->|BDC aprueba conversión| Naranja

    style Gris fill:#808080,color:#fff
    style AC1 fill:#87CEEB,color:#000
    style AC2 fill:#87CEEB,color:#000
    style V1 fill:#228B22,color:#fff
    style V2 fill:#228B22,color:#fff
    style Rojo fill:#DC143C,color:#fff
    style Amarillo fill:#FFD700,color:#000
    style Rosa fill:#FF69B4,color:#fff
    style Naranja fill:#FF8C00,color:#fff
```

---

## Módulos y conceptos referenciados

| Módulo | Referencia |
|---|---|
| Ventas | [[Ventas/Ventas\|Ventas]] · [[Reglas de Ventas]] |
| Roles de Ventas | [[Business Developer]] · [[Business Developer Coordinator]] |
| Onboarding | [[Flujo de Onboarding]] · [[Semáforo Onboarding]] |
| Propuesta y cierre | [[Propuesta Personalizada]] · [[Documento de Términos y Condiciones]] · [[Trigger Automático de Conversión]] · [[Usuario del Hotel]] · [[Contrato]] |
| Calidad | [[Operador de QA]] · [[Manager de QA]] · [[Indicador de Calidad]] · [[Métricas y KPIs por Departamento]] |
| Catálogos | [[Zonas]] · [[Posiciones]] · [[Departamentos del Hotel]] · [[Modalidades de Contratación]] |
| Operaciones (handoff) | [[Inspector]] · [[Reclutadora]] · [[Requisición]] · [[Flujo de Requisición]] · [[Self-Pick de Requisiciones]] · [[Schedule]] · [[Timesheet]] · [[Facturación al Hotel]] |
| Semáforos operativos | [[Semáforo de Requisición]] · [[Semáforo de Urgencia de Requisición]] · [[Pool de Colaboradores]] |

---

## Simulaciones relacionadas

- [[Simulación - Punto de Vista de Inspección]] — Continúa la historia del Hotel Costa Esmeralda desde la perspectiva del Inspector Daniel Ortega, quien recibe el handoff operativo tras la conversión a cliente.
- [[Simulación - Punto de Vista del Hotel]] — Narra el ciclo completo de un hotel como cliente, incluyendo las fases comerciales que aquí se detallan desde Ventas.
- [[Simulación - Punto de Vista de Reclutamiento]] — Cubre el proceso de staffing que se activa una vez que el hotel genera su primera requisición en status Naranja.
- [[Simulación - Ciclo de Vida del Colaborador]] — Recorre los estados del colaborador asignado al hotel, desde su ingreso al Pool hasta su operación diaria.
