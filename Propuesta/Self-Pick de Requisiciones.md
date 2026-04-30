---
tags:
  - propuesta
  - modulo/reclutamiento
aliases:
  - Propuesta Self-Pick
  - Self-Pick de Requisiciones
status: aprobada
---

# Self-Pick de Requisiciones

Modelo de asignación de requisiciones en el módulo de [[Reclutamiento/Reclutamiento|Reclutamiento]]. Las [[Reclutadora|Reclutadoras]] y [[Reclutamiento/Líder de Grupo de Reclutadoras|Líderes de Grupo]] toman libremente las requisiciones de una bandeja compartida, sin intermediación del [[Manager de Reclutamiento]].

## Flujo

```
Manager del Hotel autoriza requisición
      ↓
Llega al sistema y queda en cola "Autorizadas" (visible a todo Reclutamiento)
      ↓
La cola se prioriza automáticamente por el Semáforo de Urgencia de Requisición
      ↓
Reclutadoras y Líderes de Grupo toman libremente las requisiciones
      ↓
Al tomar, la requisición pasa a Amarillo (En proceso) en el Semáforo de Requisición
      ↓
La Reclutadora cubre con colaboradores del Pool
```

## Reglas operativas

- **Sin límite de requisiciones simultáneas** — cada Reclutadora atiende todas las que le lleguen según la demanda.
- **Sin restricciones por zona o idioma** — las Reclutadoras reciben candidatos de todas partes y los asignan según las [[Core/Módulos/Reglas de Negocio|Reglas de Negocio]].
- **Bandeja global con filtros** — todas las Reclutadoras ven todas las requisiciones disponibles. Pueden filtrar por zona, urgencia, posición y otros criterios, pero la bandeja no está segmentada por grupo ni por Reclutadora.
- **Concurrencia: primera en confirmar gana** — si dos Reclutadoras intentan tomar la misma requisición al mismo tiempo, el sistema la bloquea para la primera en confirmar. La segunda recibe un mensaje indicando que la requisición ya fue tomada.
- **Auto-asignación a las 24 horas** — si una requisición lleva más de 24 horas sin ser tomada (contadas desde la autorización), el sistema la asigna automáticamente a la Reclutadora con menor carga de requisiciones activas en ese momento. El [[Manager de Reclutamiento]] no recibe notificación; el proceso es transparente.

## Intervención del Manager

El [[Manager de Reclutamiento]] solo interviene en casos excepcionales:

- Balanceo entre grupos
- Líder ausente
- Corrección de error de asignación

## Escalación al Líder de Grupo

Cuando la [[Reclutadora]] no encuentra match en el [[Pool de Colaboradores]] y ha buscado activamente fuera del sistema (redes sociales, grupos externos, etc.), aplica un timeout de escalación hacia el [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo]]. El plazo depende del estado del [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición|Semáforo de Urgencia de Requisición]]:

| Color de urgencia | Condición | Plazo para escalar |
|---|---|---|
| Rojo | Menos de 72h para inicio | 24h sin cubrir |
| Amarillo | Entre 72h y 120h para inicio | 48h sin cubrir |
| Verde fuerte | Más de 120h para inicio | 72h sin cubrir |

> [!important] Durante todo este proceso la requisición permanece en estado **Amarillo** en el [[Core/Módulos/Semáforos/Semáforo de Requisición|Semáforo de Requisición]]. La escalación va al [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo]], no al [[Manager de Reclutamiento]].

## Documentos actualizados

Los siguientes archivos del vault reflejan este modelo:

- [[Reclutamiento/Reglas de Reclutamiento|Reglas de Reclutamiento]] — sección "Requisiciones — recepción y asignación (Self-Pick)"
- [[Core/Módulos/Reglas de Negocio|Reglas de Negocio]] — secciones "Distribución de requisiciones" y "Asignación"
- [[Core/Módulos/Semáforos/Semáforo de Requisición|Semáforo de Requisición]] — trigger Verde → Amarillo
- [[Core/Módulos/Requisicion/Flujo de Requisición|Flujo de Requisición]] — sección 5
- [[Reclutadora]] — primera responsabilidad
- [[Manager de Reclutamiento]] — responsabilidades

## Relacionado

- [[Reclutamiento/Reglas de Reclutamiento|Reglas de Reclutamiento]]
- [[Core/Módulos/Reglas de Negocio|Reglas de Negocio]]
- [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición|Semáforo de Urgencia de Requisición]]
- [[Core/Módulos/Semáforos/Semáforo de Requisición|Semáforo de Requisición]]
- [[Manager de Reclutamiento]]
- [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo de Reclutadoras]]
- [[Reclutadora]]
