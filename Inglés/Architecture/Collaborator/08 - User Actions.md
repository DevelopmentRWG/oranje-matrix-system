---
tags:
  - architecture
  - role/collaborator
aliases:
  - Collaborator User Actions
---

# 6. USER ACTIONS — COLLABORATOR

---

| Action                                                           | Result                                                                                                                                                                         |
| ---------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Complete sign-up — Phase 2 (RF-C-01)                            | System saves the collaborator's work data · Status light transitions to → White (pre-validation) · Notifies the Recruiter that a sign-up is pending review                    |
| Complete emergency data — Phase 3 (RF-C-02)                     | System saves emergency contact, blood type, and medical conditions · Data available for use in the event of a workplace accident                                               |
| Scan QR — Clock-in (RF-C-03)                                    | System records clock-in time · Creates or updates the Timesheet for that shift · Requires active Timesheet (Schedule + assignment) (RR-C-03)                                  |
| Scan QR — Lunch Out                                             | System records lunch departure time · Starts computing lunch time · Deduction applied per [[Collaborator Rules]]                                                               |
| Scan QR — Lunch In                                              | System records return from lunch · Closes lunch time computation · If lunch < 30 min, system applies a 30-min minimum                                                         |
| Scan QR — Break Out                                             | System records break departure time · Pauses gross hours computation                                                                                                           |
| Scan QR — Break In                                              | System records return from break · Resumes gross hours computation                                                                                                             |
| Scan QR — Clock-out (end of shift) (RF-C-03)                   | System records clock-out time · Calculates gross hours (Clock-out − Clock-in) · Applies lunch deduction · Calculates net hours · Updates collaborator's Timesheet              |
| Attempt to clock in without active Timesheet                    | System blocks; displays: *"You don't have an active shift. Contact your supervisor"* (RR-C-03)                                                                                 |
| Activate voluntary availability — Yellow (RF-C-04)             | Status light changes to Yellow · Collaborator becomes visible in the Pool as voluntarily available · No active Schedule or Timesheet until assigned                            |
| Deactivate availability — return to Strong Green               | Status returns to Strong Green · Collaborator no longer appears as voluntarily available in the Pool                                                                           |
| Report workplace accident (RF-C-05)                             | System creates workplace accident card · Collaborator status transitions to Gray (Injured) · Simultaneously notifies the Supervisor and Zone Inspector · Collaborator is protected from the 3-absences → Blacklist rule |
| View My Schedule (RF-C-06)                                      | Weekly view of assigned shifts: hotel, position, schedule, dates · Read-only                                                                                                   |
| View My Timesheet (RF-C-07)                                     | Weekly table: 6 punch columns, gross hours per shift, lunch deduction, net hours · Read-only                                                                                   |
| View My weekly Pay (RF-C-08)                                    | History of already-released payments (week, hotel, hours, amount paid, date); the current week appears as "In calculation" without an amount · Read-only (RR-C-05)             |
| View notifications (RF-C-09)                                    | List of notifications sorted by date: read and unread · Badge disappears upon opening                                                                                          |
| View My Profile and status light state (RF-C-10)               | View of all their data (Phase 1, 2, 3) + color and name of their current status light state · Can edit contact and emergency data with limits                                  |
| Edit phone or emergency data from My Profile                    | System saves the change · Re-validation not required for emergency data · Change recorded in the collaborator's journal                                                        |
| Cancel action in form                                           | Changes are not saved · Collaborator returns to the previous screen                                                                                                            |
