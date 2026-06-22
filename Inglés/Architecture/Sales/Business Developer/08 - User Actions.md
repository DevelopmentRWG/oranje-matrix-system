---
tags:
  - arquitectura
  - rol/business-developer
aliases:
  - Business Developer Actions
---

# 6. USER ACTIONS — BUSINESS DEVELOPER

---

| Action                                        | Result                                                                                  |
| --------------------------------------------- | --------------------------------------------------------------------------------------- |
| Identify prospect                             | Creates record in Gray status with minimum data · Appears in my Pipeline                |
| Create hotel profile (Light Blue)             | Completes data: name, email, phone, contact, need · Status moves to Light Blue          |
| Register cold visit                           | Documents visit (date, contact, result) · Logged in history                             |
| Register contact attempt                      | Documents call / email / visit · Logged in the timeline                                 |
| Prepare Personalized Proposal                 | Creates proposal (services, prices, conditions) in draft state                          |
| Edit proposal draft                           | Changes persist · State is maintained                                                   |
| Send proposal to hotel                        | Changes to "Sent" state · Prospect status moves to Green · Notifies the BD              |
| Advance to Yellow (hotel interest)            | Status change with reason and comment · Logged in the timeline                          |
| Create T&C Document                           | Starts document with mandatory fields (Pay/Bill/Overtime/Holidays/Calendar)             |
| Edit T&C draft                                | Changes persist                                                                         |
| Send T&C to the BDC for validation            | Notifies the BDC · Document remains pending validation                                  |
| Initiate negotiation (Pink)                   | Status changes to Pink · Notifies the BDC                                               |
| Mark rejection (Red)                          | Status moves to Red · Mandatory reason · Notifies the BDC                               |
| Reactivate from Red                           | Status returns to Light Blue · History keeps the rejection record                       |
| Mark stagnation (Brown)                       | Status moves to Brown · Notifies the BDC to unblock                                     |
| Duplicate proposal as template               | Creates new proposal with pre-loaded data                                               |
| Export proposal as PDF                        | Downloads PDF                                                                           |
| Plan route of the day                         | Selects prospects to visit · Generates an optimized route view                          |
| Register commercial contact (active client)   | Documents courtesy visit / follow-up · Logged in the client's history                   |
| Cancel action                                 | Changes are not saved                                                                   |
