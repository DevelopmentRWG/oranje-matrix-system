---
tags:
  - arquitectura
  - rol/colaborador
aliases:
  - Feature Map Colaborador
---

# FEATURE MAP — COLABORADOR

---

## Mapa de funcionalidades (Primarias / Secundarias)

```
PLATAFORMA COLABORADOR — MÓVIL + WEB (COL)
│
├── PRIMARIAS
│   │
│   ├── Onboarding
│   │   ├── Fase 2 — Alta en la app
│   │   │   ├── SSN / ITIN (opcional; sin ambos → aviso retención 16% reembolsable, ver Deducciones)
│   │   │   ├── Documento SSN/ITIN (adjunto — JPG/PNG/PDF, opcional · recomendado si hay SSN/ITIN)
│   │   │   ├── Posición (catálogo)
│   │   │   ├── Nivel de inglés (catálogo)
│   │   │   ├── Nivel de experiencia
│   │   │   ├── Tipo de transporte
│   │   │   └── Modalidad de contratación (catálogo)
│   │   └── Fase 3 — Datos de emergencia
│   │       ├── Contacto de emergencia (nombre, teléfono, parentesco)
│   │       ├── Tipo de sangre
│   │       └── Alergias o condiciones médicas
│   │
│   ├── Asistencia / Ponche QR
│   │   ├── Escanear QR (cámara del dispositivo)
│   │   ├── Ponche — Entrada (inicio de jornada)
│   │   ├── Ponche — Salida Lunch
│   │   ├── Ponche — Entrada Lunch (regreso de lunch)
│   │   ├── Ponche — Salida Break
│   │   ├── Ponche — Entrada Break (regreso de break)
│   │   └── Ponche — Salida (fin de jornada)
│   │
│   ├── Disponibilidad
│   │   ├── Toggle — Activar Amarillo (disponible voluntario)
│   │   └── Toggle — Desactivar Amarillo
│   │
│   └── Reportar Accidente
│       ├── Crear tarjeta de accidente (Escenario A — colaborador reporta primero)
│       │   ├── Fecha y hora del incidente
│       │   ├── Descripción del accidente
│       │   └── Fotos / evidencia (opcional)
│       └── Ver mis accidentes reportados (historial propio)
│
└── SECUNDARIAS
    │
    ├── Dashboard
    │   ├── Mi estado actual (color del semáforo + nombre)
    │   └── Próximo turno (fecha, hora, hotel — si tiene asignación)
    │
    ├── Mi Schedule
    │   ├── Vista semanal de mis turnos asignados
    │   ├── Semana en curso y siguiente (si aplica)
    │   └── Detalle de turno (hotel, posición, horario)
    │
    ├── Mi Timesheet
    │   ├── Tabla de ponches de la semana (6 columnas)
    │   ├── Horas brutas por jornada
    │   ├── Deducción de lunch por jornada
    │   ├── Horas netas por jornada
    │   └── Total horas netas de la semana
    │
    ├── Mi Pago
    │   ├── Monto total a cobrar esta semana
    │   ├── Desglose por hotel (si trabajó en más de uno)
    │   └── Semana y rango de fechas del consolidado
    │
    ├── Notificaciones
    │   ├── Alta validada (Reclutadora aprobó → Verde fuerte)
    │   ├── Alta pendiente de corrección
    │   ├── Nueva asignación recibida (→ estado Café)
    │   ├── Fin de asignación temporal
    │   ├── Cambio de estado del semáforo
    │   └── Actualización en tarjeta de accidente
    │
    └── Mi Perfil
        ├── Datos de Fase 1 (nombre, edad, género, domicilio, teléfono — editables con límites)
        ├── Datos de Fase 2 (SSN/ITIN enmascarado, posición, inglés, experiencia, transporte, modalidad; documento de SSN/ITIN almacenado)
        ├── Datos de Fase 3 (contacto de emergencia, sangre, alergias — editables)
        ├── Estado actual del semáforo (color + nombre)
        └── Configuración (cambiar contraseña, preferencias de notificación)
```

---

## Funcionalidades del Colaborador

| Feature | Permitido |
|---|---|
| Completar alta Fase 2 | ✅ acción de onboarding |
| Completar datos de emergencia Fase 3 | ✅ acción de onboarding |
| Ponchar vía QR (6 ponches) | ✅ acción diaria principal |
| Activar disponibilidad voluntaria (Amarillo) | ✅ única acción autónoma de cambio de estado |
| Reportar accidente (Escenario A) | ✅ |
| Consultar Mi Schedule | ✅ (solo lectura) |
| Consultar Mi Timesheet | ✅ (solo lectura) |
| Consultar Mi Pago semanal | ✅ (solo lectura) |
| Ver notificaciones | ✅ (solo lectura) |
| Ver Mi Perfil y estado del semáforo | ✅ (solo lectura + edición limitada) |
| Editar Schedule | ❌ (exclusivo del Manager de Área — RR-C-01) |
| Corregir ponche propio | ❌ (exclusivo del Manager de Área) |
| Generar QR | ❌ (exclusivo del Manager de Área / Manager General) |
| Ver datos de otros colaboradores | ❌ (RR-C-01) |
| Aceptar / rechazar asignaciones | ❌ (modelo pasivo) |
| Solicitar reasignación directamente | ❌ (modelo pasivo) |
| Ponchar por QR desde web | ❌ — exclusivo de móvil (RR-C-04); requiere cámara del dispositivo |
| Ver Indicador de Lunch Extendido | ❌ (exclusivo de Inspección y Reclutamiento) |
