---
tags:
  - arquitectura
  - modulo/hotel
aliases:
  - Arquitectura Manager General
  - Wireframe Manager General
  - Arquitectura GM
---

# Arquitectura — Manager General

Wireframe de la plataforma Oranje para el rol [[Hotel/Manager General|Manager General]]. Define el flujo de entrada, header global, sidebar de módulos y el detalle de cada módulo al que tiene acceso.

> [!info]
> El Manager General es el rol de **máxima autoridad del lado del hotel**, **solo en jerarquía extendida**. Supervisa a los Gerentes de Departamento (Manager del Hotel de cada depto) y tiene visibilidad global del Schedule y Timesheet de todo el hotel.

> [!important]
> El Manager General **NO autoriza requisiciones directamente** — esa responsabilidad recae en cada Gerente de Departamento. Su rol es de **supervisión, visibilidad global y reporte directivo**, no operativo.

> [!warning]
> Este rol **NO existe** en jerarquía simple. En hoteles pequeños, el Manager del Hotel es la máxima autoridad.

## N0 — Inicio

```
PLATAFORMA ORANGE
        │
        ▼
LOGIN / AUTORIZACIÓN
        │
        ▼
ROL IDENTIFICADO / MANAGER GENERAL (GM)
        │
        ▼
MÓDULOS / SIDEBAR
```

---

## HEADER (presente en toda la app)

### 👤 PERFIL DEL USUARIO (dropdown)

**Mi información**
- Nombre completo + foto
- Correo + teléfono
- Rol: Manager General (GM)

**Mi hotel**
- Nombre del hotel
- Zona del hotel
- Cantidad de departamentos operativos
- Cantidad de Gerentes de Departamento a cargo
- Cantidad de Supervisores totales

**Mis métricas globales (mes en curso)**
- Cobertura global del hotel (% de posiciones cubiertas)
- Requisiciones autorizadas (total del hotel)
- Colaboradores activos
- Indicador de Cumplimiento del Timesheet (consolidado)
- Indicador de Calidad del depto Hotel ([[QA]])

**Configuración**
- Cambiar contraseña
- Preferencias de notificación

🚪 Cerrar sesión

### 🔍 BUSCADOR (global)

**Qué se puede buscar**
- Requisiciones (cualquier depto del hotel)
- Colaboradores asignados (cualquier depto)
- Schedule por posición / día
- Gerentes de Departamento y Supervisores del hotel
- Vetados en [[Core/Módulos/Blacklist|Blacklist]] (consulta)

**Cómo funciona**
- Resultados en vivo agrupados por tipo
- Atajo: `/` o `Ctrl+K`

### 🔔 NOTIFICACIONES (campanita con badge)

**Por tipo de evento**
- 🔴 Requisición en urgencia Red sin autorizar (>24h)
- 🟢 Cobertura crítica de un departamento (visibilidad global)
- 🚨 Accidente laboral grave en cualquier depto
- 🛡️ Indicador de Calidad de QA bajó a Rojo
- 📊 Reporte semanal/mensual disponible
- ⏱️ Indicador de Cumplimiento del Timesheet en Rojo (consolidado)
- 🔁 Cambio organizacional (alta/baja de Gerente o Supervisor)

**Estados**
- 🟠 Sin leer (cuenta en el badge)
- 🟢 Leída

---

## N1 — SIDEBAR (Módulos del Manager General)

```
SIDEBAR
   ├─ DASHBOARD
   ├─ SCHEDULE GLOBAL      (todos los deptos — consulta)
   ├─ TIMESHEET GLOBAL     (todos los deptos — consulta)
   ├─ REQUISICIONES        (vista global — consulta + supervisión)
   ├─ MI EQUIPO DEL HOTEL  (Gerentes de Depto + Supervisores)
   ├─ REPORTES             (consolidados + envío a dirección)
   └─ BLACKLIST            (consulta)
```

> [!note]
> El Manager General NO tiene módulo de "Mi Personal" operativo, NO genera QR, NO autoriza requisiciones, NO pone Stand-by. Su sidebar está orientado a **consulta global y reportes ejecutivos**, no a operación diaria.

---

## 📊 Módulo DASHBOARD

### KPIs globales del hotel
- **Cobertura global** (% de posiciones cubiertas — todos los deptos)
- **Cobertura por depto** (Housekeeping, Alimentos, Mantenimiento, Front Desk)
- **Requisiciones pendientes de autorizar** (alerta si algún Gerente tarda)
- **Requisiciones en proceso de cobertura** (Reclutamiento trabajándolas)
- **Colaboradores activos** (total + por depto)
- **Indicador de Cumplimiento del Timesheet** (consolidado y por depto)
- **Indicador de Calidad** ([[QA]] — semaforizado por depto)
- **Accidentes laborales** del mes (total)

### Vistas resumen
- **Heatmap de cobertura** por depto y día de la semana.
- **Ranking de Gerentes de Departamento** por velocidad de autorización y cobertura.
- **Alertas críticas** (cualquier depto con cobertura <70%, accidente laboral abierto, calidad en Rojo).

