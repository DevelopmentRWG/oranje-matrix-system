---
tags:
  - arquitectura
  - global
  - diseño
aliases:
  - Convenciones de Diseño
  - Sistema de Diseño Oranje
  - Semilla de Diseño
---

# Sistema de Diseño Oranje (Semilla)

Define los tokens visuales y componentes compartidos de la plataforma Oranje. La fuente de verdad del CSS es el archivo `oranje-seed.css`, ubicado en `oranje-mockups/Mockups/oranje-seed.css` (repo de mockups, no en este vault).

> [!info]
> Todo mockup nuevo debe enlazar `oranje-seed.css` y solo agregar CSS específico del rol encima. No se reimplementan componentes por rol. El origen de la semilla fue el mockup del Líder de Grupo.

---

## Tokens de diseño

### Paleta Oranje

| Token | Valor | Uso |
|---|---|---|
| `--o-50` | #FFF6E8 | Tinte más claro |
| `--o-500` | #FF8E00 | Primario (naranja Oranje) |
| `--o-700` | #C85F00 | Variante oscura |

Gradientes: `--grad-brand`, `--grad-warm`, `--grad-hero`, `--grad-soft`.

### Neutrales

| Token | Valor |
|---|---|
| `--bg` | #F6F4F1 |
| `--surface` | #FFFFFF |
| `--surface-2` | — |
| `--surface-3` | — |
| `--line` | — |
| `--ink` | #1A1108 |
| `--ink-2` | — |
| `--ink-3` | — |
| `--ink-4` | — |

### Semánticos

| Token | Valor |
|---|---|
| `--red` | #E11919 |
| `--yellow` | #FFD500 |
| `--green` | #1FA84A |
| `--blue` | #3B7DDD |
| `--purple` | #7B2CBF |

### Colores del Semáforo del Colaborador

Usados exclusivamente para representar los 12 estados del [[Semáforo del Colaborador]].

| Token | Estado |
|---|---|
| `--st-blanco` | Blanco |
| `--st-negro` | Negro |
| `--st-verde-manzana` | Verde manzana |
| `--st-azul-claro` | Azul claro |
| `--st-naranja` | Naranja |
| `--st-rosa` | Rosa |
| `--st-morado` | Morado |
| `--st-rojo` | Rojo |
| `--st-amarillo` | Amarillo |
| `--st-verde` | Verde |
| `--st-cafe` | Café |
| `--st-gris` | Gris |

### Layout y estilos base

| Token | Valor | Descripción |
|---|---|---|
| `--sb` | 248px | Ancho del sidebar |
| `--hd` | 64px | Alto del header |
| `--r-lg` | — | Radio grande |
| `--r-md` | — | Radio medio |
| `--r-sm` | — | Radio pequeño |
| `--ease` | — | Curva de animación |
| `--sh-sm` | — | Sombra pequeña |
| `--sh-md` | — | Sombra media |
| `--sh-lg` | — | Sombra grande |
| `--sh-orange` | — | Sombra naranja (acento) |

Tipografía: **Poppins**. Iconografía: **Material Icons** (variantes Round y Outlined).

---

## Componentes del sistema

- **Shell** (`.app`, `.sidebar`, `.main`, `.header`, `.content`): estructura base de la app; contiene todos los demás elementos.
- **Navegación lateral** (`.sb-item`, `.sb-label`, `.count`, `.sb-foot`, `.sb-user`): ítems del sidebar con barra de acento activa.
- **Header** (`.hd-crumbs`, `.ic-btn`, `.badge`, `.hd-profile`, `.avatar`): breadcrumbs a la izquierda; botones de acción con badge y perfil a la derecha.
- **Dropdowns de header** (`.dd`, `.notif-item`, `.prof-dd`, `.prof-menu`): panel de notificaciones y menú de perfil desplegables desde el header.
- **Page header** (`.ph`): encabezado de cada vista con título y acciones de página.
- **Botones** (`.btn` con variantes `primary`, `ghost`, `sm`, `block`).
- **Cards** (`.card`, `.card-h`, `.card-b`): contenedor genérico de contenido.
- **KPI rico** (`.kpi`, `.ki`, `.val`, `.trend`, `.foot`): tarjeta de métrica con chip de ícono, valor principal, tendencia y pie; tinte por métrica.
- **Card destacada** (`.qa-hero`): card de llamada a la acción principal.
- **Accesos rápidos** (`.qa` con variantes `primary`, `soft`, `line`): chips de ícono en tonos naranja para acciones frecuentes.
- **Tile** (`.tile`): bloque compacto de información.
- **Chip de semáforo** (`.st-chip`): pastilla de color que representa el estado del [[Semáforo del Colaborador]].
- **Meta pill** (`.meta-pill`): etiqueta de metadato.
- **Tablas** (`.tbl`): tabla de datos con estilo unificado.
- **Formularios** (`.field`, `.inp`, `.sel`, `.ta`, `.upload`): campos de texto, selectores, áreas de texto y carga de archivos.
- **Filas de info** (`.irow`): fila de clave/valor para detalle de entidad.
- **Banners** (`.banner` con variantes `info`, `warn`, `ok`): alertas contextuales.
- **Toggle** (`.switch`): interruptor on/off.
- **Tabs** (`.tabs`, `.tab`): pestañas de navegación dentro de una vista.
- **Stepper de flujo** (`.flow`, `.flow-step`, `.flow-ic`, `.flow-num`, `.flow-arrow`): proceso por pasos horizontal con íconos numerados y flechas; ideal para explicar flujos de estado (p. ej. Amarillo → Café → Verde).
- **Empty state** (`.empty`): estado vacío con ícono y mensaje, para listas o tablas sin datos.
- **Toast** (`#toast`): notificación temporal de retroalimentación (oculta con opacidad cuando inactiva).
- **Modal** (`.modal-bg`, `.modal`): capa de diálogo.

---

## Principios de diseño

> [!important]
> Estas reglas aplican a todos los mockups de la plataforma Oranje.

1. **Reutilizar la semilla, no reimplementar.** Cada mockup enlaza `oranje-seed.css` y solo agrega estilos exclusivos del rol encima. No se duplican componentes.
2. **Nada decorativo.** Todo lo que parece clickeable debe funcionar. No se agregan elementos UI sin comportamiento asociado.
3. **Notificaciones y Perfil van en el header.** La campana (notificaciones) y el avatar (menú de perfil) viven en el header, no como módulos del sidebar.
4. **Iconografía en tonos naranja.** Las acciones rápidas usan chips de ícono en tonos naranja para armonía cálida; se evitan colores sólidos chillones.

---

## Mockups que usan la semilla

| Mockup | Ruta en repo | Notas |
|---|---|---|
| Líder de Grupo | `Mockups/Reclutamiento/Lider de grupo/Lider de Grupo - Oranje.html` | Origen de la semilla |
| Colaborador | `Mockups/Colaborador/Colaborador - Oranje.html` | — |

---

## Relacionado

- [[Estructura General App]]
- [[Semáforo del Colaborador]]
- [[00 - Arquitectura Colaborador]]
- [[12 - Mockup y Decisiones de UI]]
