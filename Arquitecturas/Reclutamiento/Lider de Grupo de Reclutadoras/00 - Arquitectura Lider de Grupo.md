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

> [!important]
> **Modelo Self-Pick colaborativo (RR-15):** las requisiciones llegan al sistema y el Líder (como cualquier Reclutadora) las **toma libremente** desde la bandeja de Autorizadas. Tomar una requisición **NO bloquea a las demás**: una misma requisición puede tener **varios reclutadores participantes** trabajándola a la vez. Tomar una ya tomada significa **unirse** como reclutador participante adicional; nadie pierde la requisición. El avance de cobertura es **compartido** entre todos los reclutadores participantes.

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
   ├─ RECLUTAMIENTO   (Pool + Entrevistas — propias + del grupo)
   ├─ REQUISICIÓN     (Cola de Autorizadas + Mis Requisiciones tomadas/participadas — Self-Pick colaborativo)
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

### 📝 Entrevistas (sub-vista — doble modo: operativo + supervisión)

> [!info]
> El Líder usa esta sub-vista de **dos formas**:
> 1. **Modo operativo (minoría):** cuando él mismo recluta como apoyo, ve sus propios candidatos en proceso (igual que la Reclutadora).
> 2. **Modo supervisión (mayoría):** ve el **historial completo de reclutamientos del grupo** con detalle de **quién** (qué Reclutadora) hizo cada uno. Es la herramienta principal para auditar y dar seguimiento.

**Toggle superior**
- 👤 **Mis Entrevistas** — solo las que el Líder hizo personalmente.
- 👥 **Historial del Grupo** — TODAS las entrevistas hechas por el Líder + sus Reclutadoras.

**Pestañas internas (estado del candidato — comunes a ambos modos)**
- 🟠 **Pendientes de App** — Fase 1 hecha, esperando que el colaborador complete Fase 2.
- 🟡 **Pendientes de Validar** — el colaborador completó Fase 2 + Fase 3, esperando validación.
- ⚪ **Borradores** — entrevistas iniciadas pero no guardadas.
- ⚫ **Abandonados** — candidatos con >X días sin completar la app.
- ✅ **Validados** — histórico de los que ya pasaron al Pool (rango configurable).

**Filtros (transversales)**
- **Reclutadora del grupo** *(solo en modo Historial del Grupo)* — quién hizo la entrevista.
- Posición ([[Core/Catálogos/Posiciones|Posiciones]])
- Zona ([[Core/Catálogos/Zonas|Zonas]])
- Modalidad prevista
- Días en estado (slider)
- Fecha de entrevista (rango)
- Origen (referido / aplicación directa / reclutamiento activo)
- Buscar por nombre / documento / teléfono

**Detalle del candidato (al click)**
- **Cabecera:** foto + nombre + teléfono + posición prevista + timeline visual `Fase 1 ✅ → Fase 2 🟡 → Fase 3 ⚪ → Validación`.
- **Reclutadora responsable** (quién hizo la entrevista — Reclutadora del grupo o el propio Líder). 👈 *visible en modo Historial del Grupo*.
- **Días desde entrevista** con indicador de color (🟢 <3 · 🟡 3-7 · 🔴 >7).
- **Tabs internos:**
  1. **Datos Fase 1** — capturados en la entrevista (editable solo por quien la hizo o por el Líder).
  2. **Datos Fase 2** — completados por el colaborador en la app. Solo lectura.
  3. **Datos Fase 3** — datos de emergencia. Solo lectura.
  4. **Histórico de comunicación** — cuándo se envió el link, recordatorios, abrió la app.
  5. **Documentos** — cédula, fotos, comprobantes.

**Acciones**

*Comunes a ambos modos:*
- 👁️ **Ver detalle** del candidato.
- 📞 **Llamar / Contactar** al candidato.
- 📩 **Reenviar link de App** (si está en Pendientes de App).
- 🔔 **Enviar recordatorio** (Pendientes de App con >3 días).

*Modo "Mis Entrevistas" (operativas — Líder reclutando):*
- ✏️ **Editar datos Fase 1** propios.
- ✅ **Validar alta** de candidatos propios (RF-08).
- ❌ **Rechazar alta** propia con motivo.
- 🚫 **Marcar como abandonado** propio.

*Modo "Historial del Grupo" (supervisión):*
- 📊 **Ver desempeño** de la Reclutadora que hizo la entrevista (lleva a métricas individuales — RF-23).
- 💬 **Comentar al expediente** (queda visible para la Reclutadora responsable).
- 🚨 **Solicitar acción a la Reclutadora** (ej. "reenvía el link, lleva 5 días sin completar").
- 📤 **Reasignar candidato a otra Reclutadora** del grupo (caso de Reclutadora ausente o sobrecargada).
- ✅ **Validar alta en nombre del grupo** (excepcional — si la Reclutadora original no está disponible).