### Acciones rápidas
- 👁️ Ver Schedule global de la semana
- 👁️ Ver Reporte mensual
- 📤 Solicitar reporte a un Gerente de Departamento
- 🚨 Ver casos críticos abiertos

---

## 📅 Módulo SCHEDULE GLOBAL (consulta)

### Vista principal
- **Calendario semanal consolidado del hotel** (Lunes → Domingo).
- Vista por **depto**: Housekeeping / Alimentos / Mantenimiento / Front Desk.
- Vista **agregada**: total de posiciones cubiertas vs vacantes por día.

### Filtros
- Departamento
- Posición
- Estado de cobertura
- Semana / mes

### Acciones (consulta)
- 👁️ **Ver detalle** de cualquier asignación.
- 📥 **Exportar Schedule consolidado** (PDF/CSV/Excel).
- 🔔 **Alertar al Gerente de Departamento** si detecta vacantes críticas.

> [!note]
> El Manager General NO edita el Schedule. La gestión operativa la hace cada Gerente de Departamento en su Schedule.

---

## ⏱️ Módulo TIMESHEET GLOBAL (consulta)

### Vista principal
- **Tabla consolidada del hotel** con filtro por depto.
- Indicador de Cumplimiento del Timesheet por colaborador (Verde / Amarillo / Rojo).
- Resumen por depto: horas pagables, horas brutas, deducciones.

### Filtros
- Departamento
- Colaborador
- Posición
- Día / semana

### Acciones (consulta)
- 👁️ Ver detalle de jornada de cualquier colaborador del hotel.
- 📤 Exportar Timesheet consolidado (PDF/CSV).
- 📊 Generar reporte de cumplimiento por depto.

> [!warning]
> El Manager General **NO genera QR**, **NO corrige ponches**, **NO ve el Indicador de Lunch Extendido** (este último es exclusivo de roles internos de Oranje).

---

## 📋 Módulo REQUISICIONES (vista global, supervisión)

### Sub-vistas (todas son consulta + supervisión)
- 🟢 **Pendientes de autorización** (cualquier depto del hotel).
- 🟠 **Autorizadas** (en Reclutamiento).
- 🟡 **En proceso** de cobertura.
- 🔵 **Cubiertas**.
- 🔴 **Rechazadas**.
- 📂 **Toda** — vista histórica del hotel.

### Filtros
- Departamento
- Gerente de Departamento responsable
- Estado / urgencia
- Posición
- Rango de fechas

### Detalle
- Misma información que ven los Gerentes de Departamento + Supervisor que la creó + Gerente que la autorizó/rechazó + tiempo de procesamiento.

### Acciones (perfil supervisor)
- 👁️ **Ver detalle completo** de cualquier requisición del hotel.
- 💬 **Comentar al expediente** (visible para el Gerente de Departamento).
- 🚨 **Solicitar al Gerente de Departamento** que priorice una requisición demorada.
- 📤 **Escalar a Reclutamiento** si una requisición lleva tiempo sin tomar.
- 📊 **Generar reporte** de tiempos de autorización por Gerente.

> [!important]
> El Manager General **NO autoriza ni rechaza** requisiciones — la autorización es responsabilidad exclusiva del Gerente de Departamento. La intervención del Manager General es solo de supervisión y escalamiento.

---

## 👥 Módulo MI EQUIPO DEL HOTEL

### Sub-vistas
- 🧑‍💼 **Gerentes de Departamento** — uno por depto operativo.
- 🦺 **Supervisores** — listado consolidado por depto.

### Lista de Gerentes de Departamento
- Nombre · depto · n° de Supervisores a cargo · n° de colaboradores activos · % cobertura · tiempo promedio de autorización.

### Lista de Supervisores
- Nombre · depto · Gerente al que reporta · n° de requisiciones creadas (mes) · n° de accidentes reportados.

### Filtros
- Departamento
- Carga (alta / media / baja)
- Buscar por nombre

### Detalle (al click en un Gerente o Supervisor)
- Datos básicos.
- Métricas individuales.
- Historial de requisiciones gestionadas.
- Comunicación (chat / nota interna).

### Acciones
- 👁️ **Ver desempeño** detallado.
- 💬 **Comunicar** con Gerente o Supervisor.
- 📊 **Solicitar reporte** específico.
- 🚨 **Escalar** si se detecta bajo desempeño persistente.

> [!warning]
> El Manager General NO puede dar de alta / baja a Gerentes ni Supervisores (eso lo hace el Administrador del Hotel desde Configuración — fuera del alcance del depto Hotel en plataforma).

---

## 📈 Módulo REPORTES

### Tipos de reporte
- **Cobertura del hotel** (consolidado y por depto).
- **Desempeño por Gerente de Departamento** (tiempos de autorización, % cobertura, casos escalados).
- **Cumplimiento del Timesheet** por depto y colaborador.
- **Calidad** ([[QA]] — métricas y alertas).
- **Accidentes laborales** del periodo.
- **Indicadores ejecutivos** para dirección.

