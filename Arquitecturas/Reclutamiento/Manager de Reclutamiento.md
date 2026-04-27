---
tags:
  - arquitectura
  - modulo/reclutamiento
aliases:
  - Arquitectura Manager de Reclutamiento
  - Wireframe Manager de Reclutamiento
---

# Arquitectura — Manager de Reclutamiento

Wireframe de la plataforma Oranje para el rol [[Manager de Reclutamiento]]. Define el flujo de entrada, header global, sidebar de módulos y el detalle de cada módulo al que tiene acceso.

> [!info]
> El Manager **no asigna requisiciones en el flujo normal**. Las requisiciones llegan al sistema y las [[Reclutadora|Reclutadoras]] (incluidos los [[Reclutamiento/Líder de Grupo de Reclutadoras|Líderes de Grupo]]) las toman libremente según su capacidad. El Manager solo interviene en **casos especiales** (escalamientos, ausencias, requisiciones VIP, balanceo entre grupos).

> [!important]
> **Funciones principales del Manager:**
> 1. Gestionar el equipo (dar de alta Líderes de Grupo y Reclutadoras).
> 2. Resolver problemas y escalamientos.
> 3. Supervisar a los Líderes de Grupo.
> 4. Aprobar/remover Blacklist.
> 5. Ver métricas globales del módulo Reclutamiento.
> 6. Tomar requisiciones excepcionalmente (caso especial).

## N0 — Inicio

```
PLATAFORMA ORANGE
        │
        ▼
LOGIN / AUTORIZACIÓN
        │
        ▼
ROL IDENTIFICADO / MANAGER DE RECLUTAMIENTO
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
- Rol: Manager de Reclutamiento

**Mi equipo**
- Líderes de Grupo a cargo (cantidad)
- Reclutadoras totales (cantidad)
- Zonas cubiertas

**Mis métricas globales (mes en curso)**
- Cobertura global del módulo
- Requisiciones pendientes (sin tomar)
- Casos escalados pendientes
- Reclutadoras y Líderes activos
- Indicador de Calidad del módulo (semáforo de QA)

**Configuración**
- Cambiar contraseña
- Preferencias de notificación

🚪 Cerrar sesión

### 🔍 BUSCADOR (global)

**Qué se puede buscar**
- Requisiciones por ID o número
- Colaboradores por nombre / documento / teléfono
- Hoteles por nombre
- Vetados en [[Core/Módulos/Blacklist|Blacklist]]
- Reclutadoras y Líderes del módulo
- Casos de incidencias / disputas

**Cómo funciona**
- Resultados en vivo agrupados por tipo
- Atajo: `/` o `Ctrl+K`

**Filtros rápidos**
- Tipo (req · colaborador · hotel · blacklist · usuario · caso)
- Búsqueda reciente

### 🔔 NOTIFICACIONES (campanita con badge)

**Por tipo de evento**
- 🚨 Caso escalado por un Líder de Grupo
- 🚨 Caso escalado por un Inspector
- 🔴 Requisición en urgencia Red sin tomar (>X horas)
- ⚫ Solicitud de aprobación de Blacklist
- ⚖️ Disputa de Blacklist resuelta por Inspector (esperando decisión)
- 📊 Reporte recibido de un Líder de Grupo
- 🛡️ Indicador de Calidad del módulo bajó (de QA)
- 👤 Solicitud de alta de nueva Reclutadora / Líder
- 💼 Requisición VIP autorizada (hotel clave)

**Estados**
- 🟠 Sin leer (cuenta en el badge)
- 🟢 Leída

---

## N1 — SIDEBAR (Módulos del Manager)

```
SIDEBAR
   ├─ DASHBOARD
   ├─ REQUISICIONES            (vista global, intervención excepcional)
   ├─ POOL DE COLABORADORES    (consulta + creación de apoyo)
   ├─ BLACKLIST                (CRUD completo — único rol con permiso de vetar)
   ├─ MIS LÍDERES DE GRUPO     ← exclusivo del Manager
   ├─ GESTIÓN DE EQUIPO        ← exclusivo del Manager (alta/edición de roles)
   ├─ INCIDENCIAS / DISPUTAS   ← recibe escalamientos
   ├─ REPORTES                 (recibe de Líderes + genera globales)
   ├─ SCHEDULE                 (consulta)
   └─ CONFIGURACIÓN
