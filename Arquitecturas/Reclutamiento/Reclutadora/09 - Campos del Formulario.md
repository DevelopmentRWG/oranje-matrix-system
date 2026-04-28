---
tags:
  - arquitectura
  - rol/reclutadora
aliases:
  - Campos Formulario Reclutadora
---

# 3. CAMPOS DEL FORMULARIO — NUEVO COLABORADOR (FASE 1)

---

| Campo | Tipo de Input | Obligatorio | Validación | Descripción |
|---|---|---|---|---|
| Nombre completo | Text | SÍ | Mín. 3 caracteres, solo letras y espacios | Nombre legal del candidato |
| Documento de identidad | Text | SÍ | Único en el sistema, formato válido | Identificación oficial |
| Edad | Number | SÍ | Entre 18 y 65 años | Edad del candidato |
| Género | Select | SÍ | Masculino / Femenino / Otro | Género del candidato |
| Teléfono | Text | SÍ | Formato móvil válido (10 dígitos) | Contacto principal del candidato |
| Correo electrónico | Email | NO | Formato email válido | Contacto secundario del candidato |
| Domicilio | Text | SÍ | Mín. 10 caracteres | Dirección del candidato |
| Cédula (subir) | File | NO | PDF/JPG/PNG, máx. 5 MB | Documento escaneado |
| Zona | Select | SÍ | Debe seleccionar opción del catálogo | Zona geográfica de operación |
| Posición de interés | Select | SÍ | Debe seleccionar opción del catálogo | Puesto al que aspira el candidato |
| Modalidad preferida | Select | SÍ | Tiempo completo / Medio tiempo / Temporal / Según solicitud | Tipo de empleo deseado |
| Nivel de inglés | Select | SÍ | Básico / Intermedio / Avanzado / Conversacional | Dominio lingüístico |
| Disponibilidad | Select | SÍ | Inmediata / 1 semana / 2+ semanas | Cuándo puede iniciar labores |
| Experiencia previa | Textarea | NO | Máx. 500 caracteres | Historial laboral relevante |
