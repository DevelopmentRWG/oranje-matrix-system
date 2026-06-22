---
tags:
  - arquitectura
  - rol/supervisor-hotel
aliases:
  - Feature Map Supervisor
---

# FEATURE MAP — SUPERVISOR

---

## Mapa de funcionalidades (Primarias / Secundarias)

```
HOTEL — SUPERVISOR (SUP)
│
├── PRIMARIAS
│   │
│   ├── Requisiciones
│   │   ├── Borradores
│   │   ├── Pendientes de autorización (Verde manzana)
│   │   ├── Rechazadas (con observaciones del Manager de Área)
│   │   ├── Autorizadas (en Reclutamiento)
│   │   ├── En proceso (Reclutamiento asignando)
│   │   ├── Cubiertas (100%)
│   │   ├── Crear nueva requisición
│   │   ├── Editar borrador / requisición rechazada
│   │   ├── Enviar a autorización
│   │   └── Eliminar borrador
│   │
│   ├── Schedule (consulta)
│   │   ├── Calendario semanal del depto
│   │   ├── Filtros por posición / cobertura / semana
│   │   └── Sugerir refuerzo (prefill nueva requisición)
│   │
│   ├── Timesheet (consulta)
│   │   ├── Tabla semanal × colaborador
│   │   └── Indicador de Cumplimiento (Verde / Amarillo / Rojo)
│   │
│   ├── Mi Personal
│   │   ├── Lista de colaboradores asignados
│   │   ├── Semáforo del Colaborador visible
│   │   ├── Poner en Stand-by (Rosa) — compartido con Manager de Área
│   │   ├── Contactar al colaborador
│   │   └── Ver historial
│   │
│   └── Accidentes Laborales
│       ├── Casos activos (en investigación por Inspector)
│       ├── Casos cerrados (último mes)
│       ├── Histórico
│       ├── Reportar accidente — Escenario A (acudir tras notificación)
│       ├── Reportar accidente — Escenario B (detectar primero)
│       └── Captura presencial (foto, evidencia, testigos)
│
└── SECUNDARIAS
    │
    ├── Análisis
    │   ├── Dashboard — KPIs personales (mis requisiciones, accidentes activos)
    │   ├── Dashboard — Requisiciones rechazadas (necesitan corrección)
    │   └── Dashboard — Posiciones críticas del Schedule
    │
    └── Utilidades
        ├── Dashboard — Acciones rápidas
        ├── Schedule — Exportar Schedule semanal
        └── Timesheet — Exportar Timesheet
```

---

## Funcionalidades del Supervisor

| Feature | Permitido |
|---|---|
| Crear requisiciones | ✅ acción principal |
| Editar borrador / requisición rechazada | ✅ |
| Enviar a autorización | ✅ |
| Eliminar borrador | ✅ |
| Reportar accidentes (Escenarios A y B) | ✅ acción principal |
| Poner en Stand-by (Rosa) | ✅ compartido con Manager de Área |
| Sugerir refuerzo de personal | ✅ |
| Consultar Schedule / Timesheet | ✅ (solo lectura) |
| Autorizar requisición | ❌ (capa de seguridad RR-H-02) |
| Generar QR del Timesheet | ❌ (RR-H-09) |
| Corregir ponche | ❌ (RR-H-09 → solo Manager de Área) |
| Reportar colaborador (Rojo) | ❌ (RR-H-10) |
| Editar Schedule | ❌ (solo Manager de Área) |
| Ver Indicador de Lunch Extendido | ❌ (RR-H-15) |
| Visibilidad global del hotel | ❌ (solo Manager General) |
