---
tags:
  - arquitectura
  - rol/bdc
aliases:
  - Campos Formulario BDC
---

# 3. CAMPOS DEL FORMULARIO — BDC

> [!info]
> El BDC no llena formularios operativos del prospecto (eso es del BD). Sus formularios son de **validación, gestión de casos especiales, conversión y reportes ejecutivos**.

---

## A) Validar Documento de T&C — RF-V-10

| Campo            | Tipo de Input | Obligatorio                   | Validación                    | Descripción              |
| ---------------- | ------------- | ----------------------------- | ----------------------------- | ------------------------ |
| Decisión         | Select        | SÍ                            | Aprobar / Rechazar            | Decisión del BDC         |
| Comentario al BD | Textarea      | NO si aprueba / SÍ si rechaza | Mín. 30 caracteres si rechaza | Observaciones para el BD |
| Adjuntos         | File          | NO                            | PDF, máx. 10 MB               | Documentos de soporte    |

---

## B) Crear Usuario del Hotel — RF-V-11

| Campo             | Tipo de Input | Obligatorio | Validación                                    | Descripción                     |
| ----------------- | ------------- | ----------- | --------------------------------------------- | ------------------------------- |
| Hotel             | Auto          | SÍ          | Pre-llenado desde el prospecto                | Hotel destino                   |
| Email del usuario | Email         | SÍ          | Formato válido y único en el sistema          | Email del responsable del hotel |
| Nombre completo   | Text          | SÍ          | Mín. 3 caracteres                             | Persona del hotel               |
| Rol asignado      | Select        | SÍ          | Catálogo: Manager de Área / Manager General | Rol que tendrá en la plataforma |
| Teléfono          | Text          | NO          | Formato válido                                | Contacto                        |
| Notas             | Textarea      | NO          | Máx. 500 caracteres                           | Observaciones                   |

---

## C) Aprobar Conversión — RF-V-12

| Campo                          | Tipo de Input | Obligatorio | Validación                           | Descripción                                                  |
| ------------------------------ | ------------- | ----------- | ------------------------------------ | ------------------------------------------------------------ |
| Hotel                          | Auto          | SÍ          | Pre-llenado                          | Hotel a convertir                                            |
| Confirmación Usuario del Hotel | Auto          | SÍ          | Sistema valida que existe el Usuario | Bloqueo si no se ha creado (RR-V-02)                         |
| T&C validado                   | Auto          | SÍ          | Sistema valida que está aprobado     | Bloqueo si no                                                |
| Notas para el cierre           | Textarea      | NO          | Máx. 500 caracteres                  | Observaciones del BDC                                        |
| Confirmación final             | Checkbox      | SÍ          | Debe estar marcado                   | "Confirmo que el hotel cumple los requisitos para activarse" |

---

## D) Desbloquear Café — RF-V-18

| Campo             | Tipo de Input | Obligatorio | Validación                                                      | Descripción                       |
| ----------------- | ------------- | ----------- | --------------------------------------------------------------- | --------------------------------- |
| Diagnóstico       | Textarea      | SÍ          | Mín. 50 caracteres                                              | Causa del estancamiento detectada |
| Solución acordada | Textarea      | SÍ          | Mín. 50 caracteres                                              | Plan de acción                    |
| Decisión          | Select        | SÍ          | Reactivar a Azul Claro / Reasignar a otro BD / Cerrar como Rojo | Resultado final                   |

---

## E) Marcar Cliente Negro — RF-V-20

| Campo          | Tipo de Input | Obligatorio | Validación                                                                     | Descripción           |
| -------------- | ------------- | ----------- | ------------------------------------------------------------------------------ | --------------------- |
| Motivo         | Select        | SÍ          | Catálogo: Cierre del hotel / Cambio de administración / Pausa / Disputa / Otro | Razón del Negro       |
| Comentario     | Textarea      | SÍ          | Mín. 30 caracteres                                                             | Detalle               |
| Fecha de pausa | Date          | NO          | Fecha actual o pasada                                                          | Cuándo dejó de operar |

---

## F) Generar Reporte — RF-V-26

| Campo                        | Tipo de Input | Obligatorio | Validación                                                             | Descripción                |
| ---------------------------- | ------------- | ----------- | ---------------------------------------------------------------------- | -------------------------- |
| Tipo de reporte              | Select        | SÍ          | Pipeline / Conversión / Desempeño / Café / Negro / Calidad / Ejecutivo | Plantilla a usar           |
| Rango de fechas              | Date Range    | SÍ          | —                                                                      | Periodo                    |
| BDs incluidos                | Multi-select  | NO          | Catálogo de BDs a cargo                                                | Si se omite, incluye todos |
| Rutas / Zonas                | Multi-select  | NO          | Catálogo                                                               | Filtros adicionales        |
| Formato de salida            | Select        | SÍ          | PDF / CSV / Excel                                                      | —                          |
| Comparativa periodo anterior | Checkbox      | NO          | —                                                                      | Incluir vs mes anterior    |

---

## G) Enviar Reporte a Dirección — RF-V-27

| Campo                      | Tipo de Input        | Obligatorio | Validación                           | Descripción                  |
| -------------------------- | -------------------- | ----------- | ------------------------------------ | ---------------------------- |
| Destinatarios              | Multi-select / Email | SÍ          | Lista de directivos / emails válidos | A quiénes enviar             |
| Asunto                     | Text                 | SÍ          | Mín. 10 caracteres                   | Asunto del email             |
| Mensaje                    | Textarea             | NO          | Máx. 1000 caracteres                 | Contexto                     |
| Reporte adjunto            | Auto                 | SÍ          | Pre-llenado                          | Reporte previamente generado |
| Programar envío recurrente | Checkbox             | NO          | —                                    | Si se marca, abre opciones   |
| Frecuencia                 | Select               | NO          | Semanal / Mensual / Trimestral       | Solo si recurrente           |
