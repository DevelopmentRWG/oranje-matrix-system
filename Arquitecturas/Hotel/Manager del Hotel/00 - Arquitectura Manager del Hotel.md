---
tags:
  - arquitectura
  - modulo/hotel
aliases:
  - Arquitectura Manager del Hotel
  - Wireframe Manager del Hotel
  - Arquitectura Gerente de Departamento
---

# Arquitectura — Manager del Hotel (Gerente de Departamento)

Wireframe de la plataforma Oranje para el rol [[Hotel/Manager del Hotel|Manager del Hotel]]. Define el flujo de entrada, header global, sidebar de módulos y el detalle de cada módulo al que tiene acceso.

> [!info]
> En **jerarquía simple** este rol es la máxima autoridad del lado del hotel. En **jerarquía extendida**, este rol corresponde al **Gerente de Departamento** (uno por departamento: Housekeeping, Alimentos, Mantenimiento, Front Desk), subordinado al [[Hotel/Manager General|Manager General]]. Las responsabilidades en plataforma son las mismas; solo cambia el alcance (todo el hotel vs. su departamento).

> [!important]
> **Capa de seguridad:** este rol es el único que puede **autorizar** requisiciones (regla del Hotel). El Supervisor crea, pero solo el Manager del Hotel envía la requisición a Reclutamiento.

## N0 — Inicio

```
PLATAFORMA ORANGE
        │
        ▼
LOGIN / AUTORIZACIÓN
        │
        ▼
ROL IDENTIFICADO / MANAGER DEL HOTEL (o GERENTE DE DEPARTAMENTO)
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
- Rol: Manager del Hotel / Gerente de Departamento

**Mi hotel / departamento**
- Nombre del hotel
- Departamento asignado *(solo en jerarquía extendida — Housekeeping, Alimentos, Mantenimiento, Front Desk)*
- Zona del hotel

**Mis métricas (mes en curso)**
- Requisiciones autorizadas
- Posiciones cubiertas / pendientes
- Colaboradores activos en mi depto
- Indicador de Cumplimiento del Timesheet (estado del depto)

**Configuración**
- Cambiar contraseña
- Preferencias de notificación

🚪 Cerrar sesión

### 🔍 BUSCADOR (global)

**Qué se puede buscar**
- Requisiciones por ID o número
- Colaboradores asignados (por nombre / posición)
- Posiciones del Schedule (por día / posición)
- Vetados en [[Core/Módulos/Blacklist|Blacklist]] (consulta)

**Cómo funciona**
- Resultados en vivo agrupados por tipo
- Atajo: `/` o `Ctrl+K`

### 🔔 NOTIFICACIONES (campanita con badge)

**Por tipo de evento**
- 📋 Nueva requisición creada por el Supervisor → pendiente de autorización
- ✅ Reclutamiento tomó una requisición autorizada
- 👤 Colaborador asignado por Reclutamiento (entra a mi Schedule)
- 🟢 Requisición cubierta al 100%
- 🔴 Colaborador reportado / accidente laboral en mi depto
- ⏱️ Indicador de Cumplimiento del Timesheet entró a Rojo
- 🛡️ QA detectó incidencia en mi depto

**Estados**
- 🟠 Sin leer (cuenta en el badge)
- 🟢 Leída

---

## N1 — SIDEBAR (Módulos del Manager del Hotel)

```
SIDEBAR
   ├─ DASHBOARD
   ├─ REQUISICIONES        (autorizar / rechazar / ver historial del depto)
   ├─ SCHEDULE             (gestión semanal)
   ├─ TIMESHEET            (revisar ponches + generar QR)
   ├─ MI PERSONAL          (colaboradores asignados — Stand-by / Reportar)
   └─ BLACKLIST            (consulta)
