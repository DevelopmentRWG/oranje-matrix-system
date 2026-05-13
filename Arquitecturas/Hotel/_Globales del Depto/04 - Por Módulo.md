---
tags:
  - arquitectura
  - departamento/hotel
aliases:
  - Requerimientos por Módulo Hotel
---

# REQUERIMIENTOS POR MÓDULO — DEPARTAMENTO DE HOTEL

Agrupación de los RFs definidos en [[03 - Tabla de Requerimientos]] según el módulo del sidebar al que pertenecen.

---

## 📋 REQUISICIONES

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| RF-H-01 | Crear requisición | Supervisor | 🔴 Alta |
| RF-H-02 | Editar borrador de requisición | Supervisor | 🔴 Alta |
| RF-H-03 | Enviar requisición a autorización | Supervisor | 🔴 Alta |
| RF-H-04 | Eliminar borrador / requisición vacía | Supervisor / Sistema | 🟡 Media |
| RF-H-05 | Autorizar requisición | Manager de Área | 🔴 Alta |
| RF-H-06 | Rechazar requisición con observaciones | Manager de Área | 🔴 Alta |
| RF-H-07 | Eliminar requisición con posiciones | Manager de Área | 🟡 Media |
| RF-H-08 | Calcular Semáforo de Urgencia al autorizar | Sistema | 🔴 Alta |
| RF-H-09 | Asignar Inspector automáticamente por zona | Sistema | 🔴 Alta |
| RF-H-26 | Comentar al expediente de requisición | Manager General | 🟢 Baja |
| RF-H-27 | Escalar requisición demorada | Manager General | 🟡 Media |

---

## 📅 SCHEDULE

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| RF-H-10 | Reflejar posiciones en Schedule al autorizar | Sistema | 🔴 Alta |
| RF-H-12 | Editar Schedule semanal | Manager de Área | 🔴 Alta |
| RF-H-13 | Consultar Schedule | Supervisor / Manager General | 🔴 Alta |
| RF-H-19 | Sugerir refuerzo de personal | Supervisor | 🟢 Baja |
| RF-H-22 | Ver Schedule global del hotel | Manager General | 🟡 Media |

---

## ⏱️ TIMESHEET

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| RF-H-11 | Generar / Renovar QR del Timesheet | Manager de Área | 🔴 Alta |
| RF-H-14 | Corregir ponche del Timesheet | Manager de Área | 🟡 Media |
| RF-H-15 | Consultar Timesheet | Supervisor / Manager de Área / Manager General | 🔴 Alta |
| RF-H-16 | Calcular Indicador de Cumplimiento | Sistema | 🔴 Alta |
| RF-H-23 | Ver Timesheet global del hotel | Manager General | 🟡 Media |

---

## 👥 MI PERSONAL

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| RF-H-17 | Poner colaborador en Stand-by (Rosa) | Supervisor / Manager de Área | 🔴 Alta |
| RF-H-18 | Reportar colaborador (Rojo) | Manager de Área | 🔴 Alta |

---

## 🚨 ACCIDENTES LABORALES

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| RF-H-20 | Reportar accidente — Escenario A | Supervisor | 🔴 Alta |
| RF-H-21 | Reportar accidente — Escenario B | Supervisor | 🔴 Alta |

---

## 👥 MI EQUIPO DEL HOTEL *(Manager General)*

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| RF-H-28 | Solicitar reporte a Gerente de Departamento | Manager General | 🟢 Baja |

---

## 📈 REPORTES *(Manager General)*

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| RF-H-24 | Generar reporte ejecutivo | Manager General | 🟡 Media |
| RF-H-25 | Enviar reporte a dirección | Manager General | 🟡 Media |

---

## ⚫ BLACKLIST

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| RF-H-29 | Consultar Blacklist | Todos los roles del Hotel | 🟡 Media |

---

## 📊 DASHBOARD

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| — | KPIs personales (por rol) | Todos | 🔴 Alta |
| — | KPIs globales del hotel | Manager General | 🟡 Media |

---

## ⚙️ SISTEMA *(transversal)*

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| RF-H-08 | Cálculo automático de urgencia | Sistema | 🔴 Alta |
| RF-H-09 | Asignación de Inspector por zona | Sistema | 🔴 Alta |
| RF-H-10 | Reflejo en Schedule | Sistema | 🔴 Alta |
| RF-H-16 | Cálculo de Indicador de Cumplimiento | Sistema | 🔴 Alta |
| — | Notificaciones automáticas | Sistema | 🔴 Alta |
