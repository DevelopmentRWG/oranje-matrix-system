---
tags:
  - arquitectura
  - departamento/ventas
aliases:
  - Requerimientos por Módulo Ventas
---

# REQUERIMIENTOS POR MÓDULO — DEPARTAMENTO DE VENTAS

Agrupación de los RFs definidos en [[03 - Tabla de Requerimientos]] según el módulo del sidebar al que pertenecen.

---

## 📊 PIPELINE (Prospectos)

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| RF-V-01 | Identificar prospecto | BD | 🔴 Alta |
| RF-V-02 | Crear perfil del hotel | BD | 🔴 Alta |
| RF-V-03 | Registrar visita en frío | BD | 🟡 Media |
| RF-V-06 | Registrar intentos de contacto | BD | 🟡 Media |
| RF-V-07 | Avanzar a Amarillo (interés) | BD | 🔴 Alta |
| RF-V-09 | Iniciar negociación (Rosa) | BD + BDC | 🔴 Alta |
| RF-V-15 | Gestionar rechazo (Rojo) | BD | 🟡 Media |
| RF-V-16 | Reactivar prospecto desde Rojo | BD | 🟡 Media |
| RF-V-17 | Marcar estancamiento (Café) | BD / BDC | 🟡 Media |
| RF-V-18 | Desbloquear estancamiento (Café) | BDC | 🟡 Media |
| RF-V-19 | Reactivar desde Café | BDC | 🟡 Media |
| RF-V-20 | Marcar cliente Negro | BDC | 🟡 Media |
| RF-V-21 | Reactivar desde Negro | BDC | 🟢 Baja |
| RF-V-22 | Ver Pipeline | BD / BDC | 🔴 Alta |

---

## 📝 PROPUESTAS

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| RF-V-04 | Elaborar Propuesta Personalizada | BD | 🔴 Alta |
| RF-V-05 | Enviar propuesta al hotel | BD | 🔴 Alta |

---

## 📄 DOCUMENTOS T&C

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| RF-V-08 | Crear Documento de T&C | BD / BDC | 🔴 Alta |
| RF-V-10 | Validar T&C | BDC | 🔴 Alta |

---

## ✅ CONVERSIÓN

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| RF-V-11 | Crear Usuario del Hotel | BDC | 🔴 Alta |
| RF-V-12 | Aprobar conversión a cliente | BDC | 🔴 Alta |

---

## 🗺️ MI TERRITORIO *(BD)*

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| RF-V-23 | Ver Mi Territorio | BD | 🔴 Alta |

---

## 👥 MI EQUIPO *(BDC)*

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| RF-V-24 | Ver Mi Equipo (BDs a cargo) | BDC | 🔴 Alta |
| RF-V-25 | Métricas individuales por BD | BDC | 🟡 Media |

---

## 📈 REPORTES *(BDC)*

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| RF-V-26 | Generar reporte de Ventas | BDC | 🟡 Media |
| RF-V-27 | Enviar reporte a dirección | BDC | 🟡 Media |

---

## 🏨 CLIENTES ACTIVOS

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| RF-V-29 | Ver Clientes Activos (referente comercial) | BD / BDC | 🟡 Media |

---

## 📊 DASHBOARD

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| — | KPIs personales (BD: mi territorio) | BD | 🔴 Alta |
| — | KPIs del equipo (BDC) | BDC | 🔴 Alta |

---

## ⚙️ SISTEMA *(transversal)*

| RF | Nombre | Rol(es) | Prioridad |
|---|---|---|---|
| RF-V-13 | Trigger Automático de Conversión | Sistema | 🔴 Alta |
| RF-V-14 | Cambio automático a Naranja | Sistema | 🔴 Alta |
| RF-V-28 | Trazabilidad de cambios de status | Sistema | 🔴 Alta |
| — | Notificaciones automáticas | Sistema | 🔴 Alta |
