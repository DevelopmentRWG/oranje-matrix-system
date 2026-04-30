---
tags:
  - arquitectura
  - modulo/reclutamiento
aliases:
  - Arquitectura Líder de Grupo
  - Wireframe Líder de Grupo de Reclutadoras
---

# Arquitectura — Líder de Grupo de Reclutadoras

Wireframe de la plataforma Oranje para el rol [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo de Reclutadoras]]. Define el flujo de entrada, header global, sidebar de módulos y el detalle de cada módulo al que tiene acceso.

> [!info]
> El Líder de Grupo **ejecuta todas las funciones operativas de una [[Reclutadora]]** y además supervisa al grupo y reporta al [[Manager de Reclutamiento]]. Su arquitectura es la de Reclutadora + módulos de supervisión y reporte.

## N0 — Inicio

```
PLATAFORMA ORANGE
        │
        ▼
LOGIN / AUTORIZACIÓN
        │
        ▼
ROL IDENTIFICADO / LÍDER DE GRUPO DE RECLUTADORAS
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
- Rol: Líder de Grupo de Reclutadoras

**Mi grupo**
- Nombre del grupo
- Reclutadoras a cargo (cantidad)

**Mi zona asignada**
- Ej. "Zona Centro"

**Mis métricas (mes en curso)**
- Cobertura del grupo
- Requisiciones distribuidas
- Casos escalados al Manager
- Tiempo promedio de cobertura

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
- Reclutadoras del grupo

**Cómo funciona**
- Al escribir, muestra resultados en vivo agrupados por tipo
- Cada resultado lleva directo al detalle correspondiente
- Atajo de teclado: `/` o `Ctrl+K`

**Filtros rápidos**
- Tipo (req · colaborador · hotel · blacklist · reclutadora)
- Búsqueda reciente (últimos 5)

### 🔔 NOTIFICACIONES (campanita con badge)

**Por tipo de evento**
- 📋 Nueva requisición autorizada por el hotel
- 👤 Candidato completó alta en App → listo para validar
- 🔴 Requisición en urgencia Red (<72h)
- ⚫ Blacklist actualizado (nuevo colaborador vetado)
- 🛡️ Caso escalado por QA
- 🟢 Reclutadora del grupo cubrió requisición al 100%
- ⚠️ Reclutadora del grupo reportó problema
- 📊 Solicitud de reporte por parte del Manager

**Estados**
- 🟠 Sin leer (resaltada, cuenta en el badge)
- 🟢 Leída

**Acciones**
- Click → te lleva al módulo relacionado
- Marcar como leída
- Marcar todas como leídas

---

## N1 — SIDEBAR (Módulos del Líder)

```
SIDEBAR
   ├─ DASHBOARD
   ├─ RECLUTAMIENTO   (Pool + Crear/Entrevista + Validación + Asignación)
   ├─ REQUISICIÓN     (Cola de Autorizadas + Mis Tomadas — Self-Pick)
   ├─ BLACKLIST       (consulta + agregar)
   ├─ MI GRUPO        ← exclusivo del Líder (supervisión)
   └─ REPORTES        ← módulo formal con su propia pantalla
