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
│   ├── Bandeja de disponibles
│   └── Acciones rápidas
│
├── 🧑‍🤝‍🧑 Pool de Colaboradores
│   ├── Lista (12 estados del Semáforo del Colaborador)
│   ├── Filtros (posición · zona · modalidad · inglés)
│   ├── Detalle del colaborador
│   ├── Crear colaborador (Fase 1)
│   ├── Validar alta en App (Fase 2)
│   └── Habilitar accesos
│
├── 📋 Bandeja de Requisiciones (Self-Pick)
│   ├── Bandeja de Autorizadas (disponibles)
│   ├── Mis Requisiciones (tomadas)
│   ├── Tomar requisición
│   ├── Asignar colaborador
│   ├── Marcar cubierta / parcial
│   └── Liberar requisición
│
├── 📅 Schedule (consulta)
│   └── Vista del Schedule semanal del hotel
│
└── ⚫ Blacklist (consulta)
    ├── Lista de vetados
    └── Consulta obligatoria antes de asignar
```

---

## Funcionalidades exclusivas de la Reclutadora

| Feature | Permitido |
|---|---|
| Tomar requisiciones libremente (Self-Pick) | ✅ |
| Crear colaboradores (Fase 1) | ✅ |
| Validar alta en App | ✅ |
| Asignar al Schedule | ✅ |
| Distribuir requisiciones a otros | ❌ (no aplica el modelo) |
| Aprobar Blacklist | ❌ (Manager exclusivo) |
| Supervisar a otros | ❌ (no tiene equipo) |
