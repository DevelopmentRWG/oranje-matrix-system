---
tags:
  - departamento/qa
aliases:
  - Dashboard de QA
  - Dashboard QA
  - Tablero de QA
---

# Dashboard de QA

Especificación de las visualizaciones y gráficas que la aplicación debe proveer al equipo de [[QA/QA|QA]] para monitorear la calidad operativa de cada departamento. Este documento es un **requerimiento funcional** para desarrollo.

> [!info]
> Todos los datos que alimentan estas gráficas ya son rastreados por el sistema (semáforos, timesheets, journals, requisiciones). El dashboard los presenta de forma visual para facilitar el análisis del equipo de QA.

## Acceso por rol

| Rol | Paneles visibles |
|---|---|
| [[Manager de QA]] | Panel global + los 6 paneles por departamento |
| [[Operador de QA]] | Solo el panel de su departamento asignado |

## Panel global — Manager de QA

Vista consolidada de los 6 departamentos supervisados. Permite al [[Manager de QA]] identificar rápidamente qué departamentos requieren atención.

### Gráficas del panel global

| # | Gráfica | Tipo de visualización | Datos | Actualización |
|---|---------|----------------------|-------|---------------|
| 1 | **Estado actual de los 6 departamentos** | Tarjetas resumen (1 por departamento) | [[Indicador de Calidad]] de cada departamento + conteo de KPIs en Meta / En riesgo / Crítico | Tiempo real |
| 2 | **Tendencia del Indicador de Calidad** | Gráfica de líneas (1 línea por departamento) | Historial de cambios del [[Indicador de Calidad]] por departamento. Eje X = semanas | Semanal |
| 3 | **KPIs en estado Crítico** | Tabla con alertas | Lista de KPIs que están en nivel Crítico en cualquier departamento, con nombre del KPI, departamento y valor actual | Tiempo real |

## Panel por departamento — Operador de QA

Cada uno de los 6 departamentos tiene un panel detallado con las siguientes gráficas estándar, alimentadas por los KPIs definidos en [[QA/Métricas y KPIs por Departamento|Métricas y KPIs por Departamento]].

### Gráficas estándar (aplican a los 6 departamentos)

| # | Gráfica | Tipo de visualización | Datos | Actualización |
|---|---------|----------------------|-------|---------------|
| 1 | **Resumen de KPIs** | Barras horizontales con zonas Meta / En riesgo / Crítico | Valor actual de cada KPI del departamento vs umbrales definidos | Tiempo real |
| 2 | **Tendencia de KPIs** | Gráfica de líneas (1 línea por KPI) | Historial semanal de cada KPI del departamento. Eje X = semanas | Semanal |
| 3 | **Historial de observaciones** | Timeline / lista cronológica | Observaciones formales emitidas al departamento: estado (abierta / atendida / cerrada), fecha de emisión, descripción | Tiempo real |

### Gráficas específicas por departamento

Además de las gráficas estándar, cada departamento tiene visualizaciones particulares que aprovechan la naturaleza de sus datos.

#### Inspección

| Gráfica | Tipo de visualización | Datos |
|---------|----------------------|-------|
| **Mapa de cobertura de zonas** | Mapa geográfico o diagrama de zonas | Las 6 [[Core/Catálogos/Zonas|zonas]] con indicador de disponibilidad de [[Inspector]] (activo / cobertura temporal / sin cobertura) |

#### Hotel

| Gráfica | Tipo de visualización | Datos |
|---------|----------------------|-------|
| **Ranking de hoteles por cumplimiento de ponchado** | Tabla ordenada / barras verticales | Hoteles ordenados por % de timesheets con 6 ponches completos, del mejor al peor |

#### Colaborador

| Gráfica | Tipo de visualización | Datos |
|---------|----------------------|-------|
| **Distribución del Semáforo del Colaborador** | Gráfica de dona | Porcentaje de colaboradores en cada uno de los 12 estados del [[Semáforo del Colaborador]] |

#### Ventas

| Gráfica | Tipo de visualización | Datos |
|---------|----------------------|-------|
| **Funnel del Semáforo Onboarding** | Gráfica de embudo | Cantidad de hoteles en cada etapa del [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]] (Gris → Azul Claro → Verde → Amarillo → Rosa → Naranja) |

#### Reclutamiento

| Gráfica | Tipo de visualización | Datos |
|---------|----------------------|-------|
| **Embudo de reclutamiento** | Gráfica de embudo | Candidatos entrevistados → aprobados → ingresados al [[Pool de Colaboradores]] → asignados a posición |
| **Heatmap de tiempo de toma por urgencia** | Mapa de calor | Tiempo de toma de requisición (eje Y) vs nivel de urgencia del [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición|Semáforo de Urgencia]] (eje X). Intensidad = cantidad de requisiciones |

#### Customer Service

> [!note]
> Las gráficas específicas de Customer Service se definirán una vez que los KPIs del departamento estén establecidos. Ver [[QA/Métricas y KPIs por Departamento#Customer Service|Métricas y KPIs — Customer Service]].

## Relacionado

- [[QA/QA|QA]]
- [[Manager de QA]]
- [[Operador de QA]]
- [[QA/Métricas y KPIs por Departamento|Métricas y KPIs por Departamento]]
- [[Core/Módulos/Semáforos/Indicador de Calidad|Indicador de Calidad]]
