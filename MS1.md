# Requirements Identification Submission (RIS) - Phase 1
by: [Arnel Imperial](https://github.com/imperionite)

## RIS Component Links

- [Use Case Diagram](https://drive.google.com/file/d/1MYsYfS5Aj8RFiYwGMJpwl76zFq1ztPzi/view?usp=sharing)
- [Wireframe](https://drive.google.com/file/d/1VLY7Pq6Ki4HjkVK_W3DYCvGpOmF6sWig/view?usp=sharing)
- [Project Plan Timeline](https://tinyurl.com/37zmrv79)
- [MotorPH Requirements Worksheet](https://docs.google.com/spreadsheets/d/16WVjM2qbPiA4lTBkNgSnAEH1urHDoyUGpCUNWzILGxU/edit?usp=sharing)

## Limitations and Delimitations

### Limitations

1. **Scope of Features**: 
   - The project focuses only on the basic functionalities required for Phase 1. Advanced features, such as role-based access control, tax computation, or real-time integrations with external systems, are not included at this stage.
   - The salary calculation uses generic deductions without specific consideration for varying tax brackets or benefits.

2. **Data Accuracy**: 
   - The employee data and calculations depend on the accuracy of the input data. Incorrect or incomplete data may result in calculation errors.
   - No real-time validation for employee working hours or anomalies like overtime or underperformance is implemented.

3. **Database and Scalability**: 
   - The application uses H2 as a development database, which is suitable for testing purposes but may not support scalability for larger data sets.
   - Data persistence beyond Phase 1 is limited and will require migration to a production-ready database in future phases.

4. **Testing Environment**: 
   - Testing is conducted in a controlled development environment and may not cover edge cases encountered in a production setting.

5. **Limited User Roles**: 
   - The project assumes a single user type (User) interacting with the system, as no role-based access control is implemented.

---

### Delimitations

1. **Phase-Specific Objectives**:
   - The project is strictly focused on achieving the deliverables outlined for Phase 1, including employee data display, work hours calculation, gross salary computation, and net salary computation.

2. **Geographical Context**:
   - The system is designed with MotorPH in mind, adhering to generic Philippine payroll practices. Customization for other regions or companies is outside the current scope.

3. **Excluded Features**:
   - Advanced functionalities such as real-time analytics, tax integration, automated payroll distribution, and employee performance tracking are reserved for future phases.
   - Role-based security features and detailed access control mechanisms will be implemented in subsequent phases if required.

4. **Development Team Size**:
   - The project is developed by a single developer, limiting the scope of simultaneous feature implementation and testing.

5. **Technology Stack**:
   - The project uses Java with Spring Boot as the primary framework. No other frameworks or third-party libraries outside the chosen stack are considered.


## Requirement Analysis

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
- **Week 4**: System visualization (UI wireframes, use case diagram).
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
- Integration with an employee attendance system.
- Support for different tax and deduction schemes.
- UI/UX improvements for better employee self-service features.

## Effort Estimation

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
- Develop **wireframes/mockups**.
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

## Use Case

### Overview
This document describes the **Use Case Diagram** for Phase 1 of the **MotorPH Payroll System**. The system allows users to view employee details, log work hours, and calculate salaries.

#### Actor
**User**  
- Interacts with the system to retrieve employee details.  
- Logs work hours.  
- Triggers payroll calculations.  

##### Use Cases

###### View Employee Details
**Actor:** User  
**Description:** Retrieves and displays employee details such as employee number, name, and birthday.  
**Preconditions:** Employee records exist in the system.  
**Postconditions:** Employee details are displayed successfully.  

###### Log Work Hours
**Actor:** User  
**Description:** Users log their work hours by recording clock-in and clock-out times.  
**Preconditions:** The user is recognized by the system.  
**Postconditions:** Work hours are stored for payroll computation.  

###### Calculate Weekly Work Hours
**Actor:** User  
**Description:** Computes the total number of hours worked in a week based on recorded log-in and log-out times.  
**Preconditions:** Work hour records must be available.  
**Postconditions:** The system displays the calculated weekly work hours.  

###### Compute Gross Salary
**Actor:** User  
**Description:** Calculates the gross weekly salary based on the total hours worked and the predefined pay rate.  
**Preconditions:** Work hour records are available.  
**Postconditions:** The system displays the gross salary.  

###### Compute Net Salary
**Actor:** User  
**Description:** Computes the net weekly salary after applying generic deductions.  
**Preconditions:** Gross salary calculation must be completed.  
**Postconditions:** The system displays the net salary after deductions.  

##### Use Case Diagram
Refer to this [link](https://drive.google.com/file/d/1MYsYfS5Aj8RFiYwGMJpwl76zFq1ztPzi/view?usp=sharing) for the use case diagram representation of the project.


## Wireframe

### Overview
This document provides a detailed explanation of the wireframe design for the **Employee Salary Management System**. The wireframe showcases the visual layout and interaction flow of the application, focusing on Phase 1 requirements, which include presenting employee information and calculating salaries.

#### Wireframe Overview
The wireframe consists of two main sections:
1. **Employee Information**: Displays basic employee details.
2. **Salary Calculator**: Allows the user to compute an employee's gross salary, deductions, and net salary based on hours worked.

##### Key Sections and Description

###### **1. Header**
- **Title**: "Employee Salary Management System"
  - Positioned at the top of the interface.
  - Clearly indicates the purpose of the application.
  - Provides a professional and user-friendly introduction to the system.

###### **2. Employee Information Section**
- **Purpose**: Displays a list of employees and their details for easy reference.
- **Content**:
  - **Column Headers**:
    - **Employee Number**: Displays unique IDs for employees (e.g., EMP001, EMP002).
    - **Name**: Shows the full name of each employee (e.g., John Doe, Jane Smith).
    - **Birthday**: Displays the date of birth in `YYYY-MM-DD` format (e.g., 1990-05-15).
  - **Data Table**: Presents employee details in a tabular format for clear visibility.
- **Position**: Centrally aligned in the upper half of the wireframe.
- **Interaction**: Read-only; no user input is required.

###### **3. Salary Calculator Section**
- **Purpose**: Provides a simple and intuitive way to calculate salaries.
- **Content**:
  - **Dropdown Menu**: 
    - Labeled **"Select Employee"**.
    - Allows users to choose an employee from the list.
  - **Input Field for Hours Worked**: 
    - Accepts numeric input for the total hours worked by the selected employee.
  - **Calculate Salary Button**:
    - Triggers the computation of gross salary, deductions, and net salary based on the entered hours.
  - **Result Display**:
    - **Gross Salary**: Shows the calculated gross salary in currency format (e.g., `$0.00`).
    - **Deductions**: Displays total deductions applied (e.g., `$0.00`).
    - **Net Salary**: Shows the final computed salary after deductions (e.g., `$0.00`).
- **Position**: Centrally aligned in the lower half of the wireframe for easy access.

##### Layout and Interaction
- **Layout Design**: The wireframe uses a clean and simple layout, dividing the interface into two distinct sections for better usability.
- **User Interaction Flow**:
  1. User views the employee list in the **Employee Information** section.
  2. User selects an employee and enters hours worked in the **Salary Calculator** section.
  3. User clicks the **Calculate Salary** button to compute and display the results.

##### Accessibility and Usability
- **Accessibility**: The design is clean, with sufficient spacing between elements to ensure readability.
- **Usability**:
  - Simple navigation and interaction.
  - Minimal user input required to complete calculations.

##### Generalization
This wireframe provides a foundational layout for the **Employee Salary Management System**, ensuring the application is user-friendly and fulfills the Phase 1 requirements. It effectively displays employee details and simplifies salary computation through an intuitive interface. Refer to this [link](https://drive.google.com/file/d/1VLY7Pq6Ki4HjkVK_W3DYCvGpOmF6sWig/view?usp=sharing) for the visual representation of the project's wireframe.


## Project Plan

### Overview

The **MotorPH Payroll System** aims to streamline payroll processes by managing products, employee details, and salaries. This document outlines the project plan for **Phase 1**, focusing on initial requirements and deliverables.

#### Objectives

- **Visualization**: Develop a visual representation of the application interface.
- **Employee Information Presentation**: Display employee details, including employee number, name, and birthday.
- **Work Hours Calculation**: Compute the total number of hours an employee works in a week.
- **Gross Salary Calculation**: Determine the gross weekly salary based on hours worked.
- **Net Salary Calculation**: Calculate the net weekly salary after applying standard deductions.

##### Timeline

| **Week** | **Milestone**                      | **Description**                                                                 |
|----------|------------------------------------|---------------------------------------------------------------------------------|
| 1-3      | Project Initiation                 | Gather requirements, define scope, and set up the development environment.      |
| 4        | Visualization                      | Create wireframes and mockups of the application interface.                     |
| 5        | Employee Details Presentation      | Implement functionality to display employee information.                        |
| 6        | Hours Worked Calculation           | Develop feature to calculate weekly work hours.                                 |
| 7        | Gross Salary Calculation           | Implement computation of gross weekly salary.                                   |
| 8        | Net Salary Calculation             | Develop feature to calculate net weekly salary after deductions.                |
| 9-10     | Testing and Revision               | Conduct thorough testing and make necessary revisions.                          |
| 11       | Final Submission                   | Prepare and submit the final deliverable.                                       |

##### Deliverables

- **Wireframes and Mockups**: Visual designs of the application interface.
- **Functional Modules**:
  - Employee Information Display
  - Work Hours Calculation
  - Gross Salary Calculation
  - Net Salary Calculation
- **Testing Documentation**: Test cases, results, and bug fixes.
- **Final Application**: Fully functional application meeting Phase 1 requirements.

##### Tools and Technologies

- **Programming Language**: Java
- **Framework**: Spring Boot
- **Database**: MySQL
- **Version Control**: Git
- **Project Management**: [ClickUp](https://tinyurl.com/37zmrv79)

##### Risk Management

- **Scope Creep**: Maintain clear requirements and manage changes through a formal change control process.
- **Time Constraints**: Adhere to the timeline and allocate buffer time for unforeseen delays.
- **Technical Challenges**: Regularly consult documentation and seek assistance from the developer community as needed.

#### Generalization

This project plan outlines the roadmap for developing the **MotorPH Payroll System Phase 1**. By following this plan, we aim to deliver a functional and user-friendly payroll system within the stipulated timeframe.

---

### Conclusion

The **MotorPH Payroll System Phase 1** project aims to lay the groundwork for a robust, end-to-end payroll management system. Through careful planning and phased implementation, this project addresses the core requirements of displaying employee details, calculating work hours, and determining gross and net salaries. The systematic approach outlined in this project plan ensures that deliverables are met within the given timeline while maintaining quality and usability.

#### Final Thought

Building the foundation of the payroll system in Phase 1 is not just about fulfilling technical requirements but also about understanding user needs and delivering a reliable and user-friendly solution. This phase sets the tone for future enhancements and expansions, ensuring scalability and efficiency for MotorPH.

##### Key Takeaways

- **Phased Development Approach**: Breaking down the requirements into smaller phases allows for iterative development, ensuring better focus and quality control.
- **User-Centric Design**: Designing wireframes and implementing intuitive features ensures that the application is accessible and meets user expectations.
- **Foundation for Scalability**: By addressing the core functionalities now, the project creates a strong base for future phases, where additional features and role-based controls can be introduced.
- **Time Management**: Strict adherence to the project timeline will be critical for timely delivery and maintaining alignment with business goals.
- **Future Opportunities**: This phase provides valuable insights into system requirements, user behavior, and technical considerations, paving the way for an improved and comprehensive payroll solution in subsequent phases.

By completing this phase successfully, MotorPH will take a significant step toward streamlining payroll processes and improving operational efficiency.


### Author

[Arnel Imperial](https://github.com/imperionite)