### Filtros
- Rango de fechas (semana / mes / trimestre / personalizado)
- Departamento
- Tipo de reporte

### Acciones
- 📊 **Generar reporte** con vista previa.
- 📥 **Exportar** (PDF / CSV / Excel).
- 📤 **Enviar a dirección** (email / link interno).
- 📅 **Programar envío recurrente** (semanal / mensual).
- 💾 **Guardar como plantilla**.

### Histórico
- Lista de reportes generados con fecha, tipo, destinatarios, estado.
- Reabrir / Reutilizar como plantilla.

---

## ⚫ Módulo BLACKLIST (consulta)

### Lista
- Colaboradores vetados (consulta global).
- Por motivo (3 inasistencias, disputa, falta grave).

### Filtros
- Buscar por nombre / documento
- Por motivo
- Por fecha de ingreso

### Detalle
- Info del colaborador
- Motivo del veto
- Fecha de ingreso
- Quién lo propuso

> [!warning]
> El Manager General NO puede agregar ni remover de Blacklist. Solo consulta.

---

## Flujo operativo del Manager General

```
1. Login → Dashboard
   │
   ▼
2. Reviso KPIs globales del hotel:
      • Cobertura por depto
      • Requisiciones pendientes
      • Indicador de Calidad / Timesheet
      • Casos críticos (accidentes, calidad en Rojo)
   │
   ▼
3. Reviso Schedule y Timesheet globales (consulta)
   │
   ▼
4. Detecto desbalances entre deptos:
      ├─→ Solicito reporte a Gerente de Depto
      ├─→ Comento al expediente de requisiciones demoradas
      └─→ Escalo a Reclutamiento si hace falta
   │
   ▼
5. Genero reportes consolidados:
      • Para mí (operativo)
      • Para dirección (ejecutivo)
   │
   ▼
6. Programo envíos recurrentes a dirección y a mí
```

---

## Diferencias clave vs Supervisor y Manager del Hotel

| Aspecto | Supervisor | Manager del Hotel | Manager General |
|---|---|---|---|
| Crear requisición | ✅ | ❌ | ❌ |
| Autorizar requisición | ❌ | ✅ exclusivo | ❌ |
| Generar QR | ❌ | ✅ | ❌ |
| Editar Schedule | ❌ | ✅ | Solo consulta global |
| Corregir Timesheet | ❌ | ✅ | ❌ |
| Stand-by (Rosa) | ✅ | ✅ | ❌ |
| Reportar (Rojo) | ❌ | ✅ exclusivo | ❌ |
| Reportar accidente | ✅ | — | ❌ |
| Visibilidad global del hotel | ❌ | Solo su depto | ✅ todos los deptos |
| Reportes ejecutivos a dirección | ❌ | ❌ | ✅ exclusivo |
| Supervisión de Gerentes | — | — | ✅ exclusivo |

---

## Diagrama ASCII general del wireframe

```
╔══════════════════════════════════════════════════════════════╗
║                       PLATAFORMA ORANGE                       ║
║                              │                                ║
║                              ▼                                ║
║                   LOGIN / AUTORIZACIÓN                        ║
║                              │                                ║
║                              ▼                                ║
║                    ROL: MANAGER GENERAL (GM)                  ║
╚══════════════════════════════════════════════════════════════╝
                                │
                                ▼
┌──────────────────────────────────────────────────────────────┐
│ HEADER:  [👤 Perfil]   [🔍 Buscador]   [🔔 Notificaciones]   │
└──────────────────────────────────────────────────────────────┘
        │
        ▼
┌──────────────┬───────────────────────────────────────────────┐
│  SIDEBAR     │              ÁREA DE TRABAJO                  │
│              │                                               │
│ 📊 Dashboard │  KPIs globales · Heatmap · Ranking            │
│ 📅 Schedule  │  Schedule consolidado todos los deptos        │
│ ⏱️ Timesheet │  Timesheet consolidado · Cumplimiento         │
│ 📋 Requisic. │  Vista global · Supervisión · Escalamiento   │
│ 👥 Equipo    │  Gerentes de Depto · Supervisores · Métricas  │
│ 📈 Reportes  │  Generar · Enviar dirección · Programar       │
│ ⚫ Blacklist │  Consulta global                              │
└──────────────┴───────────────────────────────────────────────┘
```

---

## Relacionado

- [[Hotel/Manager General|Manager General]] (definición del rol)
- [[Hotel/Manager del Hotel|Manager del Hotel]]
- [[Hotel/Supervisor|Supervisor]]
- [[Hotel/Hotel|Hotel]]
- [[Hotel/Reglas del Hotel|Reglas del Hotel]]
- [[Departamentos del Hotel]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Timesheet]]
- [[Core/Módulos/Semáforos/Indicador de Cumplimiento del Timesheet|Indicador de Cumplimiento del Timesheet]]
- [[Core/Módulos/Semáforos/Indicador de Calidad|Indicador de Calidad]]
- [[QA/QA|QA]]
- [[Semáforo de Requisición]]
- [[Core/Módulos/Blacklist|Blacklist]]
