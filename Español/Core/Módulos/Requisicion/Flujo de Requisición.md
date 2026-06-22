---
tags:
  - modulo/core
aliases:
  - Flujo de Requisición
---

# Flujo de Requisición

Ciclo de vida operativo de una [[Requisición]] y sus posiciones: desde que el [[Hotel/Manager General|Manager General]] (GM), el [[Hotel/Manager de Área|Manager de Área]] (GH) o el [[Hotel/Supervisor|Supervisor]] (SUP) la crean, hasta que queda **Cubierta** o es eliminada. Este flujo **consume** colaboradores de la [[Pool de Colaboradores]]; no los produce.

> [!info] Punto de encuentro con el [[Flujo de Reclutamiento]]
> La [[Pool de Colaboradores]] es el único punto donde ambos flujos se conectan. El [[Flujo de Reclutamiento]] corre de forma **continua** alimentando la pool (haya o no requisiciones); este flujo la **consume** cuando necesita cubrir posiciones.

## Actores

- **GM — [[Hotel/Manager General|Manager General]]**: máxima autoridad del hotel. Puede crear, autorizar y rechazar requisiciones.
- **GH — [[Hotel/Manager de Área|Manager de Área]]**: puede crear, autorizar y rechazar requisiciones.
- **SUP — [[Hotel/Supervisor|Supervisor]]**: puede crear, modificar y preparar la requisición. No puede autorizar.
- **Reclutadores — [[Reclutadora|Reclutadoras]] / [[Reclutamiento/Líder de Grupo de Reclutadoras|Líderes de Grupo]]**: varios **reclutadores participantes** pueden trabajar la misma requisición a la vez (modelo colaborativo, RR-15) y ejecutan la asignación de personal tras la autorización. No hay dueño único.

## Validación de acceso

Al inicio el sistema valida si el usuario es GM, GH o SUP.
- **Sin acceso** → mensaje "No cuenta con acceso" → **FIN**.
- **Con acceso** → continúa al menú de operaciones (crear, modificar, autorizar, eliminar).

---

## 1. Creación de requisición

