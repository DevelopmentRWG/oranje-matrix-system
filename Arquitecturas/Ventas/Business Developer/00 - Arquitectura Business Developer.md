---
tags:
  - arquitectura
  - modulo/ventas
aliases:
  - Arquitectura Business Developer
  - Wireframe Business Developer
  - Arquitectura BD
---

# Arquitectura — Business Developer (BD)

Wireframe de la plataforma Oranje para el rol [[Ventas/Roles/Business Developer|Business Developer]]. Define el flujo de entrada, header global, sidebar de módulos y el detalle de cada módulo al que tiene acceso.

> [!info]
> El Business Developer es el **rol operativo base** del depto Ventas. Ejecuta el ciclo comercial: identifica prospectos, hace visitas en frío, elabora propuestas, da seguimiento y gestiona rechazos. Su BDC valida los términos y aprueba la conversión final.

> [!important]
> El BD **NUNCA** aprueba la conversión a cliente — esa acción es **exclusiva del BDC** (regla RR-V-01). El BD prepara, propone y negocia, pero el "sí final" lo da el BDC.

## N0 — Inicio

```
PLATAFORMA ORANGE
        │
        ▼
LOGIN / AUTORIZACIÓN
        │
        ▼
ROL IDENTIFICADO / BUSINESS DEVELOPER (BD)
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
- Rol: Business Developer (BD)

**Mi BDC asignado**
- Nombre del BDC al que reporta
- Zona / rutas a cargo

**Mi territorio**
- Rutas asignadas
- Zonas operativas
- Cantidad de prospectos activos

**Mis métricas (mes en curso)**
- Prospectos identificados
- Propuestas enviadas
- Conversiones (clientes activos)
- Tasa de conversión personal
- Rechazos gestionados

**Configuración**
- Cambiar contraseña
- Preferencias de notificación

🚪 Cerrar sesión

### 🔍 BUSCADOR (global)

**Qué se puede buscar**
- Hoteles prospecto por nombre / ciudad / zona
- Hoteles cliente activos
- Propuestas enviadas
- Documentos T&C

**Cómo funciona**
- Resultados en vivo agrupados por tipo
- Atajo: `/` o `Ctrl+K`

### 🔔 NOTIFICACIONES (campanita con badge)

**Por tipo de evento**
- 📩 Hotel respondió a la propuesta
- ✅ El BDC aprobó la conversión de mi prospecto → cliente activo
- 🔴 Hotel rechazó la propuesta
- ☕ Mi BDC desbloqueó un caso Café
- ⚫ Cliente activo pasó a Negro (pausado)
- 📊 Solicitud de reporte por parte del BDC
- 🎯 Recordatorio de seguimiento programado

**Estados**
- 🟠 Sin leer (cuenta en el badge)
- 🟢 Leída

---

## N1 — SIDEBAR (Módulos del Business Developer)

```
SIDEBAR
   ├─ DASHBOARD
   ├─ PIPELINE             (Mis prospectos por status)
   ├─ MI TERRITORIO        (rutas + zonas + mapa)
   ├─ PROPUESTAS           (Propuesta Personalizada)
   ├─ DOCUMENTOS T&C       (creación con BDC)
   └─ CLIENTES ACTIVOS     (referente comercial post-Naranja)
