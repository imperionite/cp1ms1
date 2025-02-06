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

## Technology Stack
- **Backend**: Spring Boot (Java 17), Maven
- **Database**: PostgreSQL / MySQL (TBD based on scalability needs)
- **Security**: Spring Security with JWT Authentication
- **Version Control**: GitHub for source code management

#### Future Considerations
- Integration with an employee attendance system (e.g., biometric or RFID-based logging).
- Support for different tax and deduction schemes.
- UI/UX improvements for better employee self-service features.