> [!important]
> El Líder puede **ver y supervisar** TODAS las entrevistas del grupo, pero la edición/validación rutinaria la hace la Reclutadora que originó la entrevista. La intervención del Líder es para casos de seguimiento, retraso o ausencia.

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
- Listado de todas las requisiciones que el [[Hotel/Manager de Área|Manager de Área]] aprobó.
- Cualquier Reclutadora o Líder puede **tomar** la que quiera (Self-Pick colaborativo, RR-15). Tomar **NO bloquea a las demás**.
- Una requisición ya tomada sigue visible aquí con la etiqueta **"Compartida · N reclutadores"**: tomarla significa **Unirme** como reclutador participante adicional.
- Ordenadas por urgencia (Red primero) y antigüedad en cola.

**🟡 Mis Requisiciones (las que tomé o en las que participo)**
- Las requisiciones que el Líder **tomó** O en las que **participa** junto a otros reclutadores (modelo colaborativo — no hay dueño único).
- Las compartidas muestran la etiqueta **"Compartida · N reclutadores"**.
- Por sub-estado:
  - 🟡 En proceso (uno o varios reclutadores asignando colaboradores)
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
- **Reclutadores activos en esta requisición** (RF-40) — lista de todos los reclutadores participantes que la están trabajando ahora mismo (rol + nombre), con etiqueta "Compartida · N reclutadores". El avance de cobertura es compartido entre todos.
- Posiciones solicitadas (con [[Semáforo de Posiciones de la Requisición]])
- Schedule del hotel (contexto)
- Colaboradores ya asignados (los asignados por **cualquier** reclutador participante, con quién lo asignó)

### Historial de la requisición (RF-41)
- Timeline cronológico **inmutable** con el **actor** de cada evento (rol + nombre) y timestamp.
- Registra: quién la tomó / se unió, quién salió, quién asignó/desasignó qué colaborador a qué posición, quién la cerró.
- Visible para todos los reclutadores participantes, el Líder de Grupo y el [[Manager de Reclutamiento]].

### Acciones (Self-Pick colaborativo)
- **🎯 Tomar requisición** *(desde bandeja de Autorizadas — pasa a Mis Requisiciones)*. Si ya hay otros reclutadores, la acción es **Unirme** como reclutador participante adicional.
- **👥 Ver reclutadores activos** (RF-40) — quién está trabajando la requisición ahora mismo.
- **🕓 Ver historial** (RF-41) — timeline cronológico con actor de cada evento.
- **👤 Asignar colaborador** (abre Pool filtrado por posición/zona/inglés)
- **🔄 Asignación temporal** (transición Verde fuerte/Amarillo → Café)
- Marcar como cubierta (cuando todas las posiciones están al 100%)
- Marcar como parcial (cierre con faltantes)
- Reportar problema (escala al Manager)
- **🚪 Salir de la requisición** — te retira solo a ti; la requisición sigue **En proceso** si quedan otros reclutadores y NO resetea lo ya asignado. Solo vuelve a **Autorizada** cuando sale el **último** reclutador.

> [!important]
> El Líder de Grupo opera con el mismo modelo Self-Pick colaborativo (RR-15) que la Reclutadora: **toma libremente** las requisiciones que pueda cubrir y puede **unirse** a las que ya trabajan otros reclutadores. La diferencia con la Reclutadora es que **además supervisa al grupo** (módulo "Mi Grupo") y **envía reportes formales al Manager** (módulo "Reportes").

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
- Reasignar requisición a otra reclutadora (RF-37)
- Marcar disponibilidad (vacaciones / vuelta) (RF-38)
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

### Acciones
- ➕ **Agregar a Blacklist** (con motivo y evidencia obligatorios) — disponible para **cualquier rol del depto de Reclutamiento** (regla RR-03).
- 👁️ **Consultar** antes de cada asignación (obligatorio).

> [!warning]
> El Líder **SÍ puede agregar** a Blacklist (con motivo y evidencia), igual que la Reclutadora y el Manager.
> Lo que **NO** puede es **remover ni resolver disputas** — esa acción es exclusiva del [[Manager de Reclutamiento]].
> La consulta es **obligatoria** antes de cada reclutamiento (regla del [[Flujo de Reclutamiento]]).

---

## Reglas operativas (decisión final del usuario)

### Flujo normal de requisiciones (95%)
```
Manager de Área autoriza requisición
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
| Agregar a Blacklist | ✅ | ✅ (con motivo y evidencia) |
| Remover / resolver disputa de Blacklist | ❌ | ❌ (exclusivo del Manager) |

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
│ 🧑 Reclutam. │  Pool · Entrevistas (propias + grupo) · Nuevo │
│ 📋 Requisic. │  Distribuir · Tomar · Asignar                 │
│ 👥 Mi Grupo  │  Reclutadoras · Métricas · Reasignar          │
│ 📈 Reportes  │  Generar · Enviar Manager · Histórico         │
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
