---
tags:
  - modulo/core
aliases:
  - Flujo de Requisición
---

# Flujo de Requisición

Ciclo de vida operativo de una [[Requisición]] y sus posiciones: desde que el [[Hotel/Supervisor|Supervisor]] (SUP) o el [[Hotel/Manager del Hotel|Manager del Hotel]] (GH) la crean, hasta que queda **Cubierta** o es eliminada. Este flujo **consume** colaboradores de la [[Pool de Colaboradores]]; no los produce.

> [!info] Punto de encuentro con el [[Flujo de Reclutamiento]]
> La [[Pool de Colaboradores]] es el único punto donde ambos flujos se conectan. El [[Flujo de Reclutamiento]] corre de forma **continua** alimentando la pool (haya o no requisiciones); este flujo la **consume** cuando necesita cubrir posiciones.

## Actores

- **GH — [[Hotel/Manager del Hotel|Gerente del Hotel]]**: único autorizado para **autorizar** la requisición.
- **SUP — [[Hotel/Supervisor|Supervisor]]**: puede crear, modificar y preparar la requisición.
- **Reclutador — [[Reclutadora]]**: ejecuta la asignación de personal tras la autorización.

## Validación de acceso

Al inicio el sistema valida si el usuario es GH o SUP.
- **Sin acceso** → mensaje "No cuenta con acceso" → **FIN**.
- **Con acceso** → continúa al menú de operaciones (crear, modificar, autorizar, eliminar).

---

## 1. Creación de requisición

