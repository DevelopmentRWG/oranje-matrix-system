---
tags:
  - arquitectura
  - departamento/hotel
aliases:
  - Dependencias Hotel
---

# 9. DEPENDENCIAS — DEPARTAMENTO DE HOTEL

---

## Dependencias internas (otros módulos del sistema Oranje)

| Dependencia                       | Descripción                                                                                                                                                  |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Módulo Reclutamiento**          | Recibe las requisiciones autorizadas por el Manager de Área mediante modelo Self-Pick. Sin Reclutamiento, las requisiciones no se cubren con colaboradores. |
| **Módulo Schedule**               | Las posiciones autorizadas se reflejan automáticamente en el Schedule del hotel. El Schedule es el eje del módulo: sobre él se construye el Timesheet.        |
| **Módulo Timesheet**              | Construido sobre el Schedule. Registra ponches vía QR generado por el Manager de Área. Calcula Indicador de Cumplimiento.                                  |
| **Módulo Inspección**             | Asignación automática de Inspector por zona al autorizar requisición. Investiga reportes de colaborador (Rojo) y accidentes (Gris).                          |
| **Módulo Onboarding-Hotel**       | Habilitación del hotel al alcanzar status Naranja en Semáforo Onboarding. Antes, el hotel es prospecto comercial gestionado por Ventas.                      |
| **Módulo QA**                     | Operador de QA fijo asignado al depto Hotel. Métricas e Indicador de Calidad. QA observa, mide y retroalimenta sin operar.                                   |
| **Módulo Pool de Colaboradores**  | Indirecto — los colaboradores asignados al hotel provienen del Pool. El Hotel ve solo los asignados, no el Pool completo.                                    |

---

## Dependencias externas (sistemas o apps fuera del módulo)

| Dependencia                     | Descripción                                                                                                                                  |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **App del Supervisor**          | El Supervisor opera desde mobile para crear requisiciones y reportar accidentes laborales presenciales (RNF-H-04).                          |
| **App del Colaborador**         | El colaborador poncha vía QR generado por el Manager de Área. También reporta accidentes (Escenario A) desde la app.                       |
| **Sistema de Notificaciones**   | Envía notificaciones automáticas a los roles del Hotel ante eventos relevantes (autorización, asignación, cobertura, accidente).             |
| **Sistema de Auditoría / Logs** | Registra journals de requisiciones, posiciones, ponches corregidos y acciones excepcionales. Trazabilidad obligatoria (RNF-H-03).            |

---

## Dependencias de catálogos (configuración del sistema)

| Catálogo                          | Descripción                                                                              |
| --------------------------------- | ---------------------------------------------------------------------------------------- |
| **[[Departamentos del Hotel]]**   | Housekeeping, Alimentos, Mantenimiento, Front Desk. Define el alcance del Gerente de Departamento en jerarquía extendida. |
| **[[Posiciones]]**                | Housekeeper, Hoseman, Chef, Laundry, etc. Mantenido por el Administrador. Usado al crear requisiciones. |
| **[[Zonas]]**                     | Centro, Sur, Este, Oeste, Noroeste, Sureste. Asignación de Inspectores se basa en zonas. |
| **[[Modalidades de Contratación]]** | Tiempo completo, Medio tiempo, Temporal, Según solicitud.                              |
| **[[Niveles de Inglés]]**         | Básico, Intermedio, Avanzado, Conversacional.                                            |

---

## Dependencias de roles externos

| Rol externo                                              | Cuándo interviene                                                                                |
| -------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **[[Reclutadora]]** *(módulo Reclutamiento)*             | Toma las requisiciones autorizadas y asigna colaboradores al hotel.                              |
| **[[Reclutamiento/Líder de Grupo de Reclutadoras\|Líder de Grupo]]** | También toma requisiciones (Self-Pick); aprueba cierres del grupo.                       |
| **[[Manager de Reclutamiento]]**                         | Casos especiales (intervención excepcional). Resuelve disputas de Blacklist.                     |
| **[[Inspector]]** *(módulo Inspección)*                  | Investiga accidentes laborales (Gris) y reportes de colaborador (Rojo). Asignado por zona.       |
| **[[Inspección/Coordinador\|Coordinador de Inspección]]**| Supervisión de Inspectores; ve Indicador de Lunch Extendido.                                     |
| **[[QA/Operador de QA\|Operador de QA]]**                | Observa y mide al depto Hotel. Emite alertas al Indicador de Calidad.                            |
| **Business Developer / BDC** *(Onboarding-Hotel)*        | Recibe escalamientos comerciales del Manager General o del Manager de Reclutamiento.             |

---

## Dependencias semafóricas

| Semáforo                                                                                       | Uso en el depto Hotel                                                                  |
| ---------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| **[[Core/Módulos/Semáforos/Semáforo Onboarding\|Semáforo Onboarding]]**                       | Habilitación del hotel (status Naranja).                                               |
| **[[Semáforo de Requisición]]**                                                                | Estado de cada requisición (Verde manzana, Autorizada, En proceso, Cubierta, Morado).  |
| **[[Semáforo de Urgencia de Requisición]]**                                                    | Cálculo automático al autorizar (Verde / Amarillo / Rojo según horas a fecha de inicio). |
| **[[Semáforo de Posiciones de la Requisición]]**                                               | Cobertura de cada posición (Dorado → Naranja al autorizar).                            |
| **[[Semáforo del Colaborador]]**                                                               | Estado de cada colaborador asignado (Naranja, Rosa, Rojo, Gris, etc.).                 |
| **[[Core/Módulos/Semáforos/Indicador de Cumplimiento del Timesheet\|Indicador de Cumplimiento del Timesheet]]** | Calculado por jornada y semana por colaborador.                                  |
| **[[Core/Módulos/Semáforos/Indicador de Calidad\|Indicador de Calidad]]**                     | Visibilidad para el Manager General y QA.                                              |