```

> [!note]
> El Manager del Hotel **NO** tiene módulo de Pool de Colaboradores ni de Reclutamiento — esos son del lado de Oranje. Solo ve los colaboradores asignados a su hotel/depto.

---

## 📊 Módulo DASHBOARD

### KPIs personales del depto
- Requisiciones pendientes de autorizar (badge rojo si >24h)
- Requisiciones autorizadas en proceso de cobertura
- Posiciones del depto con cobertura parcial
- Colaboradores activos
- Colaboradores en Stand-by (Rosa)
- Colaboradores reportados (Rojo)
- Accidentes laborales del mes
- Indicador de Cumplimiento del Timesheet (semaforizado)

### Vistas resumen
- **Requisiciones del Supervisor pendientes:** lista corta con CTA "Revisar y autorizar".
- **Schedule de la semana:** vista calendario con posiciones cubiertas / vacantes.
- **Posiciones críticas** (sin colaborador asignado y fecha de inicio < 72h).

### Acciones rápidas
- Revisar requisición pendiente
- Generar / Renovar QR
- Ver Schedule de la semana
- Reportar colaborador

---

## 📋 Módulo REQUISICIONES

### Sub-vistas (por estado del [[Semáforo de Requisición]])

- 🟢 **Pendientes de autorización** *(Verde manzana — En elaboración)* — creadas por mi Supervisor, esperando mi revisión.
- 🟠 **Autorizadas** — ya enviadas a Reclutamiento, esperando que tomen la requisición.
- 🟡 **En proceso** — Reclutamiento las tomó y está asignando colaboradores.
- 🔵 **Cubiertas** — al 100% de cobertura.
- 🔴 **Rechazadas** — devueltas al Supervisor con observaciones.
- 📂 **Toda** — vista completa del histórico del depto.

### Filtros
- Estado (semáforo)
- Urgencia ([[Semáforo de Urgencia de Requisición]])
- Posición ([[Posiciones]])
- Fecha de creación (rango)
- Buscar por ID o número de requisición

### Detalle
- **Cabecera:** ID requisición + número + Supervisor que la creó + fecha + estado.
- **Posiciones solicitadas:** cantidad, posición, modalidad, nivel de inglés, horario, fecha de inicio.
- **Notas adicionales** del Supervisor.
- **Cobertura actual** ([[Semáforo de Posiciones de la Requisición]]).
- **Colaboradores asignados** (cuando Reclutamiento ya empezó).

### Acciones (exclusivas del Manager del Hotel)
- ✅ **Autorizar requisición** *(envía a Reclutamiento — modelo Self-Pick)*.
- ❌ **Rechazar con observaciones** *(devuelve al Supervisor en estado En elaboración)*.
- 👁️ **Ver historial / journal** de la requisición.
- 🗑️ **Eliminar requisición** *(solo si aún no está autorizada)*.

> [!important]
> Si el Supervisor intenta autorizar, el sistema bloquea con: **"Solo el gerente del hotel puede autorizar la requisición"**. Si la requisición no tiene posiciones: **"No tiene posiciones registradas, registre al menos una posición e intente nuevamente"**.

### Efectos automáticos al autorizar
| Efecto | Resultado |
|---|---|
| Cálculo de urgencia por posición | >120h → Verde · 72-120h → Amarillo · <72h → Rojo |
| Transición de posiciones | Dorado → Naranja en [[Semáforo de Posiciones de la Requisición]] |
| Reflejo en Schedule | Posiciones aparecen en la semana correspondiente |
| Asignación de Inspector | Automática según zona del hotel |

---

## 📅 Módulo SCHEDULE

### Vista principal
- **Calendario semanal** del hotel/depto (Lunes → Domingo).
- Filas: posiciones requeridas (Housekeeper, Hoseman, Chef, etc.).
- Columnas: días de la semana.
- Celdas: colaborador asignado + horario, o "Vacante" en rojo.

### Filtros
- Departamento *(solo Manager General; el Manager del Hotel ve solo el suyo)*.
- Posición.
- Estado de cobertura (cubierta / parcial / vacante).
- Semana (selector).

### Acciones
- ✏️ **Editar asignación** *(reordenar turnos, cambiar horarios dentro de la posición)*.
- 🔁 **Mover colaborador** entre días/turnos (sin cambiar la posición).
- ⏸️ **Marcar día como descanso** del colaborador.
- 📥 **Exportar Schedule de la semana** (PDF/CSV).
- 🔔 **Solicitar refuerzo a Reclutamiento** (genera nueva requisición express si una posición queda vacante).

> [!info]
> El Schedule es el **eje del módulo Hotel**. El Timesheet se construye sobre él — sin Schedule no hay registro de tiempo.

---

## ⏱️ Módulo TIMESHEET

### Vista principal
- **Tabla semanal** de colaboradores × días con sus 6 ponches del día (Entrada, Salida Lunch, Entrada Lunch, Salida Break, Entrada Break, Salida).
- Indicador por jornada: horas brutas, deducción de Lunch, horas netas.
- **Indicador de Cumplimiento del Timesheet** semaforizado por colaborador (Verde / Amarillo / Rojo).

### Filtros
- Colaborador
- Posición
- Día / semana
- Estado del Indicador de Cumplimiento

### Acciones
- 📷 **Generar / Renovar código QR** del depto *(exclusivo del Manager del Hotel)* — para que los colaboradores ponchen.
- 👁️ **Ver detalle de jornada** de un colaborador.
- ✏️ **Corregir ponche** (con justificación obligatoria — queda en log auditable).
- 📤 **Exportar Timesheet** semanal (PDF/CSV).

> [!warning]
> El Manager del Hotel **NO tiene acceso** al Indicador de Lunch Extendido — ese es exclusivo de roles internos de Oranje (Inspector, Coordinador de Inspección, Manager de Reclutamiento).

### Reglas de deducción de Lunch (visibles en cada jornada)
| Escenario | Deducción aplicada |
|---|---|
| Lunch < 30 min | 30 min (mínimo obligatorio) |
| Lunch ≥ 30 min | Tiempo real tomado |
| Sin ponche de Lunch | 30 min (auto-deducción) |

---

## 👥 Módulo MI PERSONAL

### Lista
- Colaboradores asignados al hotel/depto, con [[Semáforo del Colaborador]] visible:
  - 🟠 Naranja — Fijo
  - 🟢 Verde manzana — Día 1-2 onboarding
  - 🔵 Azul claro — Día 3+ entrega uniforme
  - 🩷 Rosa — Stand-by
  - 🔴 Rojo — Reportado
  - ⬜ Gris — Accidentado

### Filtros
- Posición
- Estado del semáforo
- Buscar por nombre / documento

### Detalle
- Datos del colaborador (nombre, foto, teléfono, posición, modalidad).
- Schedule del colaborador (días asignados).
- Timesheet semanal (resumen).
- Historial en el hotel (desde cuándo, posiciones que ha cubierto).
- Estado actual del semáforo.

### Acciones
- 🩷 **Poner en Stand-by (Rosa)** *(Manager del Hotel y Supervisor)* — sin Schedule ni Timesheet hasta que se cambie el estado.
- 🔴 **Reportar colaborador (Rojo)** *(exclusivo del Manager del Hotel)* — inicia investigación del Inspector.
- 👁️ **Ver historial** de incidencias / asignaciones.
- 📞 **Contactar al colaborador** (teléfono / mensaje).

> [!important]
> Tanto el Manager del Hotel como el Supervisor pueden poner en Stand-by. Solo el Manager del Hotel puede reportar (Rojo).

---

## ⚫ Módulo BLACKLIST (consulta)

### Lista
- Colaboradores vetados (visible solo como consulta).
- Por motivo (3 inasistencias, disputa, falta grave).

### Filtros
- Buscar por nombre / documento
- Por motivo
- Por fecha de ingreso

### Detalle
- Info del colaborador
- Motivo del veto
- Fecha de ingreso

> [!warning]
> El Manager del Hotel **NO** puede agregar ni remover de Blacklist — esa acción es del depto Reclutamiento (todos los roles del depto pueden agregar; solo el Manager de Reclutamiento resuelve disputas y remueve).

---

## Flujo operativo del Manager del Hotel

```
1. Login → Dashboard
   │
   ▼
