---
tags:
  - modulo/core
aliases:
  - Flujo de Accidente Laboral
---

# Flujo de Accidente Laboral

Ciclo de vida de un [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]]: desde que se reporta el incidente hasta que el [[QA Inspector|Inspector de zona]] cierra la tarjeta con la información completa. El flujo tiene dos escenarios de origen según quién detecta primero el accidente.

## Actores

- **Colaborador** — el accidentado. Solo origina el reporte (escenario A); el llenado posterior recae en los roles operativos.
- **GHC — [[Hotel/Colaborador del Gerente del Hotel|Colaborador del Gerente del Hotel]]** — captura la información presencial. Origina el reporte en escenario B.
- **QA Inspector — [[QA Inspector|Inspector de zona]]** — complementa con seguimiento médico. Responsable final del cierre de la tarjeta.

---

## Escenario A — El colaborador reporta

Ocurre cuando el colaborador accidentado es quien detecta y reporta primero el incidente.

### 1. Reporte inicial

1. El **Colaborador** reporta el accidente desde la app.
2. Se genera la tarjeta de [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]] con número de reporte automático.
3. El **Colaborador** transita a **Gris — Accidentado** en el [[Semáforo del Colaborador]].
4. La señal llega **simultáneamente** al GHC y al QA Inspector de zona asignado.

### 2. Captura presencial (GHC)

5. El **GHC** acude físicamente al lugar del incidente.
6. Captura la información presencial en la tarjeta:
   - Ubicación exacta dentro de la propiedad.
   - Circunstancias del accidente.
   - Testigos.
   - Atención inmediata brindada.

### 3. Seguimiento médico (QA Inspector)

7. El **QA Inspector** complementa la tarjeta con la información de seguimiento:
   - Traslado al centro médico (si aplica, cuál).
   - Diagnóstico recibido.
   - Días de incapacidad.
   - Observaciones médicas.

### 4. Cierre

8. El **QA Inspector** cierra la tarjeta una vez que la información está completa.
9. Al recibir el alta médica, el colaborador transita de `Gris → Verde fuerte` en el [[Semáforo del Colaborador]].

---

## Escenario B — El GHC reporta

Ocurre cuando el [[Hotel/Colaborador del Gerente del Hotel|GHC]] detecta primero el incidente (el colaborador no puede reportar por sí mismo o el GHC lo ve primero).

### 1. Reporte inicial con información presencial

1. El **GHC** detecta el incidente y crea la tarjeta desde la app.
2. Se genera la tarjeta de [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]] con número de reporte automático.
3. El **Colaborador** transita a **Gris — Accidentado** en el [[Semáforo del Colaborador]].
4. El **GHC** captura directamente la información presencial:
   - Ubicación exacta dentro de la propiedad.
   - Circunstancias del accidente.
   - Testigos.
   - Atención inmediata brindada.
5. La señal llega al **QA Inspector** de zona asignado.

### 2. Seguimiento médico (QA Inspector)

6. El **QA Inspector** complementa la tarjeta con la información de seguimiento:
   - Traslado al centro médico (si aplica, cuál).
   - Diagnóstico recibido.
   - Días de incapacidad.
   - Observaciones médicas.

### 3. Cierre

7. El **QA Inspector** cierra la tarjeta una vez que la información está completa.
8. Al recibir el alta médica, el colaborador transita de `Gris → Verde fuerte` en el [[Semáforo del Colaborador]].

---

## Regla de protección

Mientras el colaborador esté en estado **Gris — Accidentado**, las inasistencias **no cuentan** para la regla de 3 inasistencias → [[Core/Módulos/Blacklist|Blacklist]] del [[Semáforo del Colaborador]]. El colaborador está fuera de la operación activa por causa médica.

---

## Relacionado

- [[Core/Módulos/Accidente Laboral/Accidente Laboral|Accidente Laboral]]
- [[Semáforo del Colaborador]]
- [[Hotel/Colaborador del Gerente del Hotel|Colaborador del Gerente del Hotel]]
- [[QA Inspector]]
- [[Colaborador]]
- [[Hotel/Hotel|Hotel]]
- [[Core/Módulos/Blacklist|Blacklist]]