```

---

## 📊 Módulo DASHBOARD

### KPIs globales del módulo
- Cobertura global (mes / semana)
- Requisiciones pendientes de tomar (alerta si urgencia Red sin tomar)
- Tasa de cobertura por Líder de Grupo
- Tasa de cobertura por Zona
- Reclutadoras activas vs. inactivas
- Tiempo promedio de cobertura (global)
- Casos escalados abiertos
- Indicador de Calidad del módulo (de [[QA/QA|QA]])

### Vistas resumen
- **Líderes de Grupo (top y bottom):**
  - Top performers: Líder · % cobertura · n° reclutadoras
  - Atención: Líderes con baja cobertura o casos abiertos
- **Requisiciones críticas (sin tomar):**
  - Req #001 · Hotel X · Housekeeper · 🔴 Red · 80h sin tomar
  - Req #002 · Hotel Y · Chef · 🔴 Red · 65h sin tomar
- **Casos escalados pendientes:**
  - Disputa Blacklist · Inspector Juan · 2 días
  - Conflicto reclutadora · Líder Ana · 1 día
- **Indicador de Calidad:** semáforo del módulo Reclutamiento (Verde / Amarillo / Rojo)

### Bandeja Acción
- Solicitudes de aprobación de Blacklist
- Disputas de Blacklist resueltas por Inspector (esperando decisión)
- Reportes recientes de Líderes de Grupo
- Solicitudes de alta de usuarios

### Acciones rápidas
- Aprobar Blacklist
- Resolver disputa
- Tomar requisición crítica (excepcional)
- Generar reporte global
- Dar de alta nueva Reclutadora / Líder

---

## 📋 Módulo REQUISICIONES *(vista global, intervención excepcional)*

### Lista por estado
- 🟢 Autorizadas (sin tomar todavía)
- 🟡 En proceso (alguna Reclutadora/Líder ya la tomó)
- 🔵 Cubiertas (100%)
- 🔴 Parciales
- 🟣 Eliminadas
- 📂 Toda

### Filtro
- Urgencia (🔴 🟡 🟢)
- Posición / Hotel / Zona
- Estado
- Reclutadora o Líder responsable
- Líder de Grupo del responsable (filtro de supervisión)
- Tiempo en cola sin tomar
- Buscar por ID

### Detalle
- Cabecera (hotel, fechas, urgencia)
- Posiciones solicitadas
- Schedule del hotel (contexto)
- Reclutadora/Líder responsable (si la tomaron)
- Colaboradores asignados
- Historial de cambios y journal

### Acciones (intervención excepcional)
- **🎯 Tomar requisición personalmente** *(caso especial)*
- **👤 Asignar manualmente a una Reclutadora/Líder específico** *(caso VIP, balanceo, ausencia)* — requiere comentario obligatorio justificando
- Reasignar a otra Reclutadora
- Forzar cambio de semáforo (con justificación, queda en log)
- Marcar como cubierta / parcial
- Reportar problema o escalar

> [!warning]
> El Manager **no toma requisiciones de forma habitual**. Solo interviene cuando:
> - Una requisición lleva mucho tiempo en cola sin que nadie la tome.
> - Es una requisición VIP de un hotel clave.
> - Hay que balancear carga entre grupos.
> - Un Líder de Grupo no está disponible (vacaciones, baja).
> - Hay que corregir una asignación errónea.
> Cada intervención queda registrada con motivo en el journal.

---

## 🧑‍🤝‍🧑 Módulo POOL DE COLABORADORES

### Lista
Mismo Pool que ven Reclutadoras y Líderes, con todos los estados del [[Semáforo del Colaborador]].

### Filtros
- Posición · Zona · Modalidad · Inglés
- Estado del semáforo
- Buscar por nombre / documento / teléfono

### Detalle
- Datos personales y laborales del colaborador
- Historial completo de hoteles
- Documentos (SSN, ITIN, PDFs)
- Reclutadora que lo dio de alta

### Acciones
- Ver historial de asignaciones
- Consultar Blacklist
- Crear colaborador (apoyo, mismo modal que Reclutadora)
- Editar colaborador (CRUD por ser Manager)

---

## ⚫ Módulo BLACKLIST *(CRUD completo — único rol con permiso de vetar)*

### Lista
- Todos los vetados
- Por motivo (3 inasistencias automático, disputa resuelta, falta grave)
- Por origen (Sistema automático / Manager manual)

### Filtros
- Buscar por nombre / documento
- Por motivo
- Por fecha de ingreso
- Por zona
- Por colaborador que lo propuso

### Detalle
- Info del colaborador
- Motivo del veto
- Fecha de ingreso a Blacklist
- Quién lo propuso
- Investigación del Inspector (si hubo disputa)
- Evidencias adjuntas

### Acciones (exclusivas del Manager)
- ✅ **Aprobar inclusión en Blacklist** (con motivo y evidencia obligatoria)
- ✅ **Resolver disputa** (decisión final tras investigación del Inspector)
- ❌ **Remover de Blacklist** (con justificación obligatoria)
- 📝 Comentar en el caso

> [!important]
> Regla de negocio: **Solo el Manager puede aprobar/remover Blacklist** (regla RR-02).

---

## 👥 Módulo MIS LÍDERES DE GRUPO *(exclusivo del Manager)*

### Lista
- Líder · zona · n° de reclutadoras a cargo · % cobertura del grupo
- Ej.: Carla Méndez · Centro · 4 reclutadoras · 88%
- Ej.: Pedro García · Norte · 3 reclutadoras · 75%

### Filtros
- Por zona
- Por estado (activo / vacaciones / baja)
- Por desempeño (alto / medio / bajo)
- Buscar por nombre

### Detalle (al click en un Líder)
- Datos básicos
- Reclutadoras a cargo (vista anidada)
- Carga del grupo
- Métricas: cobertura, tiempo promedio, casos escalados, distribución de carga
- Reportes recibidos (histórico)
- Comentarios de QA sobre el Líder

### Acciones
- Ver desempeño detallado
- Reasignar Reclutadora entre Líderes (balanceo)
- Comunicar (chat / nota interna)
- Marcar disponibilidad
- Solicitar reporte
- Escalar caso a dirección (si aplica)

---

## 👨‍💼 Módulo GESTIÓN DE EQUIPO *(exclusivo del Manager)*

### Vistas
- **Líderes de Grupo:** lista + detalle + estado
- **Reclutadoras:** lista + detalle + estado + Líder al que pertenecen

### Filtros
- Tipo (Líder / Reclutadora)
- Estado (activo / vacaciones / baja)
- Zona
- Buscar por nombre / correo

### Acciones (exclusivas del Manager)
- ➕ **Dar de alta Líder de Grupo** (modal: nombre, correo, teléfono, zona, grupo)
- ➕ **Dar de alta Reclutadora** (modal: nombre, correo, teléfono, zona, Líder al que pertenece)
- ✏️ **Editar usuario** (cambiar zona, cambiar de grupo, cambiar rol)
- ⏸️ **Marcar como inactivo / vacaciones**
- ❌ **Dar de baja** (eliminación lógica)
- 🔁 **Mover Reclutadora a otro Líder** (reasignación organizacional)

---

## ⚠️ Módulo INCIDENCIAS / DISPUTAS

### Lista
- Casos abiertos (escalados por Líderes o Inspectores)
- Casos resueltos (histórico)
- Filtro por tipo: blacklist / disputa de hotel / problema operativo / accidente laboral

### Filtros
- Estado (abierto / en investigación / resuelto)
- Tipo de caso
- Origen (Líder / Inspector / Reclutadora)
- Hotel involucrado
- Fecha

### Detalle
- Descripción del caso
- Reclutadora / Colaborador involucrado
- Evidencia adjunta
- Investigación del Inspector (si aplica)
- Recomendación
- Historial de comentarios

### Acciones
- Asignar a Inspector (si aplica)
- Comentar en el caso
- ✅ **Resolver caso** (decisión final, con motivo)
- Escalar a Dirección
- Cerrar caso

---

## 📈 Módulo REPORTES *(recibe + genera)*

### Reportes recibidos (de Líderes de Grupo)
- Lista de reportes recientes
- Filtros: por Líder, por tipo, por fecha
- Detalle del reporte con todas las métricas

### Generar reporte global
**Selector de tipo**
- Cobertura global del módulo
- Comparativa entre Líderes de Grupo
- Comparativa entre zonas
- Distribución de carga
- Tiempos de cobertura
- Casos escalados
- Indicador de Calidad histórico

**Rango de fechas**
- Esta semana / Este mes / Trimestre / Personalizado

**Filtros**
- Por zona / Por Líder / Por posición / Por hotel

### Acciones
- 📤 Enviar a Dirección
- 📄 Exportar (CSV / PDF / Excel)
- 💾 Guardar como borrador
- 📋 Programar envío recurrente

### Histórico de reportes generados
- Lista con fecha · tipo · destinatario · estado

---

## 📅 Módulo SCHEDULE *(consulta)*

- Vista del [[Core/Módulos/Schedule|Schedule]] de cualquier hotel.
- Filtros por hotel, semana, zona.
- Solo consulta — no acciones de gestión (lo gestiona el [[Hotel/Manager del Hotel|Manager del Hotel]]).
- Útil para investigar casos o validar carga operativa.

---

## ⚙️ Módulo CONFIGURACIÓN

- Catálogos del módulo (consulta — el CRUD de catálogos pertenece al Administrador del sistema).
- Notificaciones: configurar tipos de alertas que recibe.
- Plantillas de reportes.
- Perfiles de acceso por rol (consulta).

---

## Reglas operativas con el modelo "self-pick"

```
Manager del Hotel autoriza requisición
        │
        ▼
