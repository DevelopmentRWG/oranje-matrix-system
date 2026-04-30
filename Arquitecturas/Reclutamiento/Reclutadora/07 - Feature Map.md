---
tags:
  - arquitectura
  - rol/reclutadora
aliases:
  - Feature Map Reclutadora
---

# FEATURE MAP — RECLUTADORA

---

## Mapa de funcionalidades por módulo

```
RECLUTADORA
├── 📊 Dashboard
│   ├── KPIs personales
│   ├── Pool por posición (resumen)
│   ├── Mis Requisiciones (resumen)
│   ├── Cola de Autorizadas (vista corta)
│   └── Acciones rápidas
│
├── 📋 Requisición (Self-Pick + Semáforos)
│   ├── Cola de Autorizadas (todas las disponibles)
│   ├── Mis Requisiciones (tomadas)
│   ├── Tomar requisición
│   ├── Marcar como cubierta / parcial
│   ├── Liberar requisición
│   ├── Semáforo de Urgencia (lectura)
│   └── Semáforo de Posiciones (lectura)
│
├── 🧑‍🤝‍🧑 Reclutamiento (Pool + Crear + Asignación)
│   ├── Pool de Colaboradores (lista, filtros, detalle)
│   ├── Crear colaborador (Fase 1 — Entrevista)
│   ├── Validar alta en App (Fase 2)
│   ├── Habilitar accesos
│   ├── Registrar entrevista
│   ├── Asignar colaborador a hotel
│   ├── Asignar al Schedule
│   ├── Reasignar colaborador
│   └── Desasignar colaborador
│
└── ⚫ Blacklist
    ├── Consulta de vetados
    └── Agregar a Blacklist (con motivo y evidencia)
```

---

## Funcionalidades de la Reclutadora

| Feature | Permitido |
|---|---|
| Tomar requisiciones libremente (Self-Pick) | ✅ |
| Crear colaboradores (Fase 1) | ✅ |
| Validar alta en App | ✅ |
| Asignar al Schedule | ✅ |
| Agregar colaborador a Blacklist | ✅ (con motivo y evidencia) |
| Distribuir requisiciones a otros | ❌ (no aplica el modelo Self-Pick) |
| Resolver disputas / Remover Blacklist | ❌ (Manager exclusivo) |
| Supervisar a otros | ❌ (no tiene equipo) |
