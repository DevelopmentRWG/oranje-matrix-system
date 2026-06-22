---
tags:
  - propuesta
  - modulo/reclutamiento
aliases:
  - Self-Pick
  - Self-Pick de Requisiciones
status: aprobada
---

# Self-Pick de Requisiciones

Modelo de asignación de requisiciones en el módulo de [[Reclutamiento/Reclutamiento|Reclutamiento]]. Las [[Reclutadora|Reclutadoras]] y [[Reclutamiento/Líder de Grupo de Reclutadoras|Líderes de Grupo]] toman libremente las requisiciones de una bandeja compartida, sin intermediación del [[Manager de Reclutamiento]].

## Flujo

```
Manager de Área autoriza requisición
      ↓
Llega al sistema y queda en cola "Autorizadas" (visible a todo Reclutamiento)
      ↓
La cola se prioriza automáticamente por el Semáforo de Urgencia de Requisición
      ↓
Reclutadoras y Líderes de Grupo toman libremente las requisiciones
      ↓
Al tomar, la requisición pasa a Amarillo (En proceso) en el Semáforo de Requisición
      ↓
¿Ya hay reclutadores trabajándola? → otro reclutador puede UNIRSE
(se agrega como reclutador participante; NO bloquea, NO desplaza, NO resetea)
      ↓
Varios reclutadores participantes cubren con colaboradores del Pool
(avance compartido; lock solo a nivel posición/slot)
      ↓
Cada reclutador puede SALIR; la requisición sigue Amarillo si quedan otros,
y vuelve a Autorizada solo cuando sale el ÚLTIMO reclutador
```

## Reglas operativas

- **Sin límite de requisiciones simultáneas** — cada Reclutadora atiende todas las que le lleguen según la demanda.
- **Sin restricciones por zona o idioma** — las Reclutadoras reciben candidatos de todas partes y los asignan según las [[Core/Módulos/Reglas de Negocio|Reglas de Negocio]].
- **Bandeja global con filtros** — todas las Reclutadoras ven todas las requisiciones disponibles. Pueden filtrar por zona, urgencia, posición y otros criterios, pero la bandeja no está segmentada por grupo ni por Reclutadora.
- **Modelo colaborativo (RR-15)** — una requisición puede tener **varios reclutadores participantes** trabajándola a la vez; no hay dueño único. Tomar una requisición **ya tomada NO la transfiere ni la bloquea**: el reclutador se **une** (acción "Unirme") como participante adicional, sin desplazar a los existentes ni retroceder el semáforo. Nadie "pierde" la requisición.
- **Salir (no liberar)** — un reclutador participante puede **salir** (acción "Salir"); se retira solo a él. La requisición sigue **Amarillo** (En proceso) si quedan otros reclutadores y **no se resetea** lo que otros ya asignaron; solo vuelve a **Autorizada** cuando sale el **último** reclutador.
- **Lock solo a nivel posición/slot** — el avance de cobertura se **comparte** entre todos los reclutadores participantes. El lock de concurrencia opera a nivel de **posición/slot**, no de la requisición completa: si dos reclutadores asignan la misma posición, **gana el primero** y el segundo ve "posición ya cubierta". Dos reclutadores no asignan el mismo [[Pool de Colaboradores|colaborador]] a la misma posición.
- **Auto-asignación a las 24 horas** — si una requisición lleva más de 24 horas sin ser tomada (contadas desde la autorización), el sistema la asigna automáticamente a la Reclutadora con menor carga de requisiciones activas en ese momento (queda como reclutador participante inicial). El [[Manager de Reclutamiento]] no recibe notificación; el proceso es transparente.

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

## Historial de la requisición

Cada requisición mantiene un **timeline cronológico inmutable** con **actor** (rol y nombre) y timestamp de cada acción (RR-16):

- Quién la **tomó** y quién **se unió** después como reclutador participante.
- Quién **salió** de la requisición.
- Quién **asignó** o **desasignó** qué [[Pool de Colaboradores|colaborador]] a qué posición/slot.
- Cambios de status y quién la **cerró**.

El historial es **visible para todos los reclutadores participantes, el [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo]] y el [[Manager de Reclutamiento]]**. Da trazabilidad completa del trabajo colaborativo sin que ningún reclutador pierda su aporte. Ver RF-41.

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
- [[Pool de Colaboradores]]
- [[Core/Módulos/Requisicion/Requisición|Requisición]]
