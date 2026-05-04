---
tags:
  - arquitectura
  - rol/supervisor-hotel
aliases:
  - Feature Map Supervisor
---

# FEATURE MAP — SUPERVISOR

---

## Mapa de funcionalidades por módulo

```
SUPERVISOR (SUP)
├── 📊 Dashboard
│   ├── KPIs personales (mis requisiciones, accidentes activos)
│   ├── Requisiciones rechazadas (necesitan corrección)
│   ├── Posiciones críticas del Schedule
│   └── Acciones rápidas
│
├── 📋 Requisiciones
│   ├── Borradores
│   ├── Pendientes de autorización (Verde manzana)
│   ├── Rechazadas (con observaciones del Manager del Hotel)
│   ├── Autorizadas (en Reclutamiento)
│   ├── En proceso (Reclutamiento asignando)
│   ├── Cubiertas (100%)
│   ├── ➕ Crear nueva requisición
│   ├── ✏️ Editar borrador / requisición rechazada
│   ├── 📤 Enviar a autorización
│   └── 🗑️ Eliminar borrador
│
├── 📅 Schedule (consulta)
│   ├── Calendario semanal del depto
│   ├── Filtros por posición / cobertura / semana
│   ├── 🔔 Sugerir refuerzo (prefill nueva requisición)
│   └── Exportar Schedule semanal
│
├── ⏱️ Timesheet (consulta)
│   ├── Tabla semanal × colaborador
│   ├── Indicador de Cumplimiento (Verde / Amarillo / Rojo)
│   └── Exportar Timesheet
│
├── 👥 Mi Personal
│   ├── Lista de colaboradores asignados
│   ├── Semáforo del Colaborador visible
│   ├── 🩷 Poner en Stand-by (Rosa) — compartido con Manager del Hotel
│   ├── 📞 Contactar al colaborador
│   └── Ver historial
│
└── 🚨 Accidentes Laborales
    ├── Casos activos (en investigación por Inspector)
    ├── Casos cerrados (último mes)
    ├── Histórico
    ├── ➕ Reportar accidente — Escenario A (acudir tras notificación)
    ├── ➕ Reportar accidente — Escenario B (detectar primero)
    └── 📷 Captura presencial (foto, evidencia, testigos)
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
| Poner en Stand-by (Rosa) | ✅ compartido con Manager del Hotel |
| Sugerir refuerzo de personal | ✅ |
| Consultar Schedule / Timesheet | ✅ (solo lectura) |
| Consultar Blacklist | ✅ (solo lectura) |
| Autorizar requisición | ❌ (capa de seguridad RR-H-02) |
| Generar QR del Timesheet | ❌ (RR-H-09) |
| Corregir ponche | ❌ (RR-H-09 → solo Manager del Hotel) |
| Reportar colaborador (Rojo) | ❌ (RR-H-10) |
| Editar Schedule | ❌ (solo Manager del Hotel) |
| Ver Indicador de Lunch Extendido | ❌ (RR-H-15) |
| Visibilidad global del hotel | ❌ (solo Manager General) |
