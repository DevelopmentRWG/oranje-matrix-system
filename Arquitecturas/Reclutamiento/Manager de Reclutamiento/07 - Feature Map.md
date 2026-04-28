---
tags:
  - arquitectura
  - rol/manager-reclutamiento
aliases:
  - Feature Map Manager
---

# FEATURE MAP — MANAGER DE RECLUTAMIENTO

---

## Mapa de funcionalidades por módulo

```
MANAGER DE RECLUTAMIENTO
├── 📊 Dashboard
│   ├── KPIs globales del depto
│   ├── Requisiciones críticas (varadas)
│   ├── Casos escalados pendientes
│   └── Indicador de Calidad
│
├── 📋 Requisiciones (vista global, intervención excepcional)
│   ├── Lista global con filtros
│   ├── Tomar requisición personal (caso especial)
│   ├── Asignar manual con justificación
│   └── Forzar cambio de semáforo
│
├── 🧑‍🤝‍🧑 Pool de Colaboradores (consulta + apoyo)
│   ├── Lista completa
│   ├── Crear colaborador (backup)
│   └── Editar (CRUD)
│
├── ⚫ Blacklist (CRUD COMPLETO — único rol)
│   ├── Aprobar inclusión
│   ├── Resolver disputa
│   ├── Remover (con justificación)
│   └── Comentar casos
│
├── 👥 Mi Equipo (EXCLUSIVO del Manager)
│   ├── Vista de Líderes con métricas
│   ├── Vista de Reclutadoras anidada
│   ├── Dar de alta Líder / Reclutadora
│   ├── Editar usuario
│   ├── Mover Reclutadora a otro Líder
│   └── Marcar inactivo / vacaciones / baja
│
├── ⚠️ Incidencias / Disputas (recibe escalamientos)
│   ├── Casos abiertos
│   ├── Investigar
│   ├── Resolver con decisión final
│   └── Escalar a Dirección
│
├── 📈 Reportes (recibe + genera)
│   ├── Reportes recibidos de Líderes
│   ├── Generar reporte global
│   ├── Comparativa entre Líderes / zonas
│   ├── Exportar (CSV / PDF / Excel)
│   └── Programar envío recurrente
│
├── 📅 Schedule (consulta global)
│   └── Vista de cualquier hotel
│
└── ⚙️ Configuración
    ├── Catálogos (consulta)
    ├── Plantillas de reportes
    └── Configuración de notificaciones
```

---

## Funcionalidades exclusivas del Manager

| Feature | Reclutadora | Líder | Manager |
|---|---|---|---|
| Tomar requisición (Self-Pick) | ✅ | ✅ | ⚠️ excepcional |
| Aprobar Blacklist | ❌ | ❌ | ✅ exclusivo |
| Resolver disputas | ❌ | ❌ | ✅ decisión final |
| Mi Equipo (gestión completa) | ❌ | ❌ | ✅ exclusivo |
| Forzar cambio semáforo | ❌ | ❌ | ✅ con justificación |
| Reportes globales para Dirección | ❌ | ❌ | ✅ exclusivo |
| Escalar a Dirección | ❌ | ❌ | ✅ exclusivo |
