# Requirements Identification Submission (RIS)

## Links to RIS Components

- [Use Case Diagram](https://drive.google.com/file/d/1MYsYfS5Aj8RFiYwGMJpwl76zFq1ztPzi/view?usp=sharing)
- [Wireframe](https://drive.google.com/file/d/1VLY7Pq6Ki4HjkVK_W3DYCvGpOmF6sWig/view?usp=sharing)
- [Project Plan Timeline](https://tinyurl.com/37zmrv79)
- [MotorPH Requirements Worksheet](https://docs.google.com/spreadsheets/d/16WVjM2qbPiA4lTBkNgSnAEH1urHDoyUGpCUNWzILGxU/edit?usp=sharing)

## MotorPH Payroll System - Phase 1 Requirement Analysis

### Overview
MotorPH is developing an end-to-end payroll system to manage employee details, work hours, and salary calculations. The project will be built in phases, expanding capabilities over time. This document outlines the requirements for **Phase 1**, which focuses on basic employee management and payroll calculations.

### Objectives
- Design and visualize the application structure.
- Develop a Spring Boot-based backend to manage employee details.
- Implement functionality to calculate work hours, gross salary, and net salary.
- Ensure data accuracy and basic security measures.

#### Functional Requirements

##### Employee Information Management
- Store and retrieve employee details in the following format:
  - Employee Number
  - Employee Name
  - Birthday
- Develop an API endpoint to fetch employee details.

##### Work Hours Calculation
- Record and process employee log-in and log-out times.
- Calculate the total number of hours worked in a week.
- Handle multiple log-in/log-out records per day.

##### Gross Salary Calculation
- Compute gross weekly salary based on the total hours worked.
- Support different hourly rates for employees.
- Define a standard overtime calculation method (if applicable).

##### Net Salary Calculation
- Apply generic deductions (e.g., tax, benefits, other withholdings).
- Compute net salary after deductions.
- Ensure accurate calculations based on predefined rules.

#### Non-Functional Requirements

##### Performance
- The system should handle a reasonable number of employees efficiently.
- API responses should be optimized for quick retrieval of employee records and salary calculations.

##### Security
- Employee data should be protected from unauthorized access.
- API endpoints should have JWT-based authentication.

##### Scalability
- The system should be designed to accommodate future phases, including more complex payroll rules and additional employee data fields.

#### Deliverables
- **Week 4**: System visualization (UI wireframes, architecture diagrams, API documentation).
- **Week 5**: Working code for employee information display.
- **Week 6**: Implementation of work hours calculation.
- **Week 7**: Gross salary computation logic.
- **Week 8**: Net salary computation with deductions.
- **Week 9-10**: Testing and revisions.
- **Week 11**: Final submission.

#### Technology Stack
- **Backend**: Spring Boot (Java 17), Maven
- **Database**: PostgreSQL / MySQL (TBD based on scalability needs)
- **Security**: Spring Security with JWT Authentication
- **Version Control**: GitHub for source code management

#### Future Considerations
- Integration with an employee attendance system (e.g., biometric or RFID-based logging).
- Support for different tax and deduction schemes.
- UI/UX improvements for better employee self-service features.

## Effort Estimation for MotorPH Payroll System (Phase 1)

### Overview
This document provides an estimated effort required to develop Phase 1 of the MotorPH Payroll System. The estimation is based on a single developer handling the project end-to-end, covering design, development, testing, and documentation.

#### Assumptions
- The project follows an **iterative development approach**.
- Development is done using **Spring Boot (Java-based framework)**.
- No external team members; all tasks are handled by the sole developer.
- **40-hour workweek** is assumed for effort calculations.
- Complexity is **moderate**, considering CRUD operations, calculations, and database interactions.

##### Effort Breakdown

###### Visualization of Requirements (Week 4)
**Estimated Effort: 8-12 hours**  
- Research payroll system designs and UI best practices.
- Create a high-level **system architecture** and **data flow diagram**.
- Develop **wireframes/mockups** using Figma, Draw.io, or Balsamiq.
- Document requirements and refine based on feedback.

###### Employee Details Presentation (Week 5)
**Estimated Effort: 15-20 hours**  
- Design and implement an **Employee model** (Spring Boot entity).
- Set up **database schema** (e.g., MySQL or PostgreSQL).
- Develop REST API for **retrieving employee details**.
- Implement a **frontend or API testing tool** for viewing data.
- Perform initial unit testing.

###### Work Hours Calculation (Week 6)
**Estimated Effort: 18-22 hours**  
- Design logic for **clock-in and clock-out records**.
- Develop API endpoint to **store and retrieve attendance data**.
- Implement calculation logic to compute **weekly work hours**.
- Unit test work hour computations.

###### Gross Wage Calculation (Week 7)
**Estimated Effort: 15-18 hours**  
- Define **pay rate logic** for employees.
- Implement a calculation method for **weekly gross salary**.
- Integrate this functionality into the API.
- Write unit and integration tests.

###### Net Wage Calculation (Week 8)
**Estimated Effort: 15-18 hours**  
- Implement **deductions logic** (e.g., taxes, benefits).
- Integrate net salary computation into the existing payroll calculation.
- Develop API response to return **net salary**.
- Conduct initial validation testing.

###### Testing and Revision (Weeks 9-10)
**Estimated Effort: 20-25 hours**  
- Perform unit testing using **JUnit and Mockito**.
- Conduct **manual API testing** using Postman or Swagger UI.
- Fix bugs, optimize performance, and refine code.
- Review system usability and security.
- Document API endpoints and usage.

###### Final Submission (Week 11)
**Estimated Effort: 8-12 hours**  
- Prepare final **documentation** and **README.md** for GitHub.
- Conduct a final **end-to-end test**.
- Deploy or package the application for review.
- Submit the project.

##### Total Estimated Effort
**99 - 127 hours (~2.5 - 3.5 weeks of full-time work)**  
Since this project is being developed part-time over **11 weeks**, the workload is spread out to maintain steady progress.

##### Risks and Considerations
- **Unexpected technical challenges** (e.g., database issues, API bugs).
- **Requirement changes** or scope creep in later phases.
- **Learning curve** for advanced payroll calculations in later phases.
- **Time constraints** with academic workload or external factors.

#### Generalization
This effort estimation provides a **realistic roadmap** for a single developer to complete **Phase 1** of the MotorPH Payroll System within the allocated timeframe. Regular progress tracking and iterative development will ensure timely completion.

