---
tags:
  - modulo/customer-service
  - flujo
aliases:
  - Flujo de Customer Service
  - Flujo de Atención al Cliente
---

# Flujo de Customer Service

Proceso paso a paso para la atención de solicitudes del hotel cliente activo. El flujo cubre desde la recepción de una solicitud hasta su cierre o escalamiento. Aplica únicamente a hoteles en status **Naranja** del [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]].

## Paso 1 — Recepción de la solicitud

**Responsable:** [[Customer Service/Agente de Customer Service|Agente de Customer Service]]

El hotel contacta a Customer Service a través de los canales habilitados. El interlocutor del hotel puede ser el [[Hotel/Manager General|Manager General]], el [[Hotel/Manager de Área|Manager de Área]] o el [[Hotel/Supervisor|Supervisor]].

**Acción:** el Agente registra la solicitud con los siguientes datos:
- Hotel y contacto.
- Fecha y hora de recepción.
- Descripción de la solicitud.
- Categoría (consulta, queja, incidencia, solicitud operativa).

**Avance →** al registrar la solicitud, pasa a Paso 2.

## Paso 2 — Clasificación y respuesta inicial

**Responsable:** [[Customer Service/Agente de Customer Service|Agente de Customer Service]]

El Agente evalúa la solicitud y determina si puede resolverla directamente o si requiere coordinación con otro departamento.

**Decisión: ¿El Agente puede resolver directamente?**

- **SÍ →** el Agente resuelve, documenta la solución y pasa a Paso 5 (Cierre).
- **NO →** pasa a Paso 3 (Coordinación interdepartamental).

**Decisión: ¿La solicitud involucra una disputa comercial o riesgo de transición a Negro?**

- **SÍ →** escalamiento inmediato al [[Customer Service/Customer Service Manager|Customer Service Manager]] (Paso 4).

## Paso 3 — Coordinación interdepartamental

**Responsable:** [[Customer Service/Agente de Customer Service|Agente de Customer Service]]

El Agente contacta al departamento interno correspondiente para obtener la información o acción necesaria:

| Tipo de incidencia | Departamento a contactar | Contacto |
|---|---|---|
| Colaborador no se presentó / problemas de desempeño | [[Inspección/Inspección\|Inspección]] | [[Inspección/Coordinador\|Coordinador]] |
| Cobertura de posiciones / asignación de personal | [[Reclutamiento/Reclutamiento\|Reclutamiento]] | [[Manager de Reclutamiento]] |
| Dudas de facturación o pagos | Contabilidad | [[Manager de Contabilidad]] |
| Temas contractuales o comerciales | [[Ventas/Ventas\|Ventas]] | [[Ventas/Roles/Business Developer Coordinator\|BDC]] |

**Acción:** el Agente documenta la coordinación realizada y la respuesta obtenida.

**Decisión: ¿Se obtuvo resolución del departamento?**

- **SÍ →** el Agente comunica la resolución al hotel y pasa a Paso 5 (Cierre).
- **NO →** el caso se escala al [[Customer Service/Customer Service Manager|Customer Service Manager]] (Paso 4).

## Paso 4 — Escalamiento

El escalamiento sigue la jerarquía definida en las [[Customer Service/Reglas de Customer Service|Reglas de Customer Service]]:

### Nivel 2 — Customer Service Manager

**Responsable:** [[Customer Service/Customer Service Manager|Customer Service Manager]]

Recibe casos que el Agente no pudo resolver o que involucran múltiples departamentos.

**Acciones:**
- Revisa el historial del caso.
- Coordina directamente con los responsables de los departamentos involucrados.
- Resuelve el caso y comunica al hotel.

**Decisión: ¿Se resolvió?**

- **SÍ →** pasa a Paso 5 (Cierre).
- **NO →** escala al Nivel 3.

### Nivel 3 — Business Developer Coordinator

**Responsable:** [[Ventas/Roles/Business Developer Coordinator|Business Developer Coordinator]]

Recibe casos con componente comercial, contractual o con riesgo de pérdida de cliente.

**Acciones:**
- Evalúa el impacto comercial.
- Negocia solución con el hotel.
- Coordina ajustes contractuales si aplica.

**Decisión: ¿Se resolvió?**

- **SÍ →** pasa a Paso 5 (Cierre).
- **NO →** escala al Nivel 4 (Dirección General).

### Nivel 4 — Dirección General

Casos sin resolución en niveles anteriores o con riesgo reputacional.

> [!warning] Si la disputa no se resuelve y el hotel decide pausar o terminar la relación, el [[Ventas/Roles/Business Developer Coordinator|BDC]] ejecuta la transición a status **Negro** en el [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]]. Customer Service no puede modificar el status del semáforo.

## Paso 5 — Cierre

**Responsable:** [[Customer Service/Agente de Customer Service|Agente de Customer Service]] o [[Customer Service/Customer Service Manager|Customer Service Manager]] (según quién resolvió)

**Acciones:**
- Documenta la resolución del caso.
- Confirma con el hotel que la solicitud fue atendida.
- Cierra el caso en el sistema.

## Puntos clave

- Customer Service **no puede modificar** el status del [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]]; solo reporta y escala.
- Customer Service **no sustituye** la operación de ningún departamento; coordina, canaliza y da seguimiento.
- Toda solicitud debe quedar documentada independientemente de si se resuelve en Paso 2 o llega a Paso 4.
- Los casos con disputa comercial siempre se escalan de forma inmediata al [[Customer Service/Customer Service Manager|CS Manager]], sin esperar el ciclo normal.

## Relacionado

- [[Customer Service/Customer Service|Customer Service]]
- [[Customer Service/Reglas de Customer Service|Reglas de Customer Service]]
- [[Customer Service/Customer Service Manager|Customer Service Manager]]
- [[Customer Service/Agente de Customer Service|Agente de Customer Service]]
- [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]]
- [[Ventas/Roles/Business Developer Coordinator|Business Developer Coordinator]]
