---
tags:
  - arquitectura
  - departamento/hotel
aliases:
  - Hotel Requirements By Module
---

# REQUIREMENTS BY MODULE — HOTEL DEPARTMENT

Grouping of the RFs defined in [[03 - Requirements Table|03 - Requirements Table]] according to the sidebar module they belong to.

---

## 📋 REQUISITIONS

| RF | Name | Role(s) | Priority |
|---|---|---|---|
| RF-H-01 | Create requisition | Supervisor | 🔴 High |
| RF-H-02 | Edit requisition draft | Supervisor | 🔴 High |
| RF-H-03 | Send requisition to authorization | Supervisor | 🔴 High |
| RF-H-04 | Delete draft / empty requisition | Supervisor / System | 🟡 Medium |
| RF-H-05 | Authorize requisition | Area Manager | 🔴 High |
| RF-H-06 | Reject requisition with remarks | Area Manager | 🔴 High |
| RF-H-07 | Delete requisition with positions | Area Manager | 🟡 Medium |
| RF-H-08 | Calculate Urgency Status Light upon authorization | System | 🔴 High |
| RF-H-09 | Assign Inspector automatically by zone | System | 🔴 High |
| RF-H-26 | Comment on the requisition file | General Manager | 🟢 Low |
| RF-H-27 | Escalate delayed requisition | General Manager | 🟡 Medium |

---

## 📅 SCHEDULE

| RF | Name | Role(s) | Priority |
|---|---|---|---|
| RF-H-10 | Reflect positions in Schedule upon authorization | System | 🔴 High |
| RF-H-12 | Edit weekly Schedule | Area Manager | 🔴 High |
| RF-H-13 | View Schedule | Supervisor / General Manager | 🔴 High |
| RF-H-19 | Suggest staff reinforcement | Supervisor | 🟢 Low |
| RF-H-22 | View global hotel Schedule | General Manager | 🟡 Medium |

---

## ⏱️ TIMESHEET

| RF | Name | Role(s) | Priority |
|---|---|---|---|
| RF-H-11 | Generate / Renew Timesheet QR | Area Manager | 🔴 High |
| RF-H-14 | Correct Timesheet punch | Area Manager | 🟡 Medium |
| RF-H-15 | View Timesheet | Supervisor / Area Manager / General Manager | 🔴 High |
| RF-H-16 | Calculate Compliance Indicator | System | 🔴 High |
| RF-H-23 | View global hotel Timesheet | General Manager | 🟡 Medium |

---

## 👥 MY STAFF

| RF | Name | Role(s) | Priority |
|---|---|---|---|
| RF-H-17 | Put collaborator on Stand-by (Pink) | Supervisor / Area Manager | 🔴 High |
| RF-H-18 | Report collaborator (Red) | Area Manager | 🔴 High |

---

## 🚨 WORKPLACE ACCIDENTS

| RF | Name | Role(s) | Priority |
|---|---|---|---|
| RF-H-20 | Report accident — Scenario A | Supervisor | 🔴 High |
| RF-H-21 | Report accident — Scenario B | Supervisor | 🔴 High |

---

## 👥 MY HOTEL TEAM *(General Manager)*

| RF | Name | Role(s) | Priority |
|---|---|---|---|
| RF-H-28 | Request report from Department Manager | General Manager | 🟢 Low |

---

## 📈 REPORTS *(General Manager)*

| RF | Name | Role(s) | Priority |
|---|---|---|---|
| RF-H-24 | Generate executive report | General Manager | 🟡 Medium |
| RF-H-25 | Send report to management | General Manager | 🟡 Medium |

---

## 📊 DASHBOARD

| RF | Name | Role(s) | Priority |
|---|---|---|---|
| — | Personal KPIs (by role) | All | 🔴 High |
| — | Global hotel KPIs | General Manager | 🟡 Medium |

---

## ⚙️ SYSTEM *(cross-cutting)*

| RF | Name | Role(s) | Priority |
|---|---|---|---|
| RF-H-08 | Automatic urgency calculation | System | 🔴 High |
| RF-H-09 | Inspector assignment by zone | System | 🔴 High |
| RF-H-10 | Reflection in Schedule | System | 🔴 High |
| RF-H-16 | Compliance Indicator calculation | System | 🔴 High |
| — | Automatic notifications | System | 🔴 High |
