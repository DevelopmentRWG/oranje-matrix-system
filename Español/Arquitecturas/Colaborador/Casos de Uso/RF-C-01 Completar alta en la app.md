---
tags:
  - arquitectura
  - rol/colaborador
  - caso-de-uso
aliases:
  - CU RF-C-01
---

# 🪪 ID: RF-C-01
🏷️ **Nombre:** Completar alta en la app — Fase 2

**Historia:**
El Colaborador recibe acceso a la app después de que la [[Reclutadora]] captura sus datos iniciales (Fase 1). Ahora debe completar su perfil desde la app ingresando sus datos laborales: posición deseada, nivel de inglés, nivel de experiencia, tipo de transporte y modalidad de contratación. De forma opcional puede ingresar su SSN y/o ITIN; si lo hace, se habilita la carga del documento de SSN/ITIN (foto o PDF de la tarjeta, también opcional pero recomendada). Si no proporciona ni SSN ni ITIN, el sistema le muestra un aviso informándole que se aplicará una retención del 16% sobre su pago (reembolsable) y le permite continuar sin bloquearlo. Al enviar el formulario, el sistema guarda los datos y notifica a la Reclutadora que hay un alta pendiente de revisión. El colaborador queda en espera de validación.

**Criterios de aceptación:**
SSN, ITIN y el documento de SSN/ITIN son **opcionales**. Si el colaborador no proporciona ni SSN ni ITIN, el sistema muestra un aviso: *"Sin SSN ni ITIN se aplicará una retención del 16% sobre tu pago (reembolsable) — ver [[Deducciones]]"*; el envío **no se bloquea**. Si proporciona ITIN, no se aplica la retención (ITIN es un TaxID). Si ingresa SSN o ITIN: SSN válido: formato XXX-XX-XXXX; ITIN válido: formato 9XX-XX-XXXX; ambos se enmascaran tras el ingreso y se almacenan cifrados (RNF-C-03). Si ingresa SSN o ITIN, el campo de carga de documento se habilita (opcional · recomendado); si se carga, debe ser JPG, PNG o PDF con tamaño máximo de 10 MB. Posición, nivel de inglés, nivel de experiencia, tipo de transporte y modalidad son los campos **obligatorios** de catálogo; sin cualquiera de ellos, el sistema bloquea el envío y muestra mensaje de error junto al campo inválido. Al enviar, el estado del colaborador transita a → **Blanco (Pre-asignación)**. La Reclutadora recibe notificación de alta pendiente. El colaborador ve confirmación: *"Tu alta fue enviada. Te avisaremos cuando sea revisada"*.

**Documentación:**
- PRD: PRD-COLAB-01
- Flow: Flujo de Reclutamiento — Alta del Colaborador
- Prototipo: (link de Figma)

**Flujo:**
`App → Login → Dashboard` → MANUAL → `Sección Alta → Fase 2` → `Ingresa SSN (opcional, enmascarado) y/o ITIN (opcional, enmascarado)` → Si ingresa SSN/ITIN → `Se habilita campo Adjuntar documento de SSN/ITIN (JPG/PNG/PDF, máx. 10 MB — opcional · recomendado)` / Si no ingresa SSN ni ITIN → `Sistema muestra aviso: "Sin SSN ni ITIN se aplicará una retención del 16% sobre tu pago (reembolsable)" · El colaborador puede continuar` → `Selecciona Posición (catálogo · obligatorio)` → `Selecciona Nivel de inglés (catálogo · obligatorio)` → `Selecciona Nivel de experiencia (catálogo · obligatorio)` → `Selecciona Tipo de transporte (catálogo · obligatorio)` → `Selecciona Modalidad (catálogo · obligatorio)` → `Enviar` → AUTOMATICO → Si campos obligatorios válidos → `Estado → Blanco · SSN/ITIN y documento cifrados en almacenamiento (si fueron proporcionados) · Retención 16% activada automáticamente si no hay SSN ni ITIN (ver [[Deducciones]]) · Notificación push a la Reclutadora: "Alta pendiente de revisión" · Confirmación al colaborador: "Tu alta fue enviada"` / Si campo obligatorio inválido o faltante → `Bloquea envío · Muestra mensaje de error junto al campo inválido`