Llega al módulo Reclutamiento (queda en cola "Autorizadas")
        │
        ▼
Reclutadoras y Líderes ven la cola en su Dashboard
        │
        ▼
Toman libremente la requisición que quieran/puedan
        │
        ▼
Cubren con colaboradores del Pool

  ╔══════════════════════════════════════╗
  ║   El Manager NO interviene normalmente   ║
  ║   Solo entra en casos especiales:        ║
  ║   - Requisición sin tomar mucho tiempo   ║
  ║   - Hotel VIP                            ║
  ║   - Balanceo entre grupos                ║
  ║   - Líder ausente                        ║
  ║   - Corrección de error                  ║
  ╚══════════════════════════════════════╝
```

### Diferencias clave vs Líder de Grupo
| Aspecto | Líder de Grupo | Manager de Reclutamiento |
|---|---|---|
| Toma requisiciones | Sí (modelo self-pick) | Sí pero excepcional |
| Pool, Schedule, Blacklist | Acceso (consulta + creación) | Acceso completo + CRUD Blacklist |
| Mi Grupo | Ve sus Reclutadoras | Ve sus Líderes (anidado: Líderes → Reclutadoras) |
| Gestión de equipo | ❌ | ✅ alta/edición de Líderes y Reclutadoras |
| Aprobar/remover Blacklist | ❌ | ✅ exclusivo |
| Resolver disputas | ❌ | ✅ decisión final |
| Reportes | Genera y envía al Manager | Recibe + genera globales |
| Indicador de Calidad | ❌ | ✅ visibilidad |
| Forzar cambios excepcionales | ❌ | ✅ con justificación |

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
║              ROL: MANAGER DE RECLUTAMIENTO                    ║
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
│ 📊 Dashboard │  KPIs globales · Líderes · Críticas           │
│ 📋 Requisic. │  Vista global · Tomar excepcional             │
│ 🧑 Pool      │  Consulta + creación de apoyo                 │
│ ⚫ Blacklist │  CRUD completo · Aprobar · Resolver           │
│ 👥 Mis Líder │  Supervisión de Líderes y sus grupos          │
│ 👨 Gestión   │  Alta/Baja/Edición de Líderes y Reclutadoras  │
│ ⚠️ Incidenc. │  Disputas · Casos · Resolver                  │
│ 📈 Reportes  │  Recibe · Genera · Exporta                    │
│ 📅 Schedule  │  Consulta global                              │
│ ⚙️ Config.   │  Catálogos · Notificaciones                   │
└──────────────┴───────────────────────────────────────────────┘
```

---

## Relacionado

- [[Manager de Reclutamiento]] (definición del rol)
- [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo de Reclutadoras]]
- [[Reclutadora]]
- [[Reclutamiento/Reclutamiento|Reclutamiento]]
- [[Flujo de Reclutamiento]]
- [[Core/Módulos/Requisicion/Requisición|Requisición]]
- [[Core/Módulos/Pool de Colaboradores|Pool de Colaboradores]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Core/Módulos/Schedule|Schedule]]
- [[QA/QA|QA]] (fuente del Indicador de Calidad)
- [[Inspector]] (origen de investigaciones de Blacklist)
- [[Arquitectura Líder de Grupo|Arquitectura del Líder de Grupo]]
