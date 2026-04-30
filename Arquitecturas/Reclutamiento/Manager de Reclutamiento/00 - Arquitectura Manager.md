---
tags:
  - arquitectura
  - rol/manager-reclutamiento
aliases:
  - Arquitectura Manager de Reclutamiento
  - Wireframe Manager de Reclutamiento
---

# Arquitectura — Manager de Reclutamiento

Wireframe de la plataforma Oranje para el rol [[Manager de Reclutamiento]]. Define el flujo de entrada, header global, sidebar de módulos y el detalle de cada módulo al que tiene acceso.

> [!info]
> El Manager **no distribuye requisiciones en el flujo normal** (modelo Self-Pick aprobado). Las requisiciones llegan al sistema y las Reclutadoras y Líderes de Grupo las toman libremente según su capacidad. El Manager solo interviene en **casos especiales** (escalamientos, ausencias, requisiciones VIP, balanceo entre grupos, corrección).

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

**Mis métricas globales**
- Cobertura global del módulo
- Requisiciones pendientes (sin tomar)
- Casos escalados pendientes
- Indicador de Calidad del módulo

🚪 Cerrar sesión

### 🔍 BUSCADOR (global)

- Requisiciones por ID
- Colaboradores por nombre / documento / teléfono
- Hoteles por nombre
- Vetados en Blacklist
- Reclutadoras y Líderes del módulo
- Casos de incidencias / disputas

### 🔔 NOTIFICACIONES (campanita con badge)

- 🚨 Caso escalado por Líder o Inspector
- 🔴 Requisición en urgencia Red sin tomar (>X horas)
- ⚫ Solicitud de aprobación de Blacklist
- 📊 Reporte recibido de un Líder de Grupo
- 🛡️ Indicador de Calidad bajó
- 💼 Requisición VIP autorizada

---

## N1 — SIDEBAR (Módulos del Manager)

```
SIDEBAR
   ├─ DASHBOARD
   ├─ RECLUTAMIENTO            (Pool + apoyo operativo)
   ├─ REQUISICIÓN              (vista global + intervención excepcional + semáforos)
   ├─ BLACKLIST                (consulta + agregar + resolver disputa + remover)
   ├─ MI EQUIPO                ← exclusivo (Líderes + Reclutadoras: gestión + supervisión)
   ├─ INCIDENCIAS              ← exclusivo (recibe escalamientos)
   └─ REPORTES                 (recibe de Líderes + genera globales)
```

---

## 📊 Módulo DASHBOARD

- KPIs globales del módulo
- Requisiciones críticas (sin tomar mucho tiempo)
- Top performers / Líderes con baja cobertura
- Casos escalados pendientes
- Indicador de Calidad

---

## 📋 Módulo REQUISICIONES (vista global, intervención excepcional)

- Lista por estado (Autorizadas / En proceso / Cubiertas / Parciales)
- Filtros por urgencia, posición, hotel, zona, tiempo en cola
- Acciones excepcionales:
  - 🎯 Tomar requisición personalmente (caso especial)
  - 👤 Asignar manualmente (VIP, balanceo, ausencia) — con justificación
  - Reasignar a otra Reclutadora
  - Forzar cambio de semáforo (con log)

---

## ⚫ Módulo BLACKLIST (CRUD completo — único rol)

- ✅ Aprobar inclusión en Blacklist (con motivo y evidencia)
- ✅ Resolver disputa (decisión final)
- ❌ Remover de Blacklist (con justificación)

---

## 👥 Módulo MI EQUIPO (exclusivo del Manager)

Sub-vistas:
- 👥 Líderes de Grupo (lista + detalle + métricas + grupo anidado)
- 🧑 Reclutadoras (lista + detalle + Líder al que pertenecen)

Acciones de gestión:
- ➕ Dar de alta Líder / Reclutadora
- 📝 Editar usuario
- 🔁 Mover Reclutadora a otro Líder
- ⏸️ Marcar inactivo / vacaciones / baja

Acciones de supervisión:
- 📊 Ver desempeño detallado
- 📝 Solicitar reporte
- 🚨 Escalar a Dirección

---

## ⚠️ Módulo INCIDENCIAS / DISPUTAS

- Casos abiertos / resueltos
- ✅ Resolver caso (decisión final con motivo)
- 🚨 Escalar a Dirección
- Cerrar caso

---

## 📈 Módulo REPORTES

- Reportes recibidos de Líderes
- Generar reporte global
- Exportar (CSV / PDF / Excel)
- Programar envío recurrente

---

## 📅 Módulo SCHEDULE (consulta global)

- Vista del Schedule de cualquier hotel
- Solo consulta — no acciones de gestión

---

## ⚙️ Módulo CONFIGURACIÓN

- Catálogos (consulta — CRUD pertenece al Admin)
- Notificaciones: configurar tipos
- Plantillas de reportes

---

## Diferencias clave vs Líder de Grupo

| Aspecto | Líder de Grupo | Manager de Reclutamiento |
|---|---|---|
| Toma requisiciones | Sí (Self-Pick) | Sí pero excepcional |
| Pool, Schedule | Acceso operativo | Acceso completo |
| Blacklist | Solo consulta | CRUD completo + decisión final |
| Mi Grupo / Mi Equipo | Ve Reclutadoras | Ve Líderes + Reclutadoras + gestión |
| Resolver disputas | ❌ | ✅ decisión final |
| Reportes | Genera y envía | Recibe + genera globales |

---

## Relacionado

- [[Manager de Reclutamiento]] (definición del rol)
- [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo de Reclutadoras]]
- [[Reclutadora]]
- [[Reclutamiento/Reclutamiento|Reclutamiento]]
- [[Core/Módulos/Blacklist|Blacklist]]
- [[QA/QA|QA]]
