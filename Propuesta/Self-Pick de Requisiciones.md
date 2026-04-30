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
- **Alerta de 24 horas** — si una requisición lleva más de 24 horas sin ser tomada, el [[Manager de Reclutamiento]] recibe alerta y la asigna manualmente.

## Intervención del Manager

El [[Manager de Reclutamiento]] solo interviene en casos excepcionales:

- Requisición varada sin tomar (después de 24 horas)
- Balanceo entre grupos
- Líder ausente
- Corrección de error de asignación

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
