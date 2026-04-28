---
tags:
  - arquitectura
  - rol/lider-de-grupo
aliases:
  - Feature Map Líder de Grupo
---

# FEATURE MAP — LÍDER DE GRUPO DE RECLUTADORAS

---

## Mapa de funcionalidades por módulo

```
LÍDER DE GRUPO DE RECLUTADORAS
├── 📊 Dashboard
│   ├── KPIs personales (como Reclutadora)
│   ├── KPIs del grupo (extra del Líder)
│   ├── Pool por posición
│   ├── Mis Requisiciones
│   ├── Bandeja de disponibles
│   └── Acciones rápidas
│
├── 🧑‍🤝‍🧑 Pool de Colaboradores (igual que Reclutadora)
│   ├── Lista (12 estados del Semáforo del Colaborador)
│   ├── Filtros
│   ├── Detalle del colaborador
│   ├── Crear colaborador (Fase 1)
│   ├── Validar alta en App (Fase 2)
│   └── Habilitar accesos
│
├── 📋 Bandeja de Requisiciones (Self-Pick)
│   ├── Bandeja de Autorizadas
│   ├── Mis Requisiciones (tomadas)
│   ├── Tomar requisición
│   ├── Asignar colaborador
│   └── Marcar cubierta / parcial
│
├── 👥 Mi Grupo (EXCLUSIVO del Líder)
│   ├── Lista de Reclutadoras del grupo
│   ├── Detalle por Reclutadora
│   ├── Métricas individuales
│   ├── Carga actual por persona
│   └── Comunicar (chat / nota interna)
│
├── 📈 Reportes (EXCLUSIVO del Líder)
│   ├── Generar reporte del grupo
│   ├── Tipos: cobertura, desempeño, casos escalados
│   ├── Filtros (zona, fecha, posición)
│   ├── Vista previa con métricas
│   ├── Enviar al Manager
│   └── Exportar (CSV / PDF)
│
├── 📅 Schedule (consulta)
│   └── Vista del Schedule semanal del hotel
│
└── ⚫ Blacklist (consulta)
    └── Lista de vetados (no puede vetar/remover)
```

---

## Funcionalidades exclusivas del Líder

| Feature | Reclutadora | Líder | Manager |
|---|---|---|---|
| Tomar requisiciones (Self-Pick) | ✅ | ✅ | ⚠️ excepcional |
| Crear colaboradores | ✅ | ✅ | ✅ |
| Mi Grupo | ❌ | ✅ exclusivo | ❌ |
| Reportes formales | ❌ | ✅ envía al Manager | ✅ recibe + genera |
| Atender incidencias 1er nivel | ❌ | ✅ | ❌ (resuelve final) |
| Aprobar Blacklist | ❌ | ❌ | ✅ exclusivo |
