---
tags:
  - arquitectura
  - rol/colaborador
aliases:
  - Arquitectura Colaborador
  - Wireframe Colaborador
  - Arquitectura COL
---

# Arquitectura — Colaborador

Wireframe de la app Oranje para el rol [[Colaborador]]. Define el flujo de entrada, la estructura de la app móvil y el detalle de cada funcionalidad a la que tiene acceso el colaborador como **usuario de autoservicio personal**.

> [!info]
> El Colaborador es el **sujeto pasivo** del sistema. Su única acción autónoma de cambio de estado es activar su disponibilidad voluntaria (Amarillo). Todas las demás transiciones de estado son ejecutadas por otros roles. Accede exclusivamente a SUS PROPIOS datos, nunca a datos de otros colaboradores ni a herramientas de gestión.

> [!important]
> El Colaborador accede a la plataforma desde **móvil y web (responsive)** (RR-C-04). El onboarding, las vistas de consulta y la activación de disponibilidad están disponibles en ambos canales. El ponche por QR (RF-C-03) es una acción nativa de móvil: requiere escanear el QR físico del hotel con la cámara del teléfono.

---

## N0 — Inicio

```
APP ORANJE (MOBILE)
        │
        ▼
LOGIN / AUTENTICACIÓN
        │
        ▼
ROL IDENTIFICADO / COLABORADOR
        │
        ▼
DASHBOARD PERSONAL
```

---

## N1 — Estructura de la App del Colaborador

```
PLATAFORMA COLABORADOR — MÓVIL + WEB (COL)
   │
   ├─ DASHBOARD (mi estado, próximo turno)
   ├─ MI SCHEDULE       (solo lectura)
   ├─ ASISTENCIA        (escanear QR — ponchar)
   ├─ MI TIMESHEET      (horas netas — solo lectura)
   ├─ MI PAGO           (consolidado semanal — solo lectura)
   ├─ DISPONIBILIDAD    (activar Amarillo)
   ├─ REPORTAR ACCIDENTE
   ├─ NOTIFICACIONES
   └─ MI PERFIL         (datos propios + estado del semáforo)
```

---

## Documentos de este rol

| Archivo | Descripción |
|---|---|
| [[01 - Ficha de Rol]] | Tabla resumen: ID, nombre, tipo, permisos clave, dispositivo |
| [[02 - Ficha Detallada]] | Responsabilidades completas, qué SÍ y qué NO puede hacer |
| [[03 - PRD]] | PRD-COLAB-01 · Casos de uso RF-C-01 a RF-C-10 |
| [[04 - Permisos Detallados]] | Matriz CRUD por módulo |
| [[05 - Requerimientos]] | Funcionales y no funcionales |
| [[06 - Resumen Rápido]] | Resumen ejecutivo en una página |
| [[07 - Feature Map]] | Árbol ASCII de la app del Colaborador |
| [[08 - Acciones del Usuario]] | Tabla Acción → Resultado |
| [[09 - Campos del Formulario]] | Campos de Fase 2, Fase 3, accidente y disponibilidad |
| [[10 - Validaciones]] | Reglas de validación por formulario |
| [[11 - Respuestas del Sistema]] | Mensajes y notificaciones del sistema |
| [[12 - Mockup y Decisiones de UI]] | Mockup web interactivo y decisiones de diseño UI |

---

## Fuentes conceptuales de dominio

- [[Colaborador]] — entidad, datos en 3 fases, roles que interactúan
- [[Reglas del Colaborador]] — semáforo, ponche QR, lunch, inasistencias, pago, accidente, pool
- [[Semáforo del Colaborador]] — 12 estados y transiciones completas

---

## Relacionado

- [[Colaborador]]
- [[Reglas del Colaborador]]
- [[Semáforo del Colaborador]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Timesheet]]
- [[Contabilidad/Consolidado Semanal del Colaborador|Consolidado Semanal del Colaborador]]
- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]]
- [[Pool de Colaboradores]]
- [[12 - Mockup y Decisiones de UI]]
- [[Convenciones de Diseño]]
