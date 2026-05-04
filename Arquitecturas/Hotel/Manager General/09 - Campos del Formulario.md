---
tags:
  - arquitectura
  - rol/manager-general
aliases:
  - Campos Formulario Manager General
---

# 3. CAMPOS DEL FORMULARIO — MANAGER GENERAL

> [!info]
> El Manager General no llena formularios operativos. Sus formularios son de **comentarios, escalamientos y generación de reportes ejecutivos**.

---

## A) Formulario de Comentar Expediente (RF-H-26)

| Campo            | Tipo de Input | Obligatorio | Validación                              | Descripción                                                |
| ---------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Comentario       | Textarea      | SÍ          | Mín. 20 caracteres                      | Comentario que verá el Gerente de Departamento             |
| Notificar a      | Multi-select  | NO          | Lista de involucrados                   | A quiénes notificar (Gerente, Supervisor, etc.)            |
| Adjuntos         | File          | NO          | PDF/JPG/PNG, máx. 5 MB                  | Evidencia o documento de soporte                           |

---

## B) Formulario de Escalar Requisición Demorada (RF-H-27)

| Campo                | Tipo de Input | Obligatorio | Validación                              | Descripción                                                |
| -------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Requisición          | Auto          | SÍ          | Pre-llenado desde la requisición        | ID y número                                                |
| Motivo del escalamiento | Select     | SÍ          | Catálogo: Tiempo en cola excesivo / Urgencia Red / Hotel VIP / Otro | Razón principal                                            |
| Mensaje al Manager de Reclutamiento | Textarea | SÍ      | Mín. 30 caracteres                       | Contexto y solicitud específica                            |

---

## C) Formulario de Solicitar Reporte a Gerente (RF-H-28)

| Campo                | Tipo de Input | Obligatorio | Validación                              | Descripción                                                |
| -------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Gerente destinatario | Select        | SÍ          | Lista de Gerentes de Departamento       | A quién se solicita                                        |
| Tipo de reporte       | Select        | SÍ          | Catálogo de plantillas                  | Cobertura / Desempeño / Casos / Otro                       |
| Rango de fechas       | Date Range    | SÍ          | —                                       | Periodo a reportar                                         |
| Mensaje              | Textarea      | NO          | Máx. 500 caracteres                     | Contexto de la solicitud                                   |
| Fecha límite         | Date          | NO          | Fecha futura                             | Cuándo se necesita                                         |

---

## D) Formulario de Generar Reporte Ejecutivo (RF-H-24)

| Campo                | Tipo de Input | Obligatorio | Validación                              | Descripción                                                |
| -------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Tipo de reporte       | Select        | SÍ          | Catálogo: Cobertura / Desempeño / Cumplimiento / Calidad / Accidentes / Indicadores ejecutivos | Plantilla a usar                                          |
| Rango de fechas       | Date Range    | SÍ          | —                                       | Periodo                                                     |
| Departamentos        | Multi-select  | NO          | Catálogo de Deptos                      | Si se omite, incluye todos                                 |
| Filtros adicionales  | Multi-select  | NO          | Posición / Hotel / Gerente              | Filtros extra                                              |
| Formato de salida     | Select        | SÍ          | PDF / CSV / Excel                       | Formato de exportación                                     |
| Comparativa contra periodo anterior | Checkbox | NO     | —                                       | Incluye vs mes anterior                                    |

---

## E) Formulario de Enviar Reporte a Dirección (RF-H-25)

| Campo                | Tipo de Input | Obligatorio | Validación                              | Descripción                                                |
| -------------------- | ------------- | ----------- | --------------------------------------- | ---------------------------------------------------------- |
| Destinatarios         | Multi-select / Email | SÍ      | Lista de directivos / emails válidos    | A quiénes enviar                                           |
| Asunto               | Text          | SÍ          | Mín. 10 caracteres                       | Asunto del email / link                                    |
| Mensaje              | Textarea      | NO          | Máx. 1000 caracteres                     | Contexto del envío                                         |
| Reporte adjunto      | Auto          | SÍ          | Pre-llenado                             | Reporte previamente generado                               |
| Programar envío recurrente | Checkbox  | NO       | —                                       | Si se marca, abre opciones de recurrencia                  |
| Frecuencia            | Select        | NO          | Semanal / Mensual / Trimestral          | Solo si recurrente                                         |