```

---

## 📊 Módulo DASHBOARD

### KPIs personales (como Reclutadora)
- Requisiciones abiertas propias
- Requisiciones urgentes
- Candidatos pendientes de validar
- Alertas críticas

### KPIs del grupo (extra del Líder)
- Cobertura agregada del grupo (mes)
- Requisiciones cubiertas vs. pendientes del grupo
- Tasa de cobertura por reclutadora
- Casos escalados pendientes
- Reclutadoras activas

### Vistas resumen
- **Pool:** colaboradores disponibles por posición
- **Mis Requisiciones (resumen):**
  - Req #001 · Housekeeper · 🔴 Red
  - Req #002 · Chef · 🟡 Yellowh
  - Req #003 · Hoseman · 🟢 Green
  - [Ver todas →] navega a Mis Requisiciones

### Bandeja Acción
- Últimas actualizaciones de Blacklist
- Candidatos que completaron App → Validar
- Reportes del grupo
- Solicitudes de aprobación pendientes

### Acciones rápidas
- Nuevo Candidato
- Buscar en Pool
- Consultar Blacklist
- Tomar requisición de la bandeja
- Generar reporte

---

## 🧑‍🤝‍🧑 Módulo RECLUTAMIENTO

### Pool de Colaboradores

**Lista** (estados del [[Semáforo del Colaborador]])
- ⚪ Blanco — Pre-asignación
- 🟢 Verde manzana — Día 1-2 onboarding
- 🔵 Azul claro — Día 3+ entrega uniforme
- 🟠 Naranja — Fijo
- 🟢 Verde fuerte — Disponible
- 🟡 Amarillo — Disponible voluntario
- 🟤 Café — Asignación temporal
- 🩷 Rosa — Stand-by
- 🟣 Morado — No regresó
- 🔴 Rojo — Reportado
- ⚫ Negro — Blacklist
- ⬜ Gris — Accidentado

**Filtros**
- Posición ([[Core/Catálogos/Posiciones|Posiciones]]: Housekeeper, Hoseman, Chef, Laundry)
- Zona ([[Core/Catálogos/Zonas|Zonas]]: Centro, Sur, Este, Oeste, Noroeste, Sureste)
- Modalidad ([[Core/Catálogos/Modalidades de Contratación|Modalidades]]: Tiempo completo, Medio tiempo, Temporal, Según solicitud)
- Nivel de inglés ([[Core/Catálogos/Niveles de Inglés|Inglés]]: Básico, Intermedio, Avanzado, Conversacional)
- Buscar por nombre / documento / teléfono

**Detalle**
- Datos personales: nombre, documento, teléfono, domicilio
- Datos laborales: posición, modalidad, inglés, experiencia
- Semáforo actual del colaborador
- Historial: hoteles donde ha trabajado
- Documentos: SSN, ITIN, PDFs subidos

**Acciones**
- Asignar a requisición (Verde fuerte / Amarillo → Café)
- Editar colaborador (Pendiente)
- Ver historial de asignaciones
- Consultar si está en Blacklist

### + Nuevo Colaborador (modal form)
- Nombre completo
- Documento
- Edad
- Género
- Teléfono
- Correo
- Domicilio
- Cédula (subir)

---

## 📋 Módulo REQUISICIONES (modelo Self-Pick)

### Sub-vistas

**🟢 Bandeja de Autorizadas (disponibles para tomar)**
- Listado de todas las requisiciones que el [[Hotel/Manager del Hotel|Manager del Hotel]] aprobó y aún nadie ha tomado.
- Cualquier Reclutadora o Líder puede tomar la que quiera (modelo Self-Pick).
- Ordenadas por urgencia (Red primero) y antigüedad en cola.

**🟡 Mis Requisiciones (tomadas y en proceso)**
- Solo las que el Líder tomó y está trabajando.
- Por sub-estado:
  - 🟡 En proceso (asignando colaboradores)
  - 🔵 Cubiertas (100%)
  - 🔴 Parciales (cerradas con faltantes)
  - 📂 Toda

### Filtro
- Urgencia (🔴 🟡 🟢) — del [[Semáforo de Urgencia de Requisición]]
- Posición
- Hotel
- Zona
- Estado
- Buscar por ID

### Detalle
- Cabecera (hotel, fechas, urgencia)
- Posiciones solicitadas (con [[Semáforo de Posiciones de la Requisición]])
- Schedule del hotel (contexto)
- Colaboradores ya asignados

### Acciones (Self-Pick)
- **🎯 Tomar requisición** *(desde bandeja de Autorizadas — pasa a Mis Requisiciones)*
- **👤 Asignar colaborador** (abre Pool filtrado por posición/zona/inglés)
- **🔄 Asignación temporal** (transición Verde fuerte/Amarillo → Café)
- Marcar como cubierta (cuando todas las posiciones están al 100%)
- Marcar como parcial (cierre con faltantes)
- Reportar problema (escala al Manager)
- Liberar requisición (devuelve a bandeja de Autorizadas)

> [!important]
> El Líder de Grupo opera con el mismo modelo Self-Pick que la Reclutadora: **toma libremente** las requisiciones que pueda cubrir. La diferencia con la Reclutadora es que **además supervisa al grupo** (módulo "Mi Grupo") y **envía reportes formales al Manager** (módulo "Reportes").

---

## 👥 Módulo MI GRUPO DE RECLUTADORAS *(exclusivo del Líder)*

### Lista
- Reclutadora · zona · n° de requisiciones activas · % cobertura
- Ej.: Ana López · Centro · 3 activas · 85%
- Ej.: Beatriz Cruz · Norte · 2 activas · 92%
- Ej.: Carlos Mena · Centro · 1 activa · 70%

### Filtros
- Por zona
- Por estado (activa / vacaciones / baja)
- Por carga (alta / media / baja)
- Buscar por nombre

### Detalle (al click en una Reclutadora)
- Datos básicos (nombre, contacto, foto)
- Zona asignada
- Carga actual (n° de requisiciones en proceso)
- Métricas individuales (cobertura, tiempo promedio, casos escalados)
- Historial de requisiciones cubiertas
- Solicitudes de aprobación pendientes

### Acciones
- Ver carga detallada
- Reasignar requisición a otra reclutadora
- Comunicar (chat / nota interna)
- Marcar disponibilidad (vacaciones / vuelta)
- Generar reporte individual (vincula al módulo Reportes)

---

## 📈 Módulo REPORTES *(módulo formal — pantalla propia)*

### Generar reporte
**Selector de tipo**
- Cobertura del grupo
- Desempeño individual de Reclutadoras
- Casos escalados
- Tiempo promedio de cobertura
- Distribución de requisiciones

**Rango de fechas**
- Hoy / Esta semana / Este mes / Personalizado

**Filtros**
- Por zona
- Por posición
- Por hotel
- Por reclutadora

### Vista previa
- Métricas numéricas
- Gráficos (barras, líneas, donas)
- Tabla detallada

### Acciones
- 📤 Enviar al [[Manager de Reclutamiento]]
- 📄 Exportar (CSV / PDF)
- 💾 Guardar como borrador
- 📋 Programar envío recurrente (semanal / mensual)

### Histórico de reportes enviados
- Lista de reportes anteriores
- Fecha · Tipo · Destinatario · Estado (enviado / leído)
- Reabrir / Reutilizar como plantilla

---

> [!info]
> **Schedule del Hotel** no es un módulo del Líder — es una vista contextual del módulo Hotel que se consulta durante el proceso de asignar (dentro del módulo Reclutamiento). Útil como contexto previo a tomar o trabajar una requisición.

---

## ⚫ Módulo BLACKLIST

### Lista
- Todos los vetados
- Por motivo (3 faltas, disputa, falta grave)

### Filtros
- Buscar por nombre / documento
- Por motivo
- Por fecha de ingreso a blacklist
- Por zona

### Detalle
- Info del colaborador
- Motivo del veto
- Fecha de ingreso
- Quién lo propuso

> [!warning]
> El Líder **NO** puede agregar/remover de Blacklist — esa acción es exclusiva del [[Manager de Reclutamiento]].
> La consulta es **obligatoria** antes de cada reclutamiento (regla del [[Flujo de Reclutamiento]]).

---

## Reglas operativas (decisión final del usuario)

### Flujo normal de requisiciones (95%)
```
Manager del Hotel autoriza requisición
        │
        ▼
