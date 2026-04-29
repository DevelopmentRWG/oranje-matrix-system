---
tags:
  - modulo/ventas
aliases:
  - Reglas de Ventas
---

# Reglas de Ventas

Consolidación de todas las reglas de negocio que aplican al departamento de Ventas dentro del sistema Oranje. Referencia cruzada con [[Reglas de Negocio]] (concentrado general del sistema).

## Jerarquía del departamento

| Rol | Función |
|---|---|
| [[Ventas/Roles/Business Developer Coordinator\|Business Developer Coordinator (BDC)]] | Supervisa a los BD en su territorio. Valida términos, aprueba conversiones y gestiona estancamientos |
| [[Ventas/Roles/Business Developer\|Business Developer (BD)]] | Ejecutor comercial en campo. Identifica prospectos, elabora propuestas y da seguimiento |

## Ciclo del Semáforo Onboarding

El proceso de captación de un hotel sigue el [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]], documentado en detalle en el [[Ventas/Onboarding-Hotel/Flujo de Onboarding|Flujo de Onboarding]].

| Status | Descripción | Responsable principal |
|---|---|---|
| **Gris** | Prospecto identificado sin contacto | [[Ventas/Roles/Business Developer\|BD]] |
| **Azul Claro** | Perfil creado, datos recopilados, visita en frío realizada | [[Ventas/Roles/Business Developer\|BD]] |
| **Verde** | Propuesta Personalizada elaborada y enviada; seguimiento activo | [[Ventas/Roles/Business Developer\|BD]] |
| **Amarillo** | Documento de T&C creado; seguimiento post-propuesta | [[Ventas/Roles/Business Developer\|BD]] + [[Ventas/Roles/Business Developer Coordinator\|BDC]] (apoyo) |
| **Rosa** | Negociación de términos; validación final y cierre | [[Ventas/Roles/Business Developer\|BD]] + [[Ventas/Roles/Business Developer Coordinator\|BDC]] |
| **Naranja** | Hotel cliente activo; pasa a operaciones | [[Inspector]] + [[Reclutadora]] (operativo) / BD y BDC (referente comercial) |
| **Rojo** | Rechazo del hotel; decisión de reactivar o archivar | [[Ventas/Roles/Business Developer\|BD]] |
| **Negro** | Cliente pausado o inactivo | [[Ventas/Roles/Business Developer Coordinator\|BDC]] |
| **Café** | Estancamiento; puente de desbloqueo | [[Ventas/Roles/Business Developer Coordinator\|BDC]] |

## Propuesta Personalizada

- Se elabora y envía en status **Verde** del [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]].
- Se ajusta o retoma desde status **Café** cuando hay estancamiento.
- Referencia: [[Ventas/Onboarding-Hotel/Conceptos/Propuesta Personalizada|Propuesta Personalizada]].

## Documento de Términos y Condiciones

| Fase | Status | Responsable |
|---|---|---|
| Creación | **Amarillo** | [[Ventas/Roles/Business Developer\|BD]] o [[Ventas/Roles/Business Developer Coordinator\|BDC]] |
| Negociación | **Rosa** | [[Ventas/Roles/Business Developer\|BD]] + [[Ventas/Roles/Business Developer Coordinator\|BDC]] |
| Validación final | **Rosa** (previo al cierre) | [[Ventas/Roles/Business Developer Coordinator\|BDC]] |

Contenido obligatorio:

| Campo |
|---|
| Pay rate |
| Bill rate |
| Overtime |
| Festivos |
| Calendario |

- Referencia: [[Ventas/Onboarding-Hotel/Conceptos/Documento de Términos y Condiciones|Documento de Términos y Condiciones]].

## Contrato

El [[Core/Módulos/Contrato|Contrato]] resulta del cierre exitoso en status **Rosa**:

- Insumo obligatorio: [[Ventas/Onboarding-Hotel/Conceptos/Documento de Términos y Condiciones|Documento de Términos y Condiciones]].
- El [[Ventas/Roles/Business Developer Coordinator|BDC]] valida antes del cierre.

| Campo del Contrato | Efecto en el sistema |
|---|---|
| Pay rate | Cálculo de pagos al colaborador |
| Bill rate | Cálculo de facturación al hotel |
| Overtime | Reglas de tiempo extra |
| Festivos | Calendario de días festivos |
| Inicio y fin de semana | Configura la estructura del [[Core/Módulos/Schedule\|Schedule]] semanal del hotel |
| Vigencia | Período de validez del contrato |
| Renovación | Términos de renovación |

## Conversión de prospecto a cliente

> [!important] **Solo** el [[Ventas/Roles/Business Developer Coordinator\|BDC]] puede aprobar la conversión de prospecto a cliente.

