---
tags:
  - arquitectura
  - rol/manager-general
aliases:
  - Responses System General Manager
---

# 7. SYSTEM RESPONSES — GENERAL MANAGER

---

| Event                                                 | System Response                                                                                                      |
| ----------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| GM consults global Schedule                           | Consolidated calendar view with drill-down by department · Coverage heatmap                                          |
| GM consults global Timesheet                          | Consolidated table with Compliance Indicator · Summary by department                                                |
| GM applies filters                                    | View updated in less than 2s                                                                                          |
| GM exports consolidated Schedule / Timesheet          | Generates downloadable PDF / CSV / Excel file                                                                        |
| GM comments on requisition file                       | Comment appears in the journal with author and date · Notifies the Department Manager                               |
| GM escalates delayed requisition                      | Notifies the Recruitment Manager · Changes indicator to "Escalated" · Stays in auditable log                       |
| GM requests report from Manager                       | Notifies the Manager with the request data · Appears in their pending inbox                                          |
| GM communicates with Manager / Supervisor             | Message sent · Push / email notification to the recipient                                                            |
| GM generates executive report                         | Preview with consolidated data according to selected template · Export / send / save buttons                       |
| GM exports report                                     | Downloadable file (CSV / PDF / Excel)                                                                                 |
| GM sends report to direction                          | Email / link sent · Stays in history with recipient, subject and status · Notifies the GM when read                |
| GM schedules recurring send                           | Configuration saved · System will send automatically according to frequency                                         |
| Quality Indicator drops to Red                        | Notifies the GM and the QA Manager · Alert visible on Dashboard                                                     |
| Timesheet Compliance Indicator drops to Red (consolidated) | Notifies the GM and the affected Department Manager                                                            |
| Hotel coverage drops <70%                             | Alert visible on Dashboard · Notifies the GM                                                                         |
| Serious workplace accident                            | Notifies the GM with case detail and assigned Inspector                                                             |
| Session started                                       | Redirects to global Dashboard with KPIs loaded                                                                        |
| Session expired                                       | Redirects to login                                                                                                   |
| GM attempts action without permission                 | Shows message: *"You do not have permission for this action"* · The button normally does not appear                 |
