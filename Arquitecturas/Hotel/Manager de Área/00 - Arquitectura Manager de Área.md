---
tags:
  - arquitectura
  - modulo/hotel
aliases:
  - Arquitectura Manager de Área
  - Wireframe Manager de Área
  - Arquitectura Gerente de Departamento
---

# Arquitectura — Manager de Área (Gerente de Departamento)

Wireframe de la plataforma Oranje para el rol [[Hotel/Manager de Área|Manager de Área]]. Define el flujo de entrada, header global, sidebar de módulos y el detalle de cada módulo al que tiene acceso.

> [!info]
> En **jerarquía simple** este rol es la máxima autoridad del lado del hotel. En **jerarquía extendida**, este rol corresponde al **Gerente de Departamento** (uno por departamento: Housekeeping, Alimentos, Mantenimiento, Front Desk), subordinado al [[Hotel/Manager General|Manager General]]. Las responsabilidades en plataforma son las mismas; solo cambia el alcance (todo el hotel vs. su departamento).

> [!important]
> **Capa de seguridad:** este rol es el único que puede **autorizar** requisiciones (regla del Hotel). El Supervisor crea, pero solo el Manager de Área envía la requisición a Reclutamiento.

## N0 — Inicio

```
PLATAFORMA ORANGE
        │
        ▼
LOGIN / AUTORIZACIÓN
        │
        ▼
ROL IDENTIFICADO / MANAGER DE ÁREA (o GERENTE DE DEPARTAMENTO)
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
- Rol: Manager de Área / Gerente de Departamento

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

## N1 — SIDEBAR (Módulos del Manager de Área)

```
SIDEBAR
   ├─ DASHBOARD
   ├─ REQUISICIONES        (crear / autorizar / rechazar / ver historial del depto)
   ├─ SCHEDULE             (gestión semanal)
   ├─ TIMESHEET            (revisar ponches + generar QR)
   ├─ MI PERSONAL          (colaboradores asignados — Stand-by / Reportar)
   └─ ACCIDENTES           (reportar y dar seguimiento)
```

> [!note]
> El Manager de Área **NO** tiene módulo de Pool de Colaboradores ni de Reclutamiento — esos son del lado de Oranje. Solo ve los colaboradores asignados a su hotel/depto.

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

### Acciones
- ➕ **Crear requisición** *(el Manager de Área también puede crear, no solo el Supervisor)*.
- ✏️ **Editar borrador** de mis requisiciones.
- 📤 **Enviar a autorización** (si la creo yo, puedo autorizarla yo mismo o que la apruebe el Manager General).
- ✅ **Autorizar requisición** *(envía a Reclutamiento — modelo Self-Pick)*.
- ❌ **Rechazar con observaciones** *(devuelve al creador en estado En elaboración)*.
- 👁️ **Ver historial / journal** de la requisición.
- 🗑️ **Eliminar requisición** *(con justificación si tiene posiciones)*.

> [!important]
> **Autorización compartida con Manager General.** Solo el Manager de Área o el Manager General pueden autorizar. Si el Supervisor intenta autorizar, el sistema bloquea con: *"Solo el gerente del hotel puede autorizar la requisición"*. Si la requisición no tiene posiciones: *"No tiene posiciones registradas, registre al menos una posición e intente nuevamente"*.

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
- Departamento *(solo Manager General; el Manager de Área ve solo el suyo)*.
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
- 📷 **Generar / Renovar código QR** del depto *(exclusivo del Manager de Área)* — para que los colaboradores ponchen.
- 👁️ **Ver detalle de jornada** de un colaborador.
- ✏️ **Corregir ponche** (con justificación obligatoria — queda en log auditable).
- 📤 **Exportar Timesheet** semanal (PDF/CSV).

> [!warning]
> El Manager de Área **NO tiene acceso** al Indicador de Lunch Extendido — ese es exclusivo de roles internos de Oranje (Inspector, Coordinador de Inspección, Manager de Reclutamiento).

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
- 🩷 **Poner en Stand-by (Rosa)** *(Manager de Área y Supervisor)* — sin Schedule ni Timesheet hasta que se cambie el estado.
- 🔴 **Reportar colaborador (Rojo)** *(exclusivo del Manager de Área)* — inicia investigación del Inspector.
- 👁️ **Ver historial** de incidencias / asignaciones.
- 📞 **Contactar al colaborador** (teléfono / mensaje).

> [!important]
> Manager de Área, Manager General y Supervisor pueden poner en Stand-by (Rosa) y pueden reportar al colaborador (Rojo).

---

## 🚨 Módulo ACCIDENTES LABORALES

> [!info]
> El Manager de Área también participa en el reporte de accidentes laborales (junto al Supervisor y al Manager General). Cuando detecta un accidente en su departamento, crea la tarjeta de accidente con captura presencial.

### Sub-vistas
- 🟢 **Activos** — accidentes en proceso de investigación por el Inspector.
- ✅ **Cerrados** — casos resueltos (último mes).
- 📂 **Histórico** — todos los accidentes del depto.

### Detalle del accidente
- Datos del colaborador afectado.
- Fecha, hora, ubicación exacta.
- Circunstancias y testigos.
- Atención inmediata brindada.
- Estado del colaborador (pasa a **Gris (Accidentado)** en el Semáforo del Colaborador — protección contra la regla de 3 inasistencias).
- Inspector de zona asignado automáticamente.

### Acciones

#### Escenario A — Colaborador reporta desde la app
1. Notificación simultánea al Supervisor, Manager de Área e Inspector.
2. Si el Manager de Área acude físicamente (o si el Supervisor no está disponible), captura la información presencial: ubicación exacta, circunstancias, testigos, atención inmediata.

#### Escenario B — El propio Manager de Área detecta el accidente
1. Crea la tarjeta de accidente desde la app:
   - 📝 Datos del accidente
   - 📷 Adjunta fotos / evidencia
   - 👤 Identifica al colaborador afectado
2. La señal llega al Inspector de zona automáticamente.

### Filtros
- Estado del caso (Activo / Cerrado)
- Colaborador afectado
- Inspector asignado
- Rango de fechas

---

## Flujo operativo del Manager de Área

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

| Aspecto | Supervisor | Manager de Área | Manager General |
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
║         ROL: MANAGER DE ÁREA / GERENTE DE DEPTO             ║
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
└──────────────┴───────────────────────────────────────────────┘
```

---

## Relacionado

- [[Hotel/Manager de Área|Manager de Área]] (definición del rol)
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
- [[Departamentos del Hotel]]
- [[Inspector]]
