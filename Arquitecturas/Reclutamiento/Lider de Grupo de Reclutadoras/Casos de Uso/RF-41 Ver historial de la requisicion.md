---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-41
---

# 🪪 ID: RF-41
🏷️ **Nombre:** Ver Historial de la requisición (timeline)

**Historia:**
Como una requisición puede tener varios reclutadores participantes trabajándola a la vez (modelo colaborativo, RR-15), el Líder necesita ver **quién hizo qué y cuándo**. Abre el detalle de la requisición y entra a la sección **Historial**: un timeline cronológico **inmutable** que muestra cada evento con su **actor** (rol + nombre) y timestamp. Sirve para auditar y dar seguimiento sin depender de un dueño único.

**Criterios de aceptación:**
El Historial muestra cronológicamente quién **tomó / se unió**, quién **salió**, quién **asignó/desasignó** cada colaborador a qué posición, y quién la **cerró**, cada evento con **fecha y autor** (AC-24, RR-16). El timeline es **inmutable**: los eventos no se editan ni se borran. Es visible para todos los reclutadores participantes, el Líder de Grupo y el [[Manager de Reclutamiento]]. El orden es estrictamente cronológico.

> [!note]
> En el Historial, "colaborador" se refiere al trabajador del Pool asignado a una posición; las personas que trabajan la requisición son los **reclutadores participantes**.

**Documentación:**
- PRD: PRD-RECL-03 Líder de Grupo
- Flow: Historial / trazabilidad de la requisición
- Prototipo: (link de Figma)

**Flujo:**
`Mis Requisiciones → Detalle de la requisición` → MANUAL → `Click en "Ver historial"` → AUTOMATICO → `Abre el timeline cronológico inmutable con cada evento (tomó/se unió, salió, asignó/desasignó colaborador↔posición, cerró) + actor (rol + nombre) + timestamp`
