---
tags:
  - arquitectura
  - modulo/hotel
aliases:
  - Arquitectura Supervisor
  - Wireframe Supervisor
  - Arquitectura SUP
---

# Arquitectura — Supervisor

Wireframe de la plataforma Oranje para el rol [[Hotel/Supervisor|Supervisor]]. Define el flujo de entrada, header global, sidebar de módulos y el detalle de cada módulo al que tiene acceso.

> [!info]
> El Supervisor es el **rol operativo base** del lado del hotel. Su tarea principal es **crear requisiciones de personal** y enviarlas al [[Hotel/Manager de Área|Manager de Área]] para que las autorice. También reporta accidentes laborales en la propiedad.

> [!important]
> El Supervisor **NO** puede autorizar requisiciones — esa acción es exclusiva del Manager de Área (capa de seguridad de la plataforma).

## N0 — Inicio

```
PLATAFORMA ORANGE
        │
        ▼
LOGIN / AUTORIZACIÓN
        │
        ▼
ROL IDENTIFICADO / SUPERVISOR
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
- Rol: Supervisor (SUP)

**Mi hotel / departamento**
- Nombre del hotel
- Departamento al que reporta *(en jerarquía extendida — ej. Housekeeping)*
- Manager de Área / Gerente de Departamento al que reporta

**Mis métricas (mes en curso)**
- Requisiciones creadas
- Requisiciones autorizadas
- Requisiciones rechazadas
- Accidentes laborales reportados

**Configuración**
- Cambiar contraseña
- Preferencias de notificación

🚪 Cerrar sesión

### 🔍 BUSCADOR (global)

**Qué se puede buscar**
- Mis requisiciones (por ID o número)
- Colaboradores asignados al hotel/depto
- Posiciones del Schedule

**Cómo funciona**
- Resultados en vivo agrupados por tipo
- Atajo: `/` o `Ctrl+K`

### 🔔 NOTIFICACIONES (campanita con badge)

**Por tipo de evento**
- ✅ Mi requisición fue autorizada por el Manager de Área
- ❌ Mi requisición fue rechazada con observaciones (necesita correcciones)
- 👤 Reclutamiento asignó un colaborador a una de mis requisiciones
- 🟢 Una de mis requisiciones quedó cubierta al 100%
- 🚨 Accidente laboral reportado por un colaborador (Escenario A — debo acudir)
- ⏱️ Cambio en el Schedule del depto

**Estados**
- 🟠 Sin leer (cuenta en el badge)
- 🟢 Leída

---

## N1 — SIDEBAR (Módulos del Supervisor)

```
SIDEBAR
   ├─ DASHBOARD
   ├─ REQUISICIONES        (crear + ver mis creadas)
   ├─ SCHEDULE             (consulta del depto)
   ├─ TIMESHEET            (consulta del depto)
   ├─ MI PERSONAL          (colaboradores asignados — Stand-by limitado)
   └─ ACCIDENTES           (reportar y dar seguimiento)
