---
tags:
  - modulo/core
aliases:
  - Arquitectura del Sistema
  - Blueprint Oranje
---
# Arquitectura Organizacional del Vault Oranje Matrix System
## Blueprint para replicar en un nuevo sistema

El vault **oranje-matrix-system** documenta un sistema de operación hotelera. Esta es la arquitectura extraída como patrón replicable para cualquier sistema organizacional nuevo.

---

## 1. Principio de diseño: Hub-and-Spoke departamental

```
                    Home.md (hub central)
                         │
        ┌────────┬───────┼───────┬────────┐
        │        │       │       │        │
   Departamento Departamento  Core/   Entidad   Simulaciones/
       A/          B/      │    Central/
                       ┌───┼───┐
                  Catálogos/ Módulos/ Semáforos/
```

**Regla:** Todo se accede desde `Home.md`. Cada carpeta de primer nivel es autónoma pero interconectada vía wikilinks.

---

## 2. Estructura de carpetas (patrón replicable)

```
nuevo-sistema/
│
├── Home.md                          ← Índice maestro (hub central)
│
├── Core/                            ← Módulos transversales compartidos
│   ├── Catálogos/                   ← Datos de referencia (enums, listas)
│   │   ├── Catalogo-A.md
│   │   └── Catalogo-B.md
│   └── Módulos/                     ← Entidades y procesos del sistema
│       ├── Semáforos/               ← State-machines visuales (indicadores)
│       │   ├── Semáforo de X.md
│       │   └── Indicador de Y.md
│       ├── [Submodulo-Complejo]/    ← Carpeta propia si tiene flujo + entidad
│       │   ├── Entidad.md
│       │   └── Flujo de Entidad.md
│       ├── Modulo-Simple.md         ← Archivo único si no necesita flujo
│       └── Reglas de Negocio.md     ← Fuente de verdad centralizada
│
├── [Departamento-A]/                ← Un folder por departamento
│   ├── Departamento-A.md           ← Hub/índice del departamento
│   ├── Rol-1.md                    ← Un archivo por rol
│   ├── Rol-2.md
│   ├── Reglas de Departamento-A.md ← Reglas locales del departamento
│   └── Flujo de Proceso-A.md      ← Procesos propios del departamento
│
├── [Departamento-B]/
│   ├── ...mismo patrón...
│   └── Subfolder/                   ← Sub-áreas si el departamento es complejo
│       ├── Subfolder.md            ← Hub del sub-área
│       ├── Flujo de Sub-Proceso.md
│       └── Conceptos/             ← Definiciones propias del sub-área
│
├── [Entidad-Central]/               ← La entidad principal del negocio
│   ├── Entidad-Central.md
│   └── Reglas de Entidad.md
│
├── [Capa-de-Control]/               ← QA, auditoría, supervisión
│   ├── Control.md
│   ├── Reglas de Control.md
│   ├── Métricas y KPIs.md
│   └── Dashboard.md
│
├── Simulaciones/                    ← Documentación narrativa
│   ├── Simulación - Vista de Dept-A.md
│   └── Simulación - Vista de Dept-B.md
│
└── .claude/                         ← Agentes IA (opcional)
    └── agents/
        ├── consultor.md             ← Agente de lectura/consulta
        └── editor.md               ← Agente de escritura
```

---

## 3. Taxonomía de tipos de archivo

Cada archivo en el vault tiene un **tipo** que determina su estructura interna:

| Tipo | Convención de nombre | Propósito | Ejemplo |
|------|---------------------|-----------|---------|
| **Hub/Índice** | `[Nombre-Departamento].md` | Punto de entrada a una carpeta | `Hotel.md`, `QA.md` |
| **Rol** | `[Título del Rol].md` | Define responsabilidades de un actor | `Reclutadora.md`, `Inspector.md` |
| **Reglas** | `Reglas de [Área].md` | Restricciones y políticas | `Reglas del Hotel.md` |
| **Flujo** | `Flujo de [Proceso].md` | Workflow paso a paso | `Flujo de Nómina.md` |
| **Semáforo** | `Semáforo de [Entidad].md` | State-machine visual | `Semáforo del Colaborador.md` |
| **Indicador** | `Indicador de [Métrica].md` | KPI con umbrales | `Indicador de Calidad.md` |
| **Catálogo** | `[Nombre descriptivo].md` | Datos de referencia (enums) | `Posiciones.md`, `Zonas.md` |
| **Módulo** | `[Nombre del módulo].md` | Entidad de sistema | `Schedule.md`, `Contrato.md` |
| **Simulación** | `Simulación - [Perspectiva].md` | Recorrido narrativo | `Simulación - Vista de QA.md` |
| **Concepto** | `[Nombre del concepto].md` | Definición de un sub-elemento | `Propuesta Personalizada.md` |

