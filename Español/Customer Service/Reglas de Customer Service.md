---
tags:
  - modulo/customer-service
aliases:
  - Reglas de Customer Service
  - Reglas de CS
---

# Reglas de Customer Service

Consolidación de las reglas de negocio que aplican al departamento de Customer Service dentro del sistema Oranje. Referencia cruzada con [[Reglas de Negocio]] (concentrado general del sistema).

## Jerarquía del departamento

| Rol | Función |
|---|---|
| [[Customer Service/Customer Service Manager\|Customer Service Manager]] | Supervisa agentes, gestiona escalamientos y reporta métricas de satisfacción |
| [[Customer Service/Agente de Customer Service\|Agente de Customer Service]] | Primer punto de contacto; recibe, documenta y resuelve solicitudes del hotel |

## Jerarquía de escalamiento

El escalamiento sigue un orden definido según la gravedad y tipo del caso:

```
Agente de CS → CS Manager → Business Developer Coordinator → Dirección
```

| Nivel | Responsable | Criterio de escalamiento |
|---|---|---|
| **1 - Atención directa** | [[Customer Service/Agente de Customer Service\|Agente de CS]] | Consultas generales, solicitudes operativas simples |
| **2 - Supervisión** | [[Customer Service/Customer Service Manager\|CS Manager]] | Casos sin resolución en tiempo, quejas recurrentes, múltiples departamentos involucrados |
| **3 - Comercial** | [[Ventas/Roles/Business Developer Coordinator\|BDC]] | Disputas contractuales, riesgo de pérdida de cliente, temas de facturación no resueltos |
| **4 - Dirección** | Dirección General | Casos sin resolución en niveles anteriores, riesgo reputacional |

## Relación con el Semáforo Onboarding

- Customer Service opera exclusivamente con hoteles en status **Naranja** (cliente activo) del [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]].
- Si una disputa comercial gestionada por Customer Service no se resuelve y el hotel decide pausar o terminar la relación, el [[Ventas/Roles/Business Developer Coordinator|BDC]] es quien ejecuta la transición a status **Negro**.
- Customer Service **no** puede modificar el status del [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]]; solo reporta y escala.

## Límites del departamento

> [!important] Customer Service no sustituye la operación de ningún departamento. Coordina, canaliza y da seguimiento, pero la ejecución corresponde al departamento responsable.

- **No crea ni aprueba** [[Requisición|requisiciones]] — eso es del [[Hotel/Hotel|Hotel]].
- **No asigna** colaboradores — eso es de [[Reclutamiento/Reclutamiento|Reclutamiento]].
- **No inspecciona** en sitio — eso es de [[Inspección/Inspección|Inspección]].
- **No capta** hoteles nuevos — eso es de [[Ventas/Ventas|Ventas]].
- **No modifica** contratos ni términos comerciales — eso es del [[Ventas/Roles/Business Developer Coordinator|BDC]].

## Supervisión de Calidad (QA)

- Un [[Operador de QA]] está asignado de forma fija al departamento de Customer Service.
- QA **no ejecuta** la operación de Customer Service; solo observa, mide y retroalimenta.
- Si el [[Core/Módulos/Semáforos/Indicador de Calidad|Indicador de Calidad]] del departamento alcanza estado **Rojo** sin mejora tras notificación, el [[Manager de QA]] escala a dirección.

## Relacionado

- [[Reglas de Negocio]]
- [[Customer Service/Customer Service Manager|Customer Service Manager]]
- [[Customer Service/Agente de Customer Service|Agente de Customer Service]]
- [[Customer Service/Customer Service|Customer Service]]
- [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]]
- [[Ventas/Roles/Business Developer Coordinator|Business Developer Coordinator]]
- [[Core/Módulos/Semáforos/Indicador de Calidad|Indicador de Calidad]]
- [[Hotel/Hotel|Hotel]]