```

> [!note]
> El Supervisor **NO** tiene acceso a generación de QR. Su Schedule y Timesheet son **solo consulta** (no edita asignaciones).

---

## 📊 Módulo DASHBOARD

### KPIs personales
- Requisiciones que creé este mes
- Mis requisiciones pendientes de autorización (esperando al Manager de Área)
- Mis requisiciones autorizadas en proceso
- Mis requisiciones rechazadas (necesitan corrección)
- Accidentes laborales activos en el depto

### Vistas resumen
- **Mis requisiciones recientes:** lista corta por estado.
- **Posiciones críticas del Schedule:** posiciones vacantes o con cobertura parcial (para identificar dónde crear nueva requisición).
- **Alertas de accidentes:** casos abiertos donde debo acudir.

### Acciones rápidas
- ➕ Nueva requisición
- 🚨 Reportar accidente
- 👁️ Ver Schedule del día
- 👁️ Ver mis requisiciones rechazadas

---

## 📋 Módulo REQUISICIONES

### Sub-vistas

- ✏️ **Borradores** — requisiciones que estoy editando (sin enviar a autorización aún).
- 🟢 **Pendientes de autorización** *(Verde manzana — En elaboración)* — enviadas al Manager de Área, esperando su decisión.
- ❌ **Rechazadas** — devueltas con observaciones del Manager de Área; debo corregir y reenviar.
- 🟠 **Autorizadas** — ya en manos de Reclutamiento (solo lectura para mí).
- 🟡 **En proceso** — Reclutamiento asignando colaboradores.
- 🔵 **Cubiertas** — al 100%.
- 📂 **Toda** — histórico completo de mis requisiciones.

### Filtros
- Estado
- Posición
- Fecha de creación
- Buscar por ID

### Detalle de requisición
- **Cabecera:**
    - ID.
    - Número (auto-generado: `AAAAMMDDHHMMxx`).
    - Fecha.
    - Estado.
- **Posiciones:**
    - Cantidad.
    - Posición.
    - Modalidad.
    - Nivel de inglés.
    - Horario.
    - Fecha de inicio.
- **Notas adicionales.**
- **Observaciones del Manager de Área** *(visible solo si fue rechazada)*.

### Acciones
- ➕ **Crear nueva requisición** *(formulario completo — ver módulo abajo)*.
- ✏️ **Editar borrador** o **requisición rechazada**.
- 📤 **Enviar al Manager de Área para autorización** *(cambia estado a Verde manzana — En elaboración)*.
- 🗑️ **Eliminar borrador** o **requisición sin posiciones** *(eliminación física automática si no tiene posiciones)*.
- 👁️ **Ver journal** de la requisición.

> [!warning]
> El Supervisor **NO puede autorizar** ni enviar directamente a Reclutamiento. Si lo intenta, el sistema bloquea con: **"Solo el gerente del hotel puede autorizar la requisición"**.

### ➕ Formulario "Nueva Requisición"

**Campos obligatorios:**
- [[Posiciones]] requeridas (autocomplete del catálogo)
- Cantidad de personas por posición
- Fecha de inicio
- Horario (entrada / salida)
- [[Modalidades de Contratación|Modalidad de contratación]] (Tiempo completo / Medio tiempo / Temporal / Según solicitud)
- Preferencia de [[Niveles de Inglés|nivel de inglés]] (Básico / Intermedio / Avanzado / Conversacional)

**Campos opcionales:**
- Notas adicionales (contexto operativo, requisitos especiales)
- Adjuntos (PDF / imagen)

**Validaciones:**
- Al menos 1 posición registrada (sin esto el Manager de Área NO podrá autorizar — sale el mensaje "No tiene posiciones registradas").
- Fecha de inicio en el futuro.
- Cantidad > 0.

---

## 📅 Módulo SCHEDULE (consulta)

### Vista principal
- **Calendario semanal** del hotel/depto (igual al del Manager de Área).
- Filas: posiciones; columnas: días; celdas: colaborador asignado o "Vacante".

### Filtros
- Posición
- Estado de cobertura
- Semana (selector)

### Acciones (limitadas — consulta)
- 👁️ Ver detalle de asignación.
- 📥 Exportar Schedule de la semana (PDF/CSV).
- 🔔 **Sugerir refuerzo al Manager de Área** (genera prefill de nueva requisición si una posición está vacante por mucho tiempo).

> [!note]
> El Supervisor **NO edita** el Schedule. Si detecta que falta cobertura, crea una nueva requisición o avisa al Manager de Área.

---

## ⏱️ Módulo TIMESHEET (consulta)

### Vista principal
- **Tabla semanal** de colaboradores × días con sus 6 ponches y horas netas.
- Indicador de Cumplimiento del Timesheet por colaborador (Verde / Amarillo / Rojo).

### Filtros
- Colaborador
- Posición
- Día / semana

### Acciones (limitadas — consulta)
- 👁️ Ver detalle de jornada.
- 📤 Exportar Timesheet semanal.

> [!warning]
> El Supervisor **NO genera QR** (eso es exclusivo del Manager de Área). **NO corrige ponches** (eso también es exclusivo del Manager de Área). **NO ve el Indicador de Lunch Extendido** (exclusivo de roles de Oranje).

---

## 👥 Módulo MI PERSONAL

### Lista
- Colaboradores asignados al hotel/depto, con [[Semáforo del Colaborador]] visible.

### Filtros
- Posición · Estado del semáforo · Buscar por nombre

### Detalle
- Datos del colaborador (nombre, foto, teléfono, posición, modalidad).
- Schedule del colaborador (días asignados).
- Timesheet semanal (resumen).

### Acciones
- 🩷 **Poner en Stand-by (Rosa)** *(compartido con Manager de Área y Manager General)* — colaborador queda sin Schedule ni Timesheet.
- 🔴 **Reportar colaborador (Rojo)** *(NUEVO — compartido con Manager de Área y Manager General)* — inicia investigación del Inspector con motivo y evidencia.
- 👁️ **Ver historial** de incidencias / asignaciones.
- 📞 **Contactar al colaborador**.

> [!info]
> Los 3 roles del Hotel pueden reportar colaborador (Rojo) y poner Stand-by (Rosa). El reporte de colaborador dispara investigación del Inspector de zona automáticamente.

---

## 🚨 Módulo ACCIDENTES LABORALES

> [!important]
> El Supervisor tiene un **rol activo** en el reporte y captura de accidentes laborales. Acude físicamente al lugar del incidente.

### Sub-vistas
- 🟢 **Activos** — accidentes en proceso de investigación por el Inspector.
- ✅ **Cerrados** — casos resueltos (último mes).
- 📂 **Histórico** — todos los accidentes del depto.

### Detalle de accidente
- Datos del colaborador afectado.
- Fecha, hora, ubicación exacta.
- Circunstancias.
- Testigos.
- Atención inmediata brindada.
- Estado del colaborador (paso a Gris en [[Semáforo del Colaborador]] = protección contra regla de 3 inasistencias).
- Inspector asignado.

### Acciones

#### Escenario A — Colaborador reporta desde la app
1. **Recibo notificación simultánea** con el Inspector de zona.
2. **Acudo físicamente** al lugar del incidente.
3. **Capturo información presencial**:
   - Ubicación exacta
   - Circunstancias
   - Testigos
   - Atención inmediata brindada

#### Escenario B — Yo detecto primero
1. **Detecto el accidente** en la propiedad.
2. **Creo la tarjeta de accidente** desde la app:
   - 📝 **Crear tarjeta** con todos los datos.
   - 📷 Adjuntar fotos / evidencia.
   - 👤 Identificar colaborador afectado.
3. **La señal llega al Inspector** de zona automáticamente.

> [!info]
> En ambos escenarios, el colaborador pasa a estado **Gris** (Accidentado) en el Semáforo del Colaborador, lo que lo protege de la regla de 3 inasistencias mientras se investiga.

### Filtros
- Estado del caso
- Colaborador afectado
- Inspector asignado
- Rango de fechas

---

## Flujo operativo del Supervisor

```
1. Login → Dashboard
   │
   ▼