---

## 4. Plantilla de cada tipo de archivo

### Hub/Índice departamental
```markdown
---
tags:
  - departamento/[nombre]
aliases:
  - [Alias alternativo]
---
# [Nombre del Departamento]

> Descripción en una línea del propósito del departamento.

## Roles
- [[Rol-1]]
- [[Rol-2]]

## Procesos
- [[Flujo de X]]

## Reglas
- [[Reglas de Departamento]]

## Relación con otros módulos
- [[Módulo-Core-Relacionado]]
- [[Otro-Departamento]]
```

### Rol
```markdown
---
tags:
  - rol/[departamento]
aliases:
  - [Nombre alternativo del rol]
---
# [Nombre del Rol]

> Descripción breve.

## Responsabilidades
- Responsabilidad 1
- Responsabilidad 2

## Interacciones
- Con [[Otro Rol]]: descripción de la interacción
- Con [[Módulo]]: cómo lo usa
```

### Flujo
```markdown
---
tags:
  - flujo/[area]
aliases:
  - [Alias]
---
# Flujo de [Proceso]

## Actores involucrados
| Actor | Rol en el flujo |
|-------|----------------|
| [[Rol-1]] | Descripción |

## Pasos
1. **[Actor]** hace X
2. ¿Condición? → SÍ: paso 3 / NO: paso 4
3. ...

## Reglas clave
- Regla aplicable 1
- Regla aplicable 2

## Relacionado
- [[Semáforo de X]]
- [[Módulo Y]]
```

### Semáforo (State-Machine)
```markdown
---
tags:
  - semaforo/[entidad]
aliases:
  - Status [Entidad] [Color1]
  - Status [Entidad] [Color2]
---
# Semáforo de [Entidad]

| Color | Estado | Responsable | Descripción |
|-------|--------|-------------|-------------|
| Verde | Activo | Sistema | ... |
| Amarillo | En riesgo | [[Rol]] | ... |
| Rojo | Crítico | [[Rol]] | ... |

## Detalle por estado

### Verde — Activo
- Condición de entrada: ...
- Acciones permitidas: ...
- Transiciones posibles: → Amarillo (si...), → Rojo (si...)

## Reglas clave
- ...

## Relacionado
- [[Flujo de X]]
- [[Reglas de Negocio]]
```

### Reglas de Negocio (centralizado)
```markdown
---
tags:
  - modulo/core
---
# Reglas de Negocio

## [Dominio 1: Entidad Central]
- Regla 1
- Regla 2

> [!important] Regla crítica destacada

## [Dominio 2: Proceso X]
- ...

> [!warning] Restricción de seguridad
```

### Catálogo
```markdown
---
tags:
  - catalogo/[nombre]
---
# [Nombre del catálogo]

- Valor 1
- Valor 2
- Valor 3

> [!info] Esta lista no es exhaustiva / es exhaustiva.

## Relacionado
- [[Módulo que lo consume]]
```

---

## 5. Sistema de conexiones (wikilinks)

### Jerarquía de referencias
```
Home.md
  └─→ [Dept].md (hub)
        ├─→ Roles (hacia abajo)
        ├─→ Flujos (hacia abajo)
        ├─→ Reglas locales (lateral)
        └─→ Core/Módulos (hacia el centro)
              ├─→ Semáforos (lateral)
              ├─→ Catálogos (datos)
              └─→ Reglas de Negocio (fuente de verdad)
```

