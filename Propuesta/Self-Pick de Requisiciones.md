---
tags:
  - propuesta
  - modulo/reclutamiento
aliases:
  - Propuesta Self-Pick
  - Self-Pick de Requisiciones
status: pendiente-de-aprobacion
---

# Propuesta — Self-Pick de Requisiciones

> [!warning] Estado de la propuesta
> **PENDIENTE DE APROBACIÓN POR EL JEFE.**
> Este documento es una propuesta de cambio al flujo actual de distribución de requisiciones en el módulo de [[Reclutamiento/Reclutamiento|Reclutamiento]]. Mientras no se valide, el modelo oficial del vault (Manager distribuye) sigue vigente y NO debe modificarse en las arquitecturas existentes.

## 1. Contexto

Actualmente, según las [[Reclutamiento/Reglas de Reclutamiento|Reglas de Reclutamiento]] del vault, las requisiciones autorizadas siguen este flujo:

```
Manager del Hotel autoriza requisición
      ↓
Manager de Reclutamiento la recibe
      ↓
Manager de Reclutamiento la distribuye manualmente a una Reclutadora
      ↓
Reclutadora la trabaja
```

Este flujo concentra la decisión de **a quién se asigna cada requisición** en el [[Manager de Reclutamiento]], lo cual:

- Lo convierte en cuello de botella si llegan muchas requisiciones a la vez.
- Lo desconecta del rol estratégico (gestión de equipo, blacklist, escalamientos, KPIs).
- Reduce la autonomía y agilidad de las [[Reclutadora|Reclutadoras]] y [[Reclutamiento/Líder de Grupo de Reclutadoras|Líderes de Grupo]].

## 2. Modelo propuesto: Self-Pick

Cambiar el flujo de **distribución manual** a **auto-asignación libre** desde una bandeja compartida:

```
Manager del Hotel autoriza requisición
      ↓
Llega al sistema y queda en cola "Autorizadas" (visible a todo Reclutamiento)
      ↓
Reclutadoras y Líderes de Grupo ven la cola priorizada por urgencia
      ↓
Cada uno toma libremente las requisiciones que pueda cubrir
      ↓
Cubren con colaboradores del Pool

  Manager interviene SOLO en casos especiales:
  - Requisición varada sin tomar (después de N horas)
  - Hotel VIP / cuenta clave
  - Balanceo entre grupos
  - Líder ausente
  - Corrección de error de asignación
```

## 3. Diferencias clave entre ambos modelos

| Aspecto | Modelo actual (oficial) | Modelo propuesto (Self-Pick) |
|---|---|---|
| Quién decide la asignación | Manager de Reclutamiento | Cada Reclutadora / Líder |
| Trigger del flujo | Manager hace clic en "Distribuir" | Reclutadora hace clic en "Tomar" |
| Tiempo desde autorización a asignación | Depende del Manager | Inmediato si hay capacidad disponible |
| Carga de trabajo del Manager | Alta operativa diaria | Solo intervención excepcional |
| Visibilidad de la bandeja | Solo el Manager ve cola completa | Toda Reclutamiento ve cola completa |
| Riesgo de requisiciones varadas | Bajo (Manager fuerza distribución) | Medio (necesita alertas de "sin tomar") |
| Autonomía del equipo | Baja | Alta |
| Posibilidad de cherry-picking | No (Manager decide) | Sí (puede haber sesgo hacia las "fáciles") |

## 4. Pros y Contras del Self-Pick

### ✅ Pros

- **Velocidad:** las requisiciones se toman al instante si hay capacidad, sin esperar al Manager.
- **Manager liberado:** se enfoca en estrategia, gestión de equipo y casos críticos.
- **Autonomía:** Reclutadoras y Líderes deciden su carga según disponibilidad real.
- **Transparencia:** todos ven la cola, lo que fomenta colaboración informal.
- **Escalabilidad:** funciona mejor cuando crece el equipo de Reclutamiento.

### ❌ Contras

- **Cherry-picking:** Reclutadoras pueden preferir requisiciones fáciles y dejar las difíciles varadas.
- **Requisiciones varadas:** las que nadie quiere tomar pueden quedarse en cola sin atención.
- **Pérdida de balanceo:** sin asignación dirigida, algunas Reclutadoras pueden sobrecargarse y otras subutilizarse.
- **Menos control de calidad por hotel:** el Manager no garantiza qué Reclutadora atiende qué hotel (importante para hoteles VIP).
- **Necesita reglas anti-abuso:** límite de requisiciones tomadas por persona, tiempo máximo en cola sin tomar, etc.

## 5. Mitigaciones propuestas para los contras

| Riesgo | Mitigación |
|---|---|
| Cherry-picking | **Auto-asignación forzada** después de N horas: si una requisición urgente lleva >24h sin tomar, el Manager recibe alerta y la asigna manualmente. |
| Sobrecarga individual | **Límite máximo** de requisiciones simultáneas por Reclutadora (ej. 5). |
| Hoteles VIP | **Marcado VIP** en la requisición: solo Líder de Grupo puede tomarla, o el Manager la asigna manualmente. |
| Pérdida de visibilidad | **Dashboard del Manager** con métricas en tiempo real: requisiciones varadas, distribución por persona, tiempos. |
| Requisiciones complejas | **Categoría "Difícil"** que da incentivos (puntos, KPI bonus) para evitar que sean ignoradas. |

