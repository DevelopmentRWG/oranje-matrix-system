---
tags:
  - arquitectura
  - rol/manager-de-area
aliases:
  - Feature Map Manager de Área
---

# FEATURE MAP — MANAGER DE ÁREA

---

## Mapa de funcionalidades (Primarias / Secundarias)

```
HOTEL — MANAGER DE ÁREA / GERENTE DE DEPARTAMENTO
│
├── PRIMARIAS
│   │
│   ├── Requisiciones
│   │   ├── Pendientes de autorización (Verde manzana)
│   │   ├── Autorizadas (Reclutamiento las tiene)
│   │   ├── En proceso (asignando colaboradores)
│   │   ├── Cubiertas (100%)
│   │   ├── Rechazadas (devueltas al Supervisor)
│   │   ├── Autorizar requisición
│   │   ├── Rechazar con observaciones
│   │   ├── Eliminar con posiciones (journal)
│   │   └── Ver historial / journal
│   │
│   ├── Schedule
│   │   ├── Calendario semanal del depto
│   │   ├── Editar asignaciones (reordenar turnos, mover entre días)
│   │   ├── Marcar día de descanso
│   │   └── Solicitar refuerzo a Reclutamiento
│   │
│   ├── Timesheet
│   │   ├── Tabla semanal × colaborador con 6 ponches
│   │   ├── Indicador de Cumplimiento (Verde / Amarillo / Rojo)
│   │   ├── Generar / Renovar QR (exclusivo)
│   │   └── Corregir ponche con justificación
│   │
│   └── Mi Personal
│       ├── Lista de colaboradores asignados
│       ├── Semáforo del Colaborador visible
│       ├── Poner en Stand-by (Rosa) — compartido con Supervisor
│       ├── Reportar colaborador (Rojo) — exclusivo
│       └── Ver historial de incidencias
│
└── SECUNDARIAS
    │
    ├── Análisis
    │   ├── Dashboard — KPIs del depto (cobertura, requisiciones pendientes, accidentes, cumplimiento)
    │   ├── Dashboard — Bandeja de requisiciones pendientes (CTA "Revisar")
    │   ├── Dashboard — Schedule de la semana (resumen)
    │   └── Dashboard — Posiciones críticas (sin colaborador asignado)
    │
    └── Utilidades
        ├── Dashboard — Acciones rápidas
        ├── Schedule — Exportar Schedule semanal
        └── Timesheet — Exportar Timesheet semanal
```

---

## Funcionalidades del Manager de Área

| Feature | Permitido |
|---|---|
| Autorizar requisiciones | ✅ exclusivo (capa de seguridad) |
| Rechazar requisición con observaciones | ✅ |
| Generar / Renovar QR del Timesheet | ✅ exclusivo |
| Editar Schedule semanal | ✅ |
| Corregir ponche con justificación | ✅ |
| Poner colaborador en Stand-by (Rosa) | ✅ compartido con Supervisor |
| Reportar colaborador (Rojo) | ✅ exclusivo |
| Eliminar requisición con posiciones | ✅ (journal individual por posición) |
| Crear requisición | ❌ (eso es del Supervisor) |
| Ver Indicador de Lunch Extendido | ❌ (RR-H-15) |
| Ver Schedule global del hotel | ❌ (eso es del Manager General) |
| Reportar accidente laboral | ❌ (eso es del Supervisor) |