```

> [!note]
> El BD **NO** tiene módulo "Mi Equipo", "Reportes ejecutivos", ni acción de "Conversión". Esos son del BDC.

---

## 📊 Módulo DASHBOARD

### KPIs personales del mes
- Prospectos en cada status del Semáforo Onboarding
- Propuestas enviadas (Verde)
- Hoteles en negociación (Amarillo / Rosa)
- Conversiones cerradas (Naranja)
- Tasa de conversión personal
- Rechazos del mes
- Visitas en frío realizadas

### Vistas resumen
- **Mis prospectos por status:** mini-pipeline con conteo por etapa.
- **Próximos seguimientos:** lista de prospectos que requieren contacto (basado en último contacto y status).
- **Alertas:** prospectos sin actividad >X días.

### Acciones rápidas
- ➕ Identificar nuevo prospecto
- ➕ Registrar visita en frío
- ➕ Elaborar nueva Propuesta
- 📞 Registrar intento de contacto

---

## 📋 Módulo PIPELINE (Mis Prospectos)

### Sub-vistas (por status del [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]])

- ⚪ **Gris** — Identificados (sin contacto aún)
- 🔵 **Azul Claro** — Contacto + datos recopilados
- 🟢 **Verde** — Propuesta enviada
- 🟡 **Amarillo** — En seguimiento (T&C en construcción)
- 🩷 **Rosa** — Negociación de términos
- 🟠 **Naranja** — Cliente activo (post-conversión)
- 🔴 **Rojo** — Rechazo
- ⚫ **Negro** — Cliente pausado / inactivo
- 🟤 **Café** — Estancamiento (gestiona el BDC)
- 📂 **Toda** — Vista completa de mi territorio

### Filtros
- Status (uno o varios)
- Ruta / Zona
- Fecha de identificación (rango)
- Días sin contacto
- Buscar por nombre / ciudad

### Detalle del prospecto
- **Cabecera:** nombre, foto, dirección, contacto principal, status actual, días en status.
- **Datos del hotel:** email, teléfono, contacto, cargo, necesidad del negocio.
- **Histórico de contactos:** llamadas, emails, visitas, resultados.
- **Documentos asociados:** Propuesta enviada, T&C borrador.
- **Línea de tiempo (timeline):** cambios de status con fecha, autor, comentario.

### Acciones
- ➕ **Identificar prospecto** *(crea registro en Gris)*
- ✏️ **Editar perfil del hotel** *(Azul Claro)*
- ➕ **Registrar visita en frío**
- ➕ **Registrar intento de contacto**
- ✏️ **Avanzar status** (Gris → Azul Claro → Verde → Amarillo → Rosa)
- 🔴 **Marcar rechazo (Rojo)** con motivo
- ↩️ **Reactivar desde Rojo** (vuelve a Azul Claro)
- ☕ **Marcar estancamiento (Café)** *(BDC se encarga del desbloqueo)*

> [!warning]
> El BD **NO** puede aprobar conversión, validar T&C, crear Usuario del Hotel, desbloquear Café, marcar/reactivar Negro. Todo eso es del BDC.

---

## 🗺️ Módulo MI TERRITORIO

### Vista principal
- **Mapa interactivo** con mis rutas y zonas asignadas.
- **Pines por status** del prospecto en cada ubicación.
- **Lista lateral** de prospectos por ruta.

### Filtros
- Ruta
- Zona
- Status
- Buscar por nombre

### Acciones
- 👁️ Ver detalle del prospecto
- ➕ Identificar nuevo prospecto en el mapa
- 📍 Marcar ruta del día (planeación de visitas)

---

## 📝 Módulo PROPUESTAS

### Sub-vistas
- ✏️ **Borradores** — propuestas en construcción
- 📤 **Enviadas** — esperando respuesta del hotel
- ✅ **Aceptadas** — el hotel mostró interés (avanzaron a Amarillo)
- ❌ **Rechazadas** — el hotel rechazó (Rojo)
- 📂 **Histórico**

### Acciones
- ➕ **Elaborar Propuesta Personalizada** (RF-V-04 — Verde)
- 📤 **Enviar al hotel** (RF-V-05)
- ✏️ **Editar borrador**
- 📥 **Exportar PDF**
- 📋 **Duplicar** (usar como plantilla para otro prospecto)

### Detalle
- Datos del hotel destino
- Servicios propuestos
- Precios y condiciones
- Vigencia de la propuesta
- Estado (borrador / enviada / respondida)
- Histórico de envíos

> [!info]
> La Propuesta Personalizada se elabora exclusivamente en status **Verde** (RR-V-09). Si el prospecto está estancado (Café), el BDC tomará el caso para desbloquear y habilitar una nueva propuesta.

---

## 📄 Módulo DOCUMENTOS T&C

### Sub-vistas
- ✏️ **Borradores** — T&C en construcción
- ⏳ **Pendientes de validación BDC**
- ✅ **Validados** (listos para Rosa)
- 📂 **Histórico**

### Acciones
- ➕ **Crear Documento de T&C** *(BD o BDC, en status Amarillo)*
- ✏️ **Editar borrador** del T&C
- 📤 **Enviar al BDC para validación**
- 👁️ **Ver feedback del BDC**

### Campos obligatorios del T&C (RR-V-10)

| Campo |
|---|
| Pay rate |
| Bill rate |
| Overtime |
| Festivos |
| Calendario |

> [!warning]
> El BD **NO** valida ni aprueba el T&C. Solo lo crea y edita. La validación final es del BDC (RR-V-15).

---

## 🏨 Módulo CLIENTES ACTIVOS (referente comercial)

### Vista principal
- Lista de clientes activos (status Naranja) en mi territorio.
- Datos comerciales (no operativos).
- Histórico del onboarding (cuándo se convirtió, T&C aplicable, vigencia).

### Filtros
- Ruta / Zona
- Fecha de conversión
- Buscar por nombre

### Acciones
- 👁️ **Ver detalle del cliente** (datos comerciales)
- 📞 **Registrar contacto comercial** (visita de cortesía, follow-up)

> [!important]
> Post-Naranja, BD y BDC son **referentes comerciales** sin permisos operativos (RR-V-12). NO crean requisiciones, NO editan el hotel, NO gestionan personal — eso es del depto Hotel y Reclutamiento.

---

## Flujo operativo del Business Developer

```
1. Login → Dashboard (mis KPIs y próximos seguimientos)
   │
   ▼