## 6. Impacto en las arquitecturas existentes

Si el jefe aprueba el Self-Pick, hay que actualizar:

### [[Arquitectura Reclutadora|Arquitectura del Reclutador]]
- Cambiar módulo "Mis Requisiciones" para que tenga sub-vista **"Bandeja Autorizadas"** (con todas las disponibles para tomar).
- Agregar acción **"Tomar requisición"**.
- Eliminar el supuesto de "recibir requisición asignada".

### [[Arquitectura Líder de Grupo|Arquitectura del Líder de Grupo]]
- Eliminar acción **"Distribuir a Reclutadora del grupo"**.
- Mantener "Tomar para mí" (es lo mismo que el Self-Pick).
- Cambiar KPI "Requisiciones distribuidas" → "Requisiciones tomadas por el grupo".
- Su rol pasa más a supervisión que a distribución.

### [[Arquitectura Manager de Reclutamiento|Arquitectura del Manager]]
- Cambiar módulo "Requisiciones" de "vista global con asignación manual" a "vista global de monitoreo".
- Mantener acción "Tomar requisición personalmente" pero como **excepcional**.
- Agregar acción **"Asignar manualmente (caso especial)"** con justificación obligatoria.
- Agregar nueva alerta en Dashboard: "Requisiciones varadas (sin tomar > N horas)".

### [[Reclutamiento/Reglas de Reclutamiento|Reglas de Reclutamiento]]
- Reemplazar la sección "Requisiciones — recepción y asignación" con el flujo Self-Pick.
- Quitar la regla "Las requisiciones nunca llegan directamente a las Reclutadoras".
- Agregar reglas anti-abuso (límites, alertas, casos especiales).

## 7. Plan de implementación si se aprueba

**Fase 1 — Documentación (1-2 días)**
1. Actualizar [[Reclutamiento/Reglas de Reclutamiento|Reglas de Reclutamiento]] con el nuevo flujo.
2. Actualizar las 3 arquitecturas (Reclutadora, Líder, Manager).
3. Actualizar [[Core/Módulos/Reglas de Negocio|Reglas de Negocio]] (sección "Distribución de requisiciones").

**Fase 2 — Diseño UI (3-5 días)**
4. Diseñar bandeja compartida en Miro.
5. Diseñar acción "Tomar requisición" con confirmación.
6. Diseñar alertas de requisiciones varadas para el Manager.

**Fase 3 — Reglas operativas (2 días)**
7. Definir límite de requisiciones simultáneas por Reclutadora.
8. Definir tiempo máximo en cola antes de alerta automática.
9. Definir clasificación VIP / Difícil de requisiciones.

**Fase 4 — Pilotar (2-4 semanas)**
10. Probar con un grupo de Reclutadoras antes de rolear a todo el módulo.
11. Medir KPIs: tiempo a primera asignación, % requisiciones varadas, balance de carga.
12. Ajustar reglas según resultados.

**Fase 5 — Rollout completo**
13. Anunciar al equipo el cambio.
14. Capacitar.
15. Activar el modelo en producción.
16. Hacer revisión a los 30 / 60 / 90 días.

## 8. Preguntas abiertas para el jefe

Cuando se presente esta propuesta, conviene tener resuelto:

1. ¿Qué porcentaje de requisiciones son consideradas VIP/críticas en Oranje? (esto define el umbral de excepciones)
2. ¿Cuál es el tiempo aceptable que una requisición urgente puede estar en cola sin tomar?
3. ¿Cuál es la carga máxima recomendable de requisiciones simultáneas por Reclutadora?
4. ¿Hay restricciones por zona/posición/idioma que deban respetarse al tomar una requisición?
5. ¿Aprueba el principio general de "autonomía del equipo" sobre "control central"?

## 9. Recomendación

> [!info] Recomendación de la propuesta
> Pasar al modelo Self-Pick es **viable y beneficioso a mediano plazo**, pero requiere:
> - Reglas anti-abuso claras antes del rollout.
> - Dashboard del Manager con alertas de requisiciones varadas.
> - Pilotaje en grupo pequeño antes de rolear a todo Reclutamiento.
>
> Si el jefe NO aprueba el cambio, las arquitecturas actuales del vault siguen siendo válidas y no requieren modificación.

---

## Relacionado

- [[Reclutamiento/Reglas de Reclutamiento|Reglas de Reclutamiento]] (modelo actual oficial)
- [[Core/Módulos/Reglas de Negocio|Reglas de Negocio]]
- [[Manager de Reclutamiento]]
- [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo de Reclutadoras]]
- [[Reclutadora]]
- [[Arquitecturas/Reclutamiento/Manager de Reclutamiento|Arquitectura del Manager]]
- [[Arquitecturas/Reclutamiento/Lider de Grupo de Reclutadoras|Arquitectura del Líder de Grupo]]
- [[Arquitecturas/Reclutamiento/Reclutadora|Arquitectura de la Reclutadora]]
