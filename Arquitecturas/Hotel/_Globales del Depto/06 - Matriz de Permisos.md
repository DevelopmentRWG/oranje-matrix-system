---
tags:
  - arquitectura
  - departamento/hotel
aliases:
  - Matriz de Permisos Hotel
---

# MATRIZ DE PERMISOS — DEPARTAMENTO DE HOTEL

**PRD-HOTEL-01 · Sistema de Gestión de Personal**

> [!info]
> El rol **Administrador (ROL-H-05)** se encuentra **en pausa** mientras se estabilizan las reglas de negocio. Los permisos del Admin se completarán al final.

> [!note]
> El **Manager General (ROL-H-03)** existe únicamente en **jerarquía extendida**. En jerarquía simple, sus celdas son N/A.

---

| Módulo | Funcionalidad / Acción | ROL-H-01 Supervisor | ROL-H-02 Manager del Hotel | ROL-H-03 Manager General | ROL-H-04 Sistema | ROL-H-05 Admin |
|---|---|---|---|---|---|---|
| **REQUISICIONES** | 👁️ Ver mis requisiciones | Ver | Ver | Ver | Auto | ⏸️ |
| | 👁️ Ver vista global del hotel | — | Solo su depto | Ver global | Auto | ⏸️ |
| | ➕ Crear requisición | Crear | — | — | — | ⏸️ |
| | 📝 Editar borrador | C · E | — | — | — | ⏸️ |
| | 📤 Enviar a autorización | Crear | — | — | — | ⏸️ |
| | ✓ Autorizar requisición | — | Aprobar | — | — | ⏸️ |
| | ✗ Rechazar con observaciones | — | Rechazar | — | — | ⏸️ |
| | 🗑️ Eliminar requisición vacía | Crear | — | — | Auto | ⏸️ |
| | 🗑️ Eliminar requisición con posiciones | — | C · E | — | Auto | ⏸️ |
| | 🚦 Calcular Semáforo de Urgencia | — | — | — | Auto | ⏸️ |
| | 🤖 Asignar Inspector por zona | — | — | — | Auto | ⏸️ |
| | 💬 Comentar al expediente | — | — | C · E | — | ⏸️ |
| | 🚨 Escalar requisición demorada | — | — | Supervisar | — | ⏸️ |
| **SCHEDULE** | 👁️ Ver Schedule del depto | Ver | Ver | Ver | Auto | ⏸️ |
| | 👁️ Ver Schedule global del hotel | — | — | Ver | Auto | ⏸️ |
| | 📝 Editar Schedule semanal | — | C · E | — | — | ⏸️ |
| | 🔄 Reflejar posiciones autorizadas | — | — | — | Auto | ⏸️ |
| | 🔔 Sugerir refuerzo de personal | Crear | — | — | — | ⏸️ |
| | 📥 Exportar Schedule | Ver | Ver | Ver | — | ⏸️ |
| **TIMESHEET** | 👁️ Ver Timesheet del depto | Ver | Ver | Ver | Auto | ⏸️ |
| | 👁️ Ver Timesheet global del hotel | — | — | Ver | Auto | ⏸️ |
| | 📷 Generar / Renovar QR | — | Crear | — | — | ⏸️ |
| | 📝 Corregir ponche | — | C · E | — | Auto | ⏸️ |
| | 🚦 Calcular Indicador de Cumplimiento | — | — | — | Auto | ⏸️ |
| | ⏰ Ver Indicador de Lunch Extendido | — | — | — | Auto | ⏸️ |
| | 📥 Exportar Timesheet | Ver | Ver | Ver | — | ⏸️ |
| **MI PERSONAL** | 👁️ Ver colaboradores asignados | Ver | Ver | Ver | Auto | ⏸️ |
| | 🩷 Poner en Stand-by (Rosa) | C · E | C · E | — | — | ⏸️ |
| | 🔴 Reportar colaborador (Rojo) | — | Reportar | — | — | ⏸️ |
| | 👁️ Ver historial del colaborador | Ver | Ver | Ver | Auto | ⏸️ |
| **ACCIDENTES** | 👁️ Ver accidentes del depto | Ver | Ver | Ver | Auto | ⏸️ |
| | ➕ Crear tarjeta de accidente — Escenario A | Crear | — | — | — | ⏸️ |
| | ➕ Crear tarjeta de accidente — Escenario B | Crear | — | — | — | ⏸️ |
| | 📷 Capturar evidencia presencial | C · E | — | — | — | ⏸️ |
| | 🤖 Notificar al Inspector | — | — | — | Auto | ⏸️ |
| **MI EQUIPO DEL HOTEL** *(GM)* | 👁️ Ver Gerentes de Departamento | — | — | Ver | — | ⏸️ |
| | 👁️ Ver Supervisores del hotel | — | — | Ver | — | ⏸️ |
| | 💬 Comunicar con Gerente / SUP | — | — | C · E | — | ⏸️ |
| | 📊 Solicitar reporte específico | — | — | Crear | — | ⏸️ |
| **REPORTES** *(GM)* | ➕ Generar reporte ejecutivo | — | — | Crear | Auto | ⏸️ |
| | 📤 Enviar a dirección | — | — | Crear | — | ⏸️ |
| | 📅 Programar envío recurrente | — | — | C · E | — | ⏸️ |
| | 👁️ Ver histórico de reportes | — | — | Ver | Auto | ⏸️ |
| **BLACKLIST** | 👁️ Consultar Blacklist | Ver | Ver | Ver | Auto | ⏸️ |
| | ➕ Agregar a Blacklist | — | — | — | — | ⏸️ |
| | 📝 Remover de Blacklist | — | — | — | — | ⏸️ |
| **DASHBOARD** | 👁️ Ver KPIs personales | Ver | Ver | Ver | Auto | ⏸️ |
| | 👁️ Ver KPIs del depto | — | Ver | Ver | Auto | ⏸️ |
| | 👁️ Ver KPIs globales del hotel | — | — | Ver | Auto | ⏸️ |
| **SISTEMA** *(transversal)* | 👁️ Recibir notificación | Ver | Ver | Ver | Auto | ⏸️ |
| | ⚙️ Enviar notificación automática | — | — | — | Auto | ⏸️ |
| | 🔢 Numeración automática de requisiciones | — | — | — | Auto | ⏸️ |
| **CONFIGURACIÓN** *(Admin EN PAUSA)* | ⏸️ Configurar alertas | — | — | — | — | ⏸️ Por confirmar |
| | ⏸️ CRUD de usuarios | — | — | — | — | ⏸️ Por confirmar |
| | ⏸️ Editar catálogos | — | — | — | — | ⏸️ Por confirmar |

---

## Notas clave

- **Capa de seguridad (RR-H-02):** solo el Manager del Hotel autoriza requisiciones. El Supervisor crea pero NO puede saltarse este paso.
- **QR del Timesheet (RR-H-09):** generación exclusiva del Manager del Hotel. El Supervisor no tiene acceso.
- **Reportar colaborador / Rojo (RR-H-10):** acción exclusiva del Manager del Hotel.
- **Stand-by / Rosa (RR-H-11):** compartido entre Manager del Hotel y Supervisor.
- **Indicador de Lunch Extendido (RR-H-15):** restringido para todos los roles del Hotel — solo lo ven Inspector, Coordinador de Inspección y Manager de Reclutamiento.
- **Blacklist:** consulta global. Las acciones de Crear / Resolver disputa / Remover son exclusivas del depto Reclutamiento (no del Hotel).
- **Manager General:** sin operación diaria. Su rol es supervisar, escalar y reportar a dirección.
