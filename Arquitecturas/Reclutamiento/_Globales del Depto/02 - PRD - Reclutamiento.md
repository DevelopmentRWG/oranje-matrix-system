---
tags:
  - arquitectura
  - departamento/reclutamiento
aliases:
  - PRD del Depto Reclutamiento
---

# DOCUMENTO DE REQUISITOS DE PRODUCTO
## PRD – RECLUTAMIENTO

**Sistema de Gestión de Personal · Departamento de Reclutamiento**

---

| Campo | Contenido |
|---|---|
| **ID del PRD** | PRD-RECL-01 |
| **Historia de Usuario** | HU-RECL-01 |
| **Departamento** | Reclutamiento |
| **Funcionalidad** | Gestionar el ciclo completo de reclutamiento bajo modelo Self-Pick |
| **Actor Principal** | Reclutadora · Líder de Grupo de Reclutadoras |
| **Dispositivo** | Web – Desktop |
| **Estado** | En definición |
| **Versión** | 1.0 |

---

## Objetivo

Permitir al equipo de Reclutamiento captar, validar y habilitar colaboradores para integrarlos al Pool de Colaboradores, y cubrir las requisiciones autorizadas por los hoteles bajo un **modelo Self-Pick** donde Reclutadoras y Líderes de Grupo toman libremente las requisiciones de la bandeja según su capacidad.

---

## Alcance

**Incluye:**
- Recepción de requisiciones autorizadas por los hoteles.
- Toma libre de requisiciones por Reclutadoras y Líderes de Grupo (Self-Pick).
- Búsqueda de candidatos en el Pool de Colaboradores.
- Alta de nuevos colaboradores en 3 fases (entrevista, app, datos de emergencia).
- Validación de colaboradores tras alta en app.
- Asignación de colaboradores a requisiciones y al Schedule del hotel.
- Consulta y gestión de Blacklist.
- Supervisión de equipo (Líder de Grupo y Manager).
- Reportes de cobertura y desempeño.

**Fuera del alcance:**
- Inspección operativa en sitio (módulo Inspección).
- Auditoría de calidad (módulo QA).
- Ciclo comercial pre-cliente (módulo Onboarding-Hotel).

---

## Flujo General

**Hotel autoriza requisición → Llega a Bandeja → Reclutadora/Líder toma → Busca en Pool → Asigna → Cubre**

---

## Actores

| Actor                          | Tipo           | Responsabilidad principal                        |
| ------------------------------ | -------------- | ------------------------------------------------ |
| Reclutadora                    | Operativo      | Toma requisiciones y las cubre con colaboradores |
| Líder de Grupo de Reclutadoras | Intermedio     | Toma + supervisa al grupo                        |
| Manager de Reclutamiento       | Supervisor     | Gestión del depto + casos especiales             |
| Sistema                        | Automatización | Cálculos automáticos, notificaciones, journals   |
| Administrador                  | Configuración  | Usuarios, catálogos, permisos                    |