1. Se genera **Número de requisición** (ver [[#RUTINA - Número de requisición automática]]).
2. Se registran datos de cabecera: Número de requisición, Hotel, GH, **Status Apple green** (Requisición en elaboración por el hotel), fecha y hora del status.
3. Se ejecuta [[#RUTINA - Journal Requisición]].

### 1.1 Agregar posiciones

Por cada posición que se agregue:
1. Se genera **Número de posición** automático (ver [[#RUTINA - Número de posición automática]]).
2. Se capturan los datos de la posición:
   - Posición (Housekeeper, Houseman, etc.)
   - Tipo (Temporal / Permanente)
   - Cantidad de personas
   - Fecha de inicio
   - Fecha fin
   - Horario
   - Preferencia de idioma
   - Notas
3. Se asigna **Status Gold** — Posición en preparación/elaboración por el hotel, con fecha y hora del status.
4. Se ejecuta [[#RUTINA - Journal Posición]].

### 1.2 Modificar posición (antes de autorizar)

Seleccionar la posición y modificar cualquiera de los campos anteriores. Re-journal.

### 1.3 Eliminar posición (antes de autorizar)

Al confirmar eliminación → la posición pasa a **Status Purple** (eliminada físicamente) y se ejecuta el journal.

---

## 2. Modificar / Autorizar requisición existente

1. Se muestran todas las requisiciones con **Status Apple green** (En elaboración por el hotel).
2. Se selecciona la requisición en elaboración.
3. Se muestran sus posiciones.
4. Se elige una acción: **Modificar posición**, **Eliminar posición**, **Autorizar requisición** o **Eliminar requisición**.

### 2.1 Autorizar requisición

Reglas:
- **Solo el GH puede autorizar.** Si es SUP → mensaje "Solo el gerente del hotel puede autorizar la requisición".
- Debe existir **al menos una posición registrada**. Si no → mensaje "No tiene posiciones registradas, registre al menos una posición e intente nuevamente".

Si cumple:
1. La requisición cambia a **Status Green** (Requisición autorizada por el gerente del hotel) + fecha/hora.
2. Se ejecuta [[#RUTINA - Journal Requisición]].
3. **Por cada posición de la requisición**:
   - Se ejecuta [[#RUTINA - Prioridad de la posición automática]] usando la fecha de autorización y la fecha de inicio de la posición.
   - Se registra la prioridad calculada (Green / Yellow / Red — ver [[Semáforo de Urgencia de Requisición]]).
   - La posición cambia a **Status Orange** (Posición autorizada por el gerente del hotel) + fecha/hora.
   - Se ejecuta [[#RUTINA - Journal Posición]].

---

## 3. Eliminar requisición

Se muestra el mensaje: "Al confirmar la eliminación de la requisición, las posiciones registradas y la requisición serán eliminadas físicamente".

Si se confirma:
- Por cada posición → **Status Morado** (eliminada físicamente) → journal posición.
- La requisición → **Status Morado** (eliminada físicamente) → journal requisición.

---

## 4. Salir de la requisición

- Si tiene **una o más posiciones registradas** → se conserva y sale.
- Si **no tiene** posiciones → la requisición se elimina físicamente (Status Purple) → journal.

---

## 5. Entrega a Reclutamiento (post-autorización)

Una vez autorizada (Status Green), las posiciones de la requisición quedan reflejadas en el [[Core/Módulos/Schedule|Schedule]] de la semana correspondiente a su fecha de inicio. La requisición queda disponible en la bandeja compartida, priorizada por el [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición|Semáforo de Urgencia]]. Una [[Reclutadora]] o [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo]] la toma de la bandeja y el status pasa a **Yellow** (En proceso de asignación de personal por el reclutador). Si ninguna la toma en 24 horas, el [[Manager de Reclutamiento]] recibe alerta y la asigna manualmente.

La reclutadora consulta el [[Core/Módulos/Schedule|Schedule]] del hotel para ver la demanda y las posiciones pendientes de cubrir, y busca match en la [[Pool de Colaboradores]]:
- **Si hay match** → asigna el colaborador al hotel y lo registra en el [[Core/Módulos/Schedule|Schedule]].
- **Si no hay match** → la requisición queda en espera. El [[Flujo de Reclutamiento]] corre de forma continua alimentando la pool; puede escalarse prioridad por zona/posición, pero no se "lanza" el reclutamiento — ya está siempre activo.

Cierre:
- **Status Light Blue** — Cubierta totalmente por el reclutador.
- **Status Red** — Cubierta parcialmente por el reclutador.

---

## Estados (semáforos)

La requisición y sus posiciones se rigen por múltiples semáforos:

### Requisición (ciclo de vida)
Ver [[Semáforo de Requisición]]. Estados: Apple green → Green → Yellow → Light blue / Red. Purple = eliminada físicamente.

### Posición (ciclo de vida)
- **Gold** — En preparación/elaboración por el hotel.
- **Orange** — Autorizada por el gerente del hotel.
- **Purple** — Eliminada físicamente.

### Posición — cobertura
Ver [[Semáforo de Posiciones de la Requisición]]. Green (100%), Yellow (75%), Red (<75%).

### Posición — prioridad (tiempo)
Ver [[Semáforo de Urgencia de Requisición]]. Green (>120 h), Yellow (72–120 h), Red (<72 h).

---

## Rutinas auxiliares

### RUTINA - Número de requisición automática
Genera el identificador tomando fecha/hora del día + homoclave aleatoria:
- Año (4 dígitos) + Mes (2) + Día (2) + Hora (2, formato 24 h) + Minutos (2) + Homoclave (2 caracteres alfanuméricos aleatorios).
- Ejemplo: `202604081632V1`.

### RUTINA - Número de posición automática
Mismo formato que el número de requisición. Ejemplo: `202604081632V1`.

### RUTINA - Prioridad de la posición automática
Parámetros: Fecha de autorización de la requisición + Fecha de inicio de la posición.
- `> 120 horas` → **Green**.
- `72 – 120 horas` → **Yellow**.
- `< 72 horas` → **Red**.

### RUTINA - Journal Requisición
Registra en el journal de requisiciones: Requisición, Hotel, Gerente Hotel, Reclutador, Inspector, Status, Nota, Fecha y hora del status.

### RUTINA - Journal Posición
Registra en el journal de posiciones: Número de requisición, Número de posición, Posición, Cantidad de personas, Fecha de inicio, Fecha fin, Status, Fecha y hora del status.

---

## Relacionado

- [[Requisición]]
- [[Pool de Colaboradores]]
- [[Flujo de Reclutamiento]]
- [[Hotel/Supervisor|Supervisor]] (SUP)
- [[Hotel/Manager del Hotel|Manager del Hotel]] (GH)
- [[Manager de Reclutamiento]]
- [[Reclutadora]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Semáforo de Requisición]]
- [[Semáforo de Urgencia de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