2. Identifico nuevo prospecto en mi territorio (Gris)
   │
   ▼
3. Visita en frío → Recopilo datos → Azul Claro
   │
   ▼
4. Elaboro Propuesta Personalizada → Envío → Verde
   │
   ▼
5. ¿Hotel responde con interés?
      ├─ SÍ → Avanzo a Amarillo
      ├─ NO → Marco Rojo (rechazo)
      └─ Estancado → Marco Café (BDC se encarga)
   │
   ▼
6. Amarillo: Creo Documento de T&C (con apoyo del BDC)
   │
   ▼
7. Envío T&C al BDC para validación
   │
   ▼
8. Iniciamos negociación (Rosa) — BD + BDC
   │
   ▼
9. BDC aprueba conversión → Naranja
   │
   ▼
10. Hotel cliente activo → BD queda como referente comercial
```

---

## Diferencias clave vs BDC

| Aspecto | BD | BDC |
|---|---|---|
| Identificar prospecto (Gris) | ✅ | — |
| Crear perfil (Azul Claro) | ✅ | — |
| Elaborar Propuesta Personalizada | ✅ exclusivo | — |
| Crear Documento de T&C | ✅ | ✅ apoyo |
| Validar Documento de T&C | ❌ | ✅ exclusivo |
| Negociar (Rosa) | ✅ | ✅ |
| Crear Usuario del Hotel | ❌ | ✅ exclusivo |
| Aprobar conversión | ❌ | ✅ exclusivo |
| Gestionar Rojo | ✅ | — |
| Desbloquear Café | ❌ | ✅ exclusivo |
| Gestionar Negro | ❌ | ✅ exclusivo |
| Mi Equipo (BDs a cargo) | ❌ | ✅ exclusivo |
| Reportes ejecutivos | ❌ | ✅ exclusivo |
| Visibilidad | Mi territorio | Toda la zona / rutas a cargo |

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
║                   ROL: BUSINESS DEVELOPER                     ║
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
│ 📊 Dashboard │  KPIs personales · Próximos seguimientos      │
│ 📋 Pipeline  │  Mis prospectos por status                    │
│ 🗺️ Territorio│  Mapa · Rutas · Pines por status              │
│ 📝 Propuesta │  Borradores · Enviadas · Histórico            │
│ 📄 T&C       │  Borradores · Validación BDC                  │
│ 🏨 Clientes  │  Activos (referente comercial)                │
└──────────────┴───────────────────────────────────────────────┘
```

---

## Relacionado

- [[Ventas/Roles/Business Developer|Business Developer]] (definición del rol)
- [[Ventas/Roles/Business Developer Coordinator|Business Developer Coordinator]]
- [[Ventas/Ventas|Ventas]]
- [[Ventas/Reglas de Ventas|Reglas de Ventas]]
- [[Ventas/Onboarding-Hotel/Onboarding-Hotel|Onboarding-Hotel]]
- [[Ventas/Onboarding-Hotel/Flujo de Onboarding|Flujo de Onboarding]]
- [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]]
- [[Ventas/Onboarding-Hotel/Conceptos/Propuesta Personalizada|Propuesta Personalizada]]
- [[Ventas/Onboarding-Hotel/Conceptos/Documento de Términos y Condiciones|Documento de Términos y Condiciones]]
- [[Hotel/Hotel|Hotel]] (destino post-Naranja)
