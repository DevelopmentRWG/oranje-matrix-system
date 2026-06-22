---
tags:
  - arquitectura
  - rol/reclutadora
aliases:
  - Recruiter Form Fields
---

# 3. FORM FIELDS — NEW COLLABORATOR (PHASE 1)

---

| Field                  | Input Type    | Required    | Validation                                                  | Description                       |
| ---------------------- | ------------- | ----------- | ----------------------------------------------------------- | --------------------------------- |
| Full name              | Text          | YES         | Min. 3 characters, only letters and spaces                  | Candidate's legal name            |
| Date of birth          | Date          | YES         | Valid date; the collaborator must be of legal age           | Candidate's date of birth         |
| Age (calculated)       | —             | Auto        | Calculated by the system from the date of birth             | Age shown automatically; not captured |
| Gender                 | Select        | YES         | Male / Female / Other                                       | Candidate's gender                |
| Phone                  | Text          | YES         | Valid mobile format (10 digits)                            | Candidate's main contact          |
| Email                  | Email         | NO          | Valid email format                                          | Candidate's secondary contact     |
| Address                | Text          | YES         | Min. 10 characters                                          | Candidate's address               |
| Zone                   | Select        | YES         | Must select an option from the catalog                      | Geographic operating zone         |
| Position of interest   | Select        | YES         | Must select an option from the catalog                      | Position the candidate aspires to |
| Preferred modality     | Select        | YES         | Full time / Part time / Temporary / On request              | Desired employment type           |
| English level          | Select        | YES         | Basic / Intermediate / Advanced / Conversational            | Language proficiency              |
| Availability           | Select        | YES         | Immediate / 1 week / 2+ weeks                               | When they can start work          |
| Previous experience    | Textarea      | NO          | Max. 500 characters                                         | Relevant work history             |