2. Detecto necesidad de personal en mi depto
   │
   ▼
3. Creo Nueva Requisición:
      • Posiciones, cantidad, modalidad, inglés, horario
      • Notas adicionales si aplica
   │
   ▼
4. Envío al Manager de Área para autorización
   │
   ├─→ Autoriza → pasa a Reclutamiento (Self-Pick)
   └─→ Rechaza → corrijo según observaciones y reenvío
   │
   ▼
5. Reclutamiento asigna colaboradores → aparecen en Schedule
   │
   ▼
6. Operación diaria:
      • Consulto Schedule y Timesheet
      • Pongo Stand-by (Rosa) si el hotel decide
      • Reporto accidentes laborales (Escenario A o B)
   │
   ▼
7. Si una posición se queda vacante o termina:
      • Genero nueva requisición
      • Sugiero refuerzo al Manager de Área
```

---

## Diferencias clave vs Manager de Área y Manager General

| Aspecto | Supervisor | Manager de Área | Manager General |
|---|---|---|---|
| Crear requisición | ✅ acción principal | ❌ | ❌ |
| Autorizar requisición | ❌ | ✅ exclusivo | ❌ |
| Generar QR | ❌ | ✅ | ❌ |
| Editar Schedule | ❌ (solo consulta) | ✅ | Solo consulta global |
| Corregir Timesheet | ❌ | ✅ | ❌ |
| Stand-by (Rosa) | ✅ | ✅ | ❌ |
| Reportar (Rojo) | ❌ | ✅ exclusivo | ❌ |
| Reportar accidente laboral | ✅ acción principal | ❌ | ❌ |
| Visibilidad global del hotel | Solo su depto | Solo su depto | ✅ todos los deptos |

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
║                    ROL: SUPERVISOR (SUP)                      ║
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
│ 📊 Dashboard │  Mis KPIs · Acciones rápidas                  │
│ 📋 Requisic. │  Crear · Mis requisiciones · Rechazadas       │
│ 📅 Schedule  │  Calendario (consulta) · Sugerir refuerzo     │
│ ⏱️ Timesheet │  Ponches del depto (consulta)                 │
│ 👥 Personal  │  Mis colaboradores · Stand-by                 │
│ 🚨 Accidents │  Reportar · Casos activos · Histórico         │
└──────────────┴───────────────────────────────────────────────┘
```

---

## Relacionado

- [[Hotel/Supervisor|Supervisor]] (definición del rol)
- [[Hotel/Manager de Área|Manager de Área]]
- [[Hotel/Manager General|Manager General]]
- [[Hotel/Hotel|Hotel]]
- [[Hotel/Reglas del Hotel|Reglas del Hotel]]
- [[Core/Módulos/Requisicion/Requisición|Requisición]]
- [[Core/Módulos/Requisicion/Flujo de Requisición|Flujo de Requisición]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Timesheet]]
- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]]
- [[Core/Módulos/Accidente Laboral/Flujo de Accidente Laboral|Flujo de Accidente Laboral]]
- [[Semáforo de Requisición]]
- [[Semáforo del Colaborador]]
- [[Departamentos del Hotel]]
- [[Inspector]]