**Precondición obligatoria:** creación del [[Ventas/Onboarding-Hotel/Conceptos/Usuario del Hotel|Usuario del Hotel]] en el sistema antes de disparar la conversión.

### Trigger Automático de Conversión

Al aprobar la conversión, el sistema ejecuta automáticamente tres acciones en paralelo:

1. Envía email de bienvenida al hotel.
2. Notifica al [[Ventas/Roles/Business Developer\|BD]] asignado.
3. El hotel desaparece de la lista de prospectos.

- Referencia: [[Ventas/Onboarding-Hotel/Conceptos/Trigger Automático de Conversión|Trigger Automático de Conversión]].

## Reactivaciones

| Status origen | Destino de reactivación | Responsable |
|---|---|---|
| **Rojo** (rechazo) | → **Azul Claro** | [[Ventas/Roles/Business Developer\|BD]] |
| **Negro** (pausado/inactivo) | → **Azul Claro** | [[Ventas/Roles/Business Developer Coordinator\|BDC]] |
| **Café** (estancamiento) | → **Azul Claro** | [[Ventas/Roles/Business Developer Coordinator\|BDC]] |

> [!note] **Café** no es un status terminal. Es un puente de desbloqueo operado exclusivamente por el [[Ventas/Roles/Business Developer Coordinator\|BDC]], quien investiga la causa del estancamiento y da solución para retomar.

## Transición a Operaciones (Naranja)

> [!important] **Naranja** es el único status del [[Core/Módulos/Semáforos/Semáforo Onboarding\|Semáforo Onboarding]] que habilita al hotel para generar requisiciones.

- Al alcanzar Naranja, el hotel pasa a responsabilidad operativa del [[Inspector]] y las [[Reclutadora|Reclutadoras]].
- El [[Ventas/Roles/Business Developer\|BD]] y el [[Ventas/Roles/Business Developer Coordinator\|BDC]] quedan como **referentes comerciales**, no como operativos.
- Se inicia el ciclo operativo: Requisiciones → cobertura → [[Core/Módulos/Schedule\|Schedule]] → [[Timesheet]].

## Trazabilidad

> [!info] Todo cambio de status en el [[Core/Módulos/Semáforos/Semáforo Onboarding\|Semáforo Onboarding]] queda registrado con: **fecha, responsable y comentario**.

## Supervisión de Calidad (QA)

- Un [[QA/Operador de QA\|Operador de QA]] está asignado de forma fija al departamento de Ventas.
- QA **no ejecuta** la operación de Ventas; solo observa, mide y retroalimenta.
- Si el [[Core/Módulos/Semáforos/Indicador de Calidad\|Indicador de Calidad]] del departamento alcanza estado **Rojo** sin mejora tras notificación, el Manager de QA escala a dirección.

## Resumen de responsabilidades por rol

| Acción | [[Ventas/Roles/Business Developer\|BD]] | [[Ventas/Roles/Business Developer Coordinator\|BDC]] |
|---|---|---|
| Identificar prospecto (Gris) | Sí | No |
| Crear perfil del hotel (Azul Claro) | Sí | No |
| Elaborar Propuesta Personalizada (Verde) | Sí | No |
| Crear Documento de T&C (Amarillo) | Sí | Apoyo |
| Negociar términos (Rosa) | Sí | Sí |
| Validar T&C y dar sí final | No | Sí (exclusivo) |
| Crear Usuario del Hotel | No | Sí (exclusivo) |
| Aprobar conversión a cliente | No | Sí (exclusivo) |
| Gestionar rechazo (Rojo) | Sí | No |
| Desbloquear estancamiento (Café) | No | Sí |
| Gestionar cliente pausado (Negro) | No | Sí |
| Referente comercial post-conversión (Naranja) | Sí | Sí |

## Relacionado

- [[Reglas de Negocio]]
- [[Ventas/Roles/Business Developer|Business Developer]]
- [[Ventas/Roles/Business Developer Coordinator|Business Developer Coordinator]]
- [[Ventas/Onboarding-Hotel/Flujo de Onboarding|Flujo de Onboarding]]
- [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]]
- [[Ventas/Onboarding-Hotel/Conceptos/Propuesta Personalizada|Propuesta Personalizada]]
- [[Ventas/Onboarding-Hotel/Conceptos/Documento de Términos y Condiciones|Documento de Términos y Condiciones]]
- [[Ventas/Onboarding-Hotel/Conceptos/Trigger Automático de Conversión|Trigger Automático de Conversión]]
- [[Ventas/Onboarding-Hotel/Conceptos/Usuario del Hotel|Usuario del Hotel]]
- [[Core/Módulos/Contrato|Contrato]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Timesheet]]
- [[Core/Módulos/Semáforos/Indicador de Calidad|Indicador de Calidad]]
- [[Inspector]]
- [[Reclutadora]]