### Regla de conexión
- **Vertical:** Hub → Roles → Flujos (de lo general a lo específico)
- **Horizontal:** Departamento ↔ Departamento (cuando interactúan)
- **Central:** Todo apunta a `Core/Módulos/` para entidades compartidas
- **Aliases:** Permiten múltiples formas de referenciar el mismo concepto

---

## 6. Sistema de tags (frontmatter)

```
Patrón: [tipo]/[área]

Tipos usados:
  - modulo/[nombre]        → Módulos core y departamentales
  - departamento/[nombre]  → Archivos departamentales
  - rol/[departamento]     → Roles de cada área
  - flujo/[area]           → Flujos de proceso
  - semaforo/[entidad]     → Indicadores de estado
  - catalogo/[nombre]      → Catálogos de referencia
```

---

## 7. Capas del sistema (de abajo hacia arriba)

```
┌─────────────────────────────────────────────┐
│  CAPA 5: Simulaciones (documentación narrativa) │
├─────────────────────────────────────────────┤
│  CAPA 4: QA / Control (transversal)            │
├─────────────────────────────────────────────┤
│  CAPA 3: Departamentos operativos              │
│  (Reclutamiento, Ventas, Inspección, etc.)     │
├─────────────────────────────────────────────┤
│  CAPA 2: Módulos Core + Semáforos              │
│  (Schedule, Pool, Timesheet, Contrato, etc.)   │
├─────────────────────────────────────────────┤
│  CAPA 1: Fundamentos                          │
│  (Catálogos + Reglas de Negocio + Entidad Central) │
└─────────────────────────────────────────────┘
```

- **Capa 1** no depende de nadie. Define los datos base y las reglas.
- **Capa 2** implementa las reglas como módulos operativos y state-machines.
- **Capa 3** consume los módulos core para sus procesos departamentales.
- **Capa 4** observa todas las capas inferiores y mide su desempeño.
- **Capa 5** documenta recorridos completos a través de todas las capas.

---

## 8. Números del sistema actual (referencia)

| Concepto | Cantidad |
|----------|----------|
| Departamentos | 8 (+ Core + Entidad Central) |
| Roles | 14 |
| Flujos | 6 |
| Semáforos/Indicadores | 7 |
| Catálogos | 5 |
| Módulos Core | ~10 |
| Simulaciones | 7 |
| Total archivos .md | ~89 |

---

## 9. Checklist para replicar esta arquitectura en un nuevo sistema

1. [ ] Definir la **entidad central** del negocio (equivalente a "Colaborador")
2. [ ] Identificar los **departamentos** que operan sobre esa entidad
3. [ ] Crear `Home.md` como hub central
4. [ ] Crear `Core/` con:
   - [ ] `Catálogos/` — datos de referencia del sistema
   - [ ] `Módulos/` — entidades compartidas entre departamentos
   - [ ] `Módulos/Semáforos/` — indicadores de estado por entidad clave
   - [ ] `Reglas de Negocio.md` — fuente de verdad centralizada
5. [ ] Por cada departamento crear carpeta con:
   - [ ] `[Dept].md` — hub/índice
   - [ ] Un archivo por rol
   - [ ] `Reglas de [Dept].md`
   - [ ] `Flujo de [Proceso].md` si tiene procesos propios
6. [ ] Crear `Simulaciones/` con un recorrido por perspectiva de departamento
7. [ ] Conectar todo con wikilinks bidireccionales
8. [ ] Aplicar tags con patrón `[tipo]/[área]`
9. [ ] (Opcional) Crear agentes Claude en `.claude/agents/`

---

## 10. Anti-patrones evitados en este vault

- **No hay archivos huérfanos** — todo está enlazado desde al menos un hub
- **No hay reglas duplicadas** — las reglas viven en un solo lugar ([[Reglas de Negocio]] central o `Reglas de [Dept].md` local) y se referencian, no se copian
- **No hay jerarquía profunda** — máximo 4 niveles de anidación
- **No hay mezcla de idiomas** — todo en español consistentemente
- **Los semáforos no definen reglas** — las implementan. La definición está en [[Reglas de Negocio]]