1. Se genera **Número de requisición** (ver [[#RUTINA - Número de requisición automática]]).
2. Se registran datos de cabecera: Número de requisición, Hotel, GM/GH, **Status Apple green** (Requisición en elaboración por el hotel), fecha y hora del status.
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
- **Solo el GM o GH pueden autorizar.** Si es SUP → mensaje "Solo el gerente del hotel puede autorizar la requisición".
- Debe existir **al menos una posición registrada**. Si no → mensaje "No tiene posiciones registradas, registre al menos una posición e intente nuevamente".

Si cumple:
1. La requisición cambia a **Status Green** (Requisición autorizada) + fecha/hora.
2. El [[Inspector]] de la cabecera se asigna automáticamente según la [[Core/Catálogos/Zonas|zona]] del hotel.
3. Se ejecuta [[#RUTINA - Journal Requisición]].
4. **Por cada posición de la requisición**:
   - Se ejecuta [[#RUTINA - Prioridad de la posición automática]] usando la fecha de autorización y la fecha de inicio de la posición.
   - Se registra la prioridad calculada (Green / Yellow / Red — ver [[Semáforo de Urgencia de Requisición]]).
   - La posición cambia a **Status Orange** (Posición autorizada) + fecha/hora.
   - Se ejecuta [[#RUTINA - Journal Posición]].

### 2.2 Rechazar requisición

Si el GM o GH rechaza la requisición:
1. La requisición regresa a **Status Apple green** (En elaboración) con las observaciones.
2. Se ejecuta [[#RUTINA - Journal Requisición]].
3. El creador corrige la **misma requisición** (mismo número/ID) y la reenvía para autorización.

> [!important] No se genera una nueva requisición tras el rechazo. Se modifica y reenvía la requisición original con el mismo identificador.

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

Una vez autorizada (Status Green), las posiciones de la requisición quedan reflejadas en el [[Core/Módulos/Schedule|Schedule]] de la semana correspondiente a su fecha de inicio. La requisición queda disponible en la bandeja compartida, priorizada por el [[Core/Módulos/Semáforos/Semáforo de Urgencia de Requisición|Semáforo de Urgencia]].

**Toma colaborativa (modelo colaborativo, RR-15):** la requisición puede tener **varios reclutadores participantes** trabajándola a la vez; no hay dueño único.
- Una [[Reclutadora]] o [[Reclutamiento/Líder de Grupo de Reclutadoras|Líder de Grupo]] la **toma** de la bandeja y el status pasa a **Yellow** (En proceso). Se ejecuta [[#RUTINA - Journal Requisición]] con evento `TOMO` + actor.
- Cuando ya hay reclutadores trabajándola, otro reclutador puede **unirse** (acción "Unirme"): se agrega como reclutador participante adicional **sin desplazar** a los existentes y **sin retroceder** el semáforo. Se ejecuta journal con evento `SE_UNIO` + actor. Nadie "pierde" la requisición.
- Cualquier reclutador participante puede **salir** (acción "Salir"): se retira solo a él. Si quedan otros reclutadores, la requisición sigue en **Yellow** (En proceso) y **no se resetea** lo que otros ya asignaron. Solo cuando sale el **último** reclutador la requisición vuelve a **Green** (Autorizada). Se ejecuta journal con evento `SALIO` + actor.
- Si ninguna la toma en 24 horas, el sistema la asigna automáticamente a la [[Reclutadora]] con menor carga de requisiciones activas (queda como reclutador participante inicial).

El avance de cobertura es **compartido** entre todos los reclutadores participantes. Cada uno consulta el [[Core/Módulos/Schedule|Schedule]] del hotel para ver la demanda y las posiciones pendientes de cubrir, y busca match en la [[Pool de Colaboradores]]:
- **Si hay match** → asigna el [[Pool de Colaboradores|colaborador]] al hotel y lo registra en el [[Core/Módulos/Schedule|Schedule]]. Se ejecuta [[#RUTINA - Journal Posición]] con evento `ASIGNO_COLAB` + actor.
- **Si no hay match** → la requisición queda en espera. El [[Flujo de Reclutamiento]] corre de forma continua alimentando la pool; puede escalarse prioridad por zona/posición, pero no se "lanza" el reclutamiento — ya está siempre activo.

> [!important] Lock a nivel posición/slot (no a nivel requisición)
> El bloqueo de concurrencia opera a nivel de **posición/slot**, no de la requisición completa: dos reclutadores no pueden asignar el mismo colaborador al mismo slot. Si dos intentan cubrir la misma posición, **gana el primero** y el segundo recibe "posición ya cubierta". Tomar una requisición ya tomada **no bloquea** — te unes como reclutador participante.

Cierre:
- **Status Light Blue** — Cubierta totalmente. Journal con evento `CAMBIO_STATUS` + actor (quién la cerró).
- **Status Red** — Cubierta parcialmente. Journal con evento `CAMBIO_STATUS` + actor (quién la cerró).

---

## Estados (semáforos)

La requisición y sus posiciones se rigen por múltiples semáforos:

### Requisición (ciclo de vida)
Ver [[Semáforo de Requisición]]. Estados: Apple green → Green → Yellow → Light blue / Red. Purple = eliminada físicamente.

### Posición (ciclo de vida)
- **Gold** — En preparación/elaboración por el hotel.
- **Orange** — Autorizada.
- **Purple** — Eliminada físicamente.

### Posición — cobertura
Ver [[Semáforo de Posiciones de la Requisición]]. Green (100%), Yellow (75%), Red (<75%).

### Posición — prioridad (tiempo)
Ver [[Semáforo de Urgencia de Requisición]]. Green (>120 h), Yellow (72–120 h), Red (<72 h).

---

## Rutinas auxiliares

### RUTINA - Número de requisición automática
Genera el identificador tomando fecha/hora del día + homoclave aleatoria:
- Año (4 dígitos) + Mes (2) + Día (2) + Hora (2, formato 24 h) + Minutos (2) + Homoclave (2 caracteres alfanuméricos aleatorios: letras y/o dígitos).
- Ejemplo: `202604081632V1` — donde `V1` es la homoclave.

### RUTINA - Número de posición automática
Mismo formato que el número de requisición. Ejemplo: `202604081632V1`.

### RUTINA - Prioridad de la posición automática
Parámetros: Fecha de autorización de la requisición + Fecha de inicio de la posición.
- `> 120 horas` → **Green**.
- `72 – 120 horas` → **Yellow**.
- `< 72 horas` → **Red**.

### RUTINA - Journal Requisición
Registra en el journal de requisiciones un **evento por acción** (no solo cambios de status), cada uno con su **actor** (rol y nombre) y timestamp. Campos: Requisición, Hotel, Manager General / Manager de Área, **Reclutadores** (lista de reclutadores participantes), Inspector, **Tipo de evento**, **Actor (rol y nombre)**, Status, Nota, Fecha y hora del evento.

Tipos de evento registrados: `TOMO` (primer reclutador toma la requisición), `SE_UNIO` (un reclutador se une como participante adicional), `SALIO` (un reclutador se retira), `CAMBIO_STATUS` (cambio de semáforo, incluye cierre). El journal es **inmutable** y alimenta el [[Requisición#Historial de la Requisición|Historial de la Requisición]] (RR-16).

### RUTINA - Journal Posición
Registra en el journal de posiciones un **evento por acción** sobre la posición/slot, cada uno con su **actor** (rol y nombre) y timestamp. Campos: Número de requisición, Número de posición, Posición, Cantidad de personas, Fecha de inicio, Fecha fin, **Tipo de evento**, **Actor (rol y nombre)**, **Colaborador** (cuando aplica), Status, Fecha y hora del evento.

Tipos de evento registrados: `ASIGNO_COLAB` (un reclutador asigna un colaborador a la posición/slot), `REASIGNO` (desasigna/reasigna un colaborador), `CAMBIO_STATUS` (cambio de cobertura). El journal es **inmutable** y alimenta el [[Requisición#Historial de la Requisición|Historial de la Requisición]] (RR-16).

---

## Relacionado

- [[Requisición]]
- [[Pool de Colaboradores]]
- [[Flujo de Reclutamiento]]
- [[Hotel/Manager General|Manager General]] (GM)
- [[Hotel/Manager de Área|Manager de Área]] (GH)
- [[Hotel/Supervisor|Supervisor]] (SUP)
- [[Manager de Reclutamiento]]
- [[Reclutadora]]
- [[Core/Módulos/Schedule|Schedule]]
- [[Semáforo de Requisición]]
- [[Semáforo de Urgencia de Requisición]]
- [[Semáforo de Posiciones de la Requisición]]
