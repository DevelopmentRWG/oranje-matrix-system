---
tags:
  - arquitectura
  - rol/business-developer
  - caso-de-uso
aliases:
  - CU RF-V-01
---

# 🪪 ID: RF-V-01
🏷️ **Name:** Identify prospect (Gray)

**Story:**
The BD detects a hotel in their territory that could become a client. They create an initial record in the system in **Gray** status, capturing minimal data (name, city, zone, optional geolocation). The prospect stays visible in their Pipeline awaiting the first contact.

**Acceptance criteria:**
The BD can only identify prospects in their assigned territory. Mandatory data: name, city, zone. Automatic geolocation if done from mobile. Automatically assigned to the BD who creates it. Appears in the Pipeline in less than 2s.

**Documentation:**
- PRD: PRD-VENTAS-02 Business Developer
- Flow: Prospect identification
- Prototype: (Figma link)

**Flow:**
`Sidebar → My Territory or Pipeline → Click "Identify prospect"` → MANUAL → `Fill in name, city, zone` → AUTOMATICO from mobile → `Capture geolocation` → MANUAL → `Optional lead origin + initial notes` → `Confirm` → AUTOMATICO → `Creates record in Gray + Assigns to the BD + Appears in Pipeline + Timeline started`
