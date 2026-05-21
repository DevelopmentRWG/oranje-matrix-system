---
tags:
  - departamento/inspeccion
aliases:
  - Inspección
  - Departamento de Inspección
---

# Inspección

Departamento encargado de la supervisión de colaboradores en sitio. Los inspectores verifican la llegada de colaboradores asignados, entregan uniformes, investigan incidencias y gestionan tarjetas de accidente laboral. Operan organizados por [[Zonas|zonas geográficas]] bajo la coordinación de un Coordinador.

## Contenido del módulo

### Roles

- [[Inspección/Coordinador|Coordinador]] — Asigna inspectores a zonas, supervisa en campo y actúa como enlace interdepartamental.
- [[Inspección/Inspector|Inspector]] — Verifica llegadas, entrega uniformes, investiga estados Rojo, ejecuta Blacklist manual y gestiona tarjetas de accidente.

### Reglas

- [[Inspección/Reglas de Inspección|Reglas de Inspección]]

### Procesos

- Verificación de llegada Día 1 (transición Blanco → Verde manzana en [[Semáforo del Colaborador]]).
- Entrega de uniforme Día 3+ (transición Verde manzana → Azul claro).
- Investigación de estado Rojo → resolución hacia Negro ([[Core/Módulos/Blacklist|Blacklist]]) o Verde fuerte.
- Gestión de [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]] — complemento y cierre de tarjeta (transición Gris → Verde fuerte).

## Conceptos Core relacionados

- [[Semáforo del Colaborador]]
- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Zonas]]
- [[Indicador de Calidad]]

## Relación con otros módulos

- [[Hotel/Hotel|Hotel]] — Los inspectores verifican colaboradores asignados a hoteles.
- [[Reclutamiento/Reclutamiento|Reclutamiento]] — Inspección valida en sitio el resultado del proceso de reclutamiento.
- [[QA/QA|QA]] — Un Operador de QA supervisa las métricas de desempeño de Inspección.
- [[Customer Service/Customer Service|Customer Service]] — Customer Service coordina con el [[Inspección/Coordinador|Coordinador]] para incidencias del hotel que requieran verificación en sitio.
