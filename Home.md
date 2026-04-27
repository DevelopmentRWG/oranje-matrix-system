---
tags:
  - modulo/core
aliases:
  - Oranje Matrix System
  - Home
---
# Oranje Matrix System

Sistema de gestión organizacional para staffing de hoteles. Documenta los roles, procesos, reglas de negocio y módulos operativos que estructuran la operación de Oranje, desde el reclutamiento de personal hasta su asignación y seguimiento en hoteles clientes.

## Departamentos y Roles

### [[Reclutamiento/Reclutamiento|Reclutamiento]]

Búsqueda, entrevista y asignación de personal a hoteles.

- [[Manager de Reclutamiento]] — recibe requisiciones aprobadas y las distribuye a las reclutadoras.
- [[Líder de Grupo de Reclutadoras]] — recluta y supervisa el desempeño de un grupo de reclutadoras.
- [[Reclutadora]] — busca, entrevista, valida y asigna colaboradores.

### [[Hotel/Hotel|Hotel]]

Operación diaria y gestión de personal en hoteles clientes.

- [[Hotel/Manager General|Manager General]] — máxima autoridad en hoteles con jerarquía extendida.
- [[Manager del Hotel]] — aprueba requisiciones, genera QR de ponchado y gestiona el schedule semanal. En jerarquía extendida: Gerente de Departamento.
- [[Hotel/Supervisor|Supervisor]] — crea requisiciones de personal y reporta accidentes laborales.

### Inspección

Supervisión de colaboradores en sitio durante sus primeros días de asignación.

- [[Coordinador]] — asigna inspectores a zonas y actúa como enlace con otros departamentos.
- [[Inspector]] — supervisa colaboradores en sitio, verifica llegadas y cierra tarjetas de accidente.

### [[QA/QA|QA]]

Control de calidad sobre todos los departamentos de Oranje.

- [[Manager de QA]] — define métricas y KPIs, supervisa operadores y presenta reportes a dirección.
- [[Operador de QA]] — monitorea semáforos, mide métricas y emite observaciones por departamento.

### [[Ventas/Ventas|Ventas]]

Desarrollo de negocio y onboarding de nuevos hoteles clientes.

- [[Business Developer Coordinator]] — supervisa BDs en su territorio y da el visto bueno para convertir prospectos en clientes.
- [[Business Developer]] — gestiona el ciclo comercial con hoteles prospectos.

Proceso: [[Onboarding-Hotel]]

## Entidad Central

- [[Colaborador/Colaborador|Colaborador]] — la persona que se recluta, asigna y opera en los hoteles. Su ciclo de vida es el eje del sistema.

## Módulos Core

### Procesos

- [[Requisición]] — solicitud formal de personal por parte de un hotel. Ver [[Flujo de Requisición]].
- [[Contrato]] — acuerdo legal entre Oranje y el colaborador.
- [[Flujo de Reclutamiento]] — proceso de captación y alta de colaboradores nuevos.
- [[Flujo de Onboarding]] — proceso de incorporación de un hotel nuevo como cliente.

### Operación

- [[Core/Módulos/Schedule|Schedule]] — asignación semanal de colaboradores a hoteles.
- [[Timesheet]] — registro de horas trabajadas mediante ponches QR.
- [[Pool de Colaboradores]] — repositorio de colaboradores disponibles para asignación.

### Control

- [[Core/Módulos/Blacklist|Blacklist]] — registro de colaboradores bloqueados.
- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]] — gestión de incidentes en sitio. Ver [[Flujo de Accidente Laboral]].
- [[Reglas de Negocio]] — restricciones y condiciones operativas del sistema.

## Catálogos

- [[Posiciones]] — tipos de puesto que puede ocupar un colaborador.
- [[Zonas]] — áreas geográficas de operación.
- [[Niveles de Inglés]] — escala de competencia lingüística de colaboradores.
- [[Departamentos del Hotel]] — áreas operativas internas del hotel.
- [[Modalidades de Contratación]] — formas de contrato disponibles.

## Semáforos

Indicadores de estado que reflejan la situación operativa de cada entidad en tiempo real.

- [[Semáforo del Colaborador]] — estado del colaborador en su ciclo de vida.
- [[Semáforo de Requisición]] — estado de una requisición en su proceso de cobertura.
- [[Semáforo de Urgencia de Requisición]] — nivel de urgencia de una requisición abierta.
- [[Semáforo de Posiciones de la Requisición]] — estado de cada posición dentro de una requisición.
- [[Semáforo Onboarding]] — estado de la negociación con un hotel prospecto.
- [[Indicador de Calidad]] — nivel de desempeño de un área supervisada por QA.
