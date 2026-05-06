---
tags:
  - arquitectura
  - departamento/ventas
aliases:
  - Dependencias Ventas
---

# 9. DEPENDENCIAS — DEPARTAMENTO DE VENTAS

---

## Dependencias internas (otros módulos del sistema Oranje)

| Dependencia                       | Descripción                                                                                                                                                  |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Módulo Hotel**                  | Destino del onboarding. Al alcanzar Naranja, el hotel se habilita para generar requisiciones desde el módulo Hotel.                                          |
| **Módulo Reclutamiento**          | Recibe el hotel cliente activo (post-Naranja) para iniciar el ciclo operativo de cobertura de requisiciones.                                                 |
| **Módulo Inspección**             | Al activarse el hotel, el sistema asigna automáticamente un Inspector según la zona del hotel.                                                              |
| **Módulo Contrato**               | Artefacto generado al cierre exitoso en Rosa. Insumo obligatorio: Documento de T&C validado por el BDC.                                                     |
| **Módulo Schedule**               | Indirectamente — el Contrato configura la estructura del Schedule semanal del hotel (inicio y fin de semana, festivos).                                     |
| **Módulo QA**                     | Operador de QA fijo asignado al depto. Métricas e Indicador de Calidad. QA observa, mide y retroalimenta sin operar.                                         |
| **Pool de Colaboradores**         | Indirecto — solo se vuelve relevante post-Naranja cuando Reclutamiento empieza a cubrir.                                                                    |

---

## Dependencias externas (sistemas o apps fuera del módulo)

| Dependencia                     | Descripción                                                                                                                                  |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **App del BD (Mobile)**         | El BD opera desde mobile durante visitas en frío y seguimientos de campo (RNF-V-04).                                                          |
| **Sistema de Email Marketing / Transaccional** | Envía email de bienvenida automático al hotel tras la conversión (Trigger — RI-V-05).                                          |
| **Sistema de Notificaciones**   | Envía notificaciones automáticas a BD y BDC ante eventos relevantes (cambios de status, conversión, alertas).                                |
| **Sistema de Auditoría / Logs** | Registra trazabilidad obligatoria de todos los cambios de status (RR-V-11, RNF-V-03).                                                         |

---

## Dependencias de catálogos (configuración del sistema)

| Catálogo                          | Descripción                                                                                              |
| --------------------------------- | -------------------------------------------------------------------------------------------------------- |
| **Zonas / Rutas comerciales**     | Define el territorio de cada BD y el alcance del BDC. Mantenido por el Administrador.                    |
| **Plantillas de Propuesta**       | Plantillas base que el BD puede personalizar al elaborar una Propuesta Personalizada.                    |
| **Plantillas de T&C**             | Estructura base del Documento de T&C con campos obligatorios (Pay/Bill/Overtime/Festivos/Calendario).    |
| **Estados del Semáforo Onboarding** | Catálogo de status: Gris, Azul Claro, Verde, Amarillo, Rosa, Naranja, Rojo, Negro, Café.              |
| **Motivos de cambio de status**   | Catálogo para selector de motivo al cambiar status (rechazo, estancamiento, pausa, etc.).               |

---

## Dependencias de roles externos

| Rol externo                                              | Cuándo interviene                                                                            |
| -------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| **[[Hotel/Manager del Hotel\|Manager del Hotel]]**       | Recibe el sistema activo post-Naranja; crea requisiciones.                                   |
| **[[Hotel/Supervisor\|Supervisor del Hotel]]**           | Recibe el sistema activo post-Naranja; crea requisiciones.                                   |
| **[[Reclutadora]]**                                      | Recibe el hotel activo para empezar a cubrir requisiciones.                                  |
| **[[Inspector]]**                                        | Asignado automáticamente al hotel al activarse (por zona).                                   |
| **[[QA/Operador de QA\|Operador de QA]]**                | Mide y retroalimenta el desempeño del depto Ventas.                                          |
| **Cliente del hotel**                                    | Recibe email de bienvenida al activarse; usuario de la plataforma vía Usuario del Hotel.    |

---

## Dependencias semafóricas

| Semáforo                                                                                       | Uso en el depto Ventas                                                                  |
| ---------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| **[[Core/Módulos/Semáforos/Semáforo Onboarding\|Semáforo Onboarding]]**                       | Columna vertebral del depto. Define cada etapa del proceso (Gris → Naranja).            |
| **[[Core/Módulos/Semáforos/Indicador de Calidad\|Indicador de Calidad]]**                     | Visibilidad para BDC y QA. Si entra a Rojo persistente, escala a dirección.             |