2. Reviso requisiciones pendientes creadas por mi Supervisor
   │
   ├─→ Autorizo → pasa a Reclutamiento (Self-Pick)
   └─→ Rechazo → vuelve al Supervisor con observaciones
   │
   ▼
3. Reclutamiento toma la requisición y asigna colaboradores
   │
   ▼
4. Los colaboradores aparecen en mi Schedule semanal
   │
   ▼
5. Genero QR para que ponchen en Timesheet
   │
   ▼
6. Reviso Timesheet semanal:
      • Verifico cumplimiento (semáforo Verde / Amarillo / Rojo)
      • Corrijo ponches con justificación si aplica
   │
   ▼
7. Gestión continua:
      • Stand-by (Rosa) por temporada baja / decisión del hotel
      • Reportar (Rojo) si hay falta grave
      • Recibir alertas de QA y de Inspector
```

---

## Diferencias clave vs Supervisor y Manager General

| Aspecto | Supervisor | Manager del Hotel | Manager General |
|---|---|---|---|
| Crear requisición | ✅ | ❌ | ❌ |
| Autorizar requisición | ❌ | ✅ exclusivo | ❌ |
| Rechazar con observaciones | ❌ | ✅ | ❌ |
| Generar QR (Timesheet) | ❌ | ✅ exclusivo | ❌ |
| Poner en Stand-by (Rosa) | ✅ | ✅ | ❌ |
| Reportar colaborador (Rojo) | ❌ | ✅ exclusivo | ❌ |
| Gestionar Schedule semanal | Consulta | ✅ edición | Visibilidad global |
| Reportar accidente laboral | ✅ | — | ❌ |
| Visibilidad global del hotel | ❌ | Solo su depto | ✅ todos los deptos |

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
║         ROL: MANAGER DEL HOTEL / GERENTE DE DEPTO             ║
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
│ 📊 Dashboard │  KPIs del depto · Acciones rápidas            │
│ 📋 Requisic. │  Pendientes · Autorizar / Rechazar · Histor.  │
│ 📅 Schedule  │  Calendario semanal · Editar · Exportar       │
│ ⏱️ Timesheet │  Ponches · Generar QR · Cumplimiento          │
│ 👥 Personal  │  Mis colaboradores · Stand-by · Reportar      │
│ ⚫ Blacklist │  Consulta · Motivos · Histórico               │
└──────────────┴───────────────────────────────────────────────┘
```

---

## Relacionado

- [[Hotel/Manager del Hotel|Manager del Hotel]] (definición del rol)
- [[Hotel/Supervisor|Supervisor]]
- [[Hotel/Manager General|Manager General]]
- [[Hotel/Hotel|Hotel]]
- [[Hotel/Reglas del Hotel|Reglas del Hotel]]
- [[Core/Módulos/Requisicion/Requisición|Requisición]]
- [[Core/Módulos/Requisicion/Flujo de Requisición|Flujo de Requisición]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Timesheet]]
- [[Semáforo de Requisición]]
- [[Semáforo del Colaborador]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Departamentos del Hotel]]
- [[Inspector]]