Llega al módulo Reclutamiento
        │
        ▼
Líder de Grupo la recibe
        │
        ├── 🎯 Distribuir a una Reclutadora del grupo  (mayoría)
        └── 👤 Tomar para mí                            (casos especiales)
        │
        ▼
Reclutadora (o Líder) cubre con colaboradores del Pool
```

### Flujo de excepción (5%) — interviene el Manager
- Líder no disponible (vacaciones, baja, fuera de horario).
- Requisición VIP / hotel clave.
- Balanceo entre grupos cuando uno está saturado.
- Escalamiento por urgencia Red sin avance.
- Auditoría / corrección de asignaciones erróneas.

### Diferencias clave vs el Reclutador
| Aspecto | Reclutador | Líder de Grupo |
|---|---|---|
| Reclutamiento, Requisición, Blacklist | Acceso completo | Acceso completo (mismas funciones) |
| KPIs Dashboard | Personales | Personales **+ del grupo** |
| Distribuir requisiciones | ❌ | ✅ acción principal |
| Tomar requisición para sí | ✅ (única opción) | ✅ (caso especial) |
| Mi Grupo de Reclutadoras | ❌ | ✅ módulo exclusivo |
| Reportes formales | ❌ | ✅ módulo exclusivo |
| Aprobación de blacklist | ❌ | ❌ (exclusivo del Manager) |

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
║              ROL: LÍDER DE GRUPO DE RECLUTADORAS              ║
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
│ 📊 Dashboard │  KPIs personales + del grupo                  │
│ 🧑 Reclutam. │  Pool · Nuevo Colaborador                     │
│ 📋 Requisic. │  Distribuir · Tomar · Asignar                 │
│ 👥 Mi Grupo  │  Reclutadoras · Métricas · Reasignar          │
│ 📈 Reportes  │  Generar · Enviar Manager · Histórico         │
│ 📅 Schedule  │  Consulta del Schedule del hotel              │
│ ⚫ Blacklist │  Consulta · Motivos · Histórico               │
└──────────────┴───────────────────────────────────────────────┘
```

---

## Relacionado

- [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo de Reclutadoras]] (definición del rol)
- [[Reclutadora]]
- [[Manager de Reclutamiento]]
- [[Reclutamiento/Reclutamiento|Reclutamiento]]
- [[Flujo de Reclutamiento]]
- [[Core/Módulos/Requisicion/Requisición|Requisición]]
- [[Core/Módulos/Pool de Colaboradores|Pool de Colaboradores]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Semáforo del Colaborador]]
- [[Semáforo de Requisición]]
