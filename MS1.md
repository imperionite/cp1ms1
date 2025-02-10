<a name="intro"></a>

# Requirements Identification Submission (RIS) - Phase 1
by: [Arnel Imperial](https://github.com/imperionite)

MotorPH is a fictional company aiming to develop a robust end-to-end payroll system to efficiently manage employee details, working hours, salary computations, and associated payroll processes. The goal is to create the payroll system incrementally, adding features in distinct phases.

Phase 1 of the project focuses on establishing the fundamental functionality of the payroll system, which includes presenting basic employee information, calculating hours worked, and determining salary based on working hours and basic deductions. This phase sets the foundation for future enhancements and will be developed using a Java-based framework, specifically Spring Boot.

## 🧬 Table of Contents

1. [ Introduction ](#intro)
2. [ RIS Components ](#ris)
3. [ Requirement Analysis ](#ra)
4. [ Effort Estimation ](#ee)
5. [ Use Case ](#uc)
6. [ Wireframe ](#wireframe)
7. [ Project Plan ](#pp)
8. [ Limitations ](#l)
9. [ Delimitations ](#d)
10. [ Project Continuation & MS 2 Foundation ](#ms2)
11. [ Conclusion ](#conclusion)

<a name="ris"></a>

## 📌 RIS Component Links

- [Use Case Diagram](https://drive.google.com/file/d/1MYsYfS5Aj8RFiYwGMJpwl76zFq1ztPzi/view?usp=sharing)
- [Wireframe](https://drive.google.com/file/d/1VLY7Pq6Ki4HjkVK_W3DYCvGpOmF6sWig/view?usp=sharing)
- [Project Plan Timeline](https://tinyurl.com/37zmrv79)
- [MotorPH Requirements Worksheet](https://docs.google.com/spreadsheets/d/16WVjM2qbPiA4lTBkNgSnAEH1urHDoyUGpCUNWzILGxU/edit?usp=sharing)

<a name="ra"></a>

## 📌 Requirement Analysis

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
Non-functional requirements are considered based on the developers' preferences, but only the aspects strictly stated in the Phase 1 requirements are implemented. In fact, non-functional requirements are not explicitly mentioned in the Phase 1 task.

##### Performance
- The system should handle a reasonable number of employees efficiently.
- API responses should be optimized for quick retrieval of employee records and salary calculations.

##### Security
- Employee data should be protected from unauthorized access.
- API endpoints should have basic JWT-based authentication.
- Role-based Access Control (RBAC) was not mentioned or emphasized in Phase 1 initial requirements, so it will not be implemented in this project.

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
- **Database**: MySQL
- **Security**: Spring Security with JWT Authentication
- **Version Control**: GitHub for source code management

#### Future Considerations
- Integration with an employee attendance system.
- Support for different tax and deduction schemes.
- UI/UX improvements for better employee self-service features.

<a name="ee"></a>

## 📌 Effort Estimation

### Overview
This document provides an estimated effort required to develop Phase 1 of the MotorPH Payroll System. The estimation is based on a single developer handling the project end-to-end, covering design, development, testing, and documentation.

#### Assumptions
- The project follows an **iterative development approach**.
- Development is done using **Spring Boot (Java-based framework)**.
- No external team members; all tasks are handled by the sole developer.
- **40-hour workweek** is assumed for effort calculations.
- Complexity is **moderate**, considering CRUD operations, calculations, and database interactions.

##### Main Tasks

1. **Conduct Needs Analysis (Requirements Gathering)**
   - Identify all stakeholders' needs within MotorPH regarding their desired features in a custom payroll system.

2. **Design Database Schema for Payroll Data Storage**
   - Create tables for storing employee details, work hours, salary rates, deductions.

3. **Implement Employee Details Presentation**
   - Develop code to display employee information such as number, name, birthday.

4. **Develop Hours Worked Calculation Logic**
    – Write algorithms to accurately calculate weekly work hours based on attendance records.

5.**Gross Salary Calculation Integration**
     — Modify calculation logic to retrieve necessary data from the database like hourly wage rates

6. **Net Salary Calculation After Deductions**
     — Apply generic deductions using stored deduction rules from the database

7. **Testing & Revision**
      — Conduct thorough testing of all calculations & integrations; revise code as needed

8. **Compliance & Security Measures Implementation_
       — Implement measures ensuring legal compliance & safeguarding sensitive employee data 

9. **User-Friendly Interface Development**
        – Design intuitive UI/UX allowing easy navigation by both administrators & employees accessing pay stubs or updating personal info 

10. **Backup Strategy Preparation**
        – Plan regular backups of critical payroll data against potential loss or corruption 

12. **Documentation of System Processes**
        – Maintain detailed documentation outlining each step involved in using & maintaining the new system 

##### Knowledge Needed
To accomplish these tasks effectively:
- Familiarity with database design principles.
- Understanding of payroll calculation logic.
- Knowledge of UI/UX design principles.
- Awareness of compliance regulations affecting payroll processing.
- Proficiency in programming languages suitable for web applications (e.g., Java or Python).
- Experience with security measures like encryption and access controls.

##### Additional Help Needed
Additional resources that would be beneficial include:
1. Technical documentation and guides on database management systems (DBMS) like MySQL or PostgreSQL.
2. Mentorship from experienced developers familiar with similar projects.
3. Collaboration tools such as Slack or Trello to manage tasks efficiently across teams.
4. Testing frameworks like JUnit for comprehensive unit testing.
5.Integration APIs documentation if integrating with existing HR systems is required 
6.Security audits by cybersecurity experts to ensure compliance and protect sensitive data 
7.User interface templates that can be customized according to MotorPH’s branding guidelines 

##### Estimated Time per Task
Here are estimated times based on complexity and assuming moderate experience:

1.Conduct Needs Analysis: 8–12 hours  
2.Design Database Schema: 10–15 hours  
3.Employee Details Presentation: 6–10 hours  
4.Hours Worked Calculation Logic: 8–12 hours  
5.Gross Salary Calculation Integration: 10–15 hours  
6.Net Salary Calculation After Deductions: 12–18 hours  
7.Testing & Revision: 20–30 hours  
8.Integration Planning: 15–25 hours   
9.Compliance Measures Implementation:20—30 hours   
10.User-Friendly Interface Development: 20—30 hours   
11.Backup Strategy Preparation: 5—10 hours    
12.Documentation Process: 8—15 hours   

##### Estimated Completion

To determine the number of weeks required to complete my outputs for Phase 1 of the MotorPH Payroll System, I need to consider the estimated total hours of work and the expected weekly time commitment of 7.5 hours per week. Based on the complexity of the project, the development process involves multiple stages, including visualization, employee information display, work hours calculation, payroll computation, and system testing. If I estimate that the entire project will take approximately 75 hours to complete, dividing this by the 7.5-hour weekly commitment results in 10 weeks of work. This aligns closely with the given 11-week timeline, allowing for some flexibility in testing, refinements, and mentoring sessions. By effectively managing my time and following a structured approach, I can ensure that all Phase 1 requirements are met within the expected timeframe while maintaining high-quality output.


<a name="uc"></a>

## 📌 Use Case

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


<a name="wireframe"></a>

## 📌 Wireframe

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


<a name="pp"></a>

## 📌 Project Plan

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


<a name="l"></a>

## 📌 Limitations

- **Single Developer**: As the sole developer on this project, all tasks including system design, coding, testing, and debugging will be handled by one person. This may lead to limited bandwidth for tackling issues that arise during development, possibly impacting the speed and efficiency of completion.

- **Database Constraints**: The MySQL database will be used to store employee data, including employee details and work hours, and will run in a Docker container. The database setup is limited to Phase 1 requirements and will not include features such as: data analytics, reporting, integration with external systems, stored procedures, triggers or scheduled tasks.

- **Time Constraints**: With an 11-week timeframe, the focus will be on ensuring that the core functionality of employee information presentation, work hour and salary calculations is achieved. Time will not be allocated to expanding the system or addressing features not specified in Phase 1.

- **Testing Limitations**: Testing will be concentrated on validating the functionality of employee data presentation, work hour calculation, and salary computation. System-wide testing, user acceptance testing, load testing, stress testing, performance optimization, or security testing will not be performed in this phase.

- **Optional Features**: Any features that are not explicitly stated in the Phase 1 requirements will be considered optional elements. Their implementation will depend on time availability after fulfilling all mandatory requirements and will not be prioritized. Implementation of optional features will be at the discretion of the developer, based on available time and resources.

- **Mentor Suggestions**: The developer welcomes mentoring and feedback from the mentor and will actively seek their comments and suggestions during mentoring sessions. All suggestions will be carefully considered, with implementation decisions based on their impact on the project's timeline, feasibility, learning objectives, and available resources.


<a name="d"></a>

## 📌 Delimitations

- **Strictly Phase 1 Requirements**: The system will be developed only to meet the objectives defined in Phase 1.

- **User Roles**: Phase 1 includes only basic employee details and salary calculations. User roles, such as admin or system user, will be implemented. Employee-level access and management will be considered but not emphasized.

- **Data Structure**: The MySQL database will be used solely to store employee information (employee number, name, birthday) and work hours for calculation purposes. Additional data models or relationships (such as employee benefits, payroll history, or detailed logs) are excluded from Phase 1.

- **User Interface**: Phase 1 will not focus on complex user interfaces or frontend development. The application will operate primarily as a backend service, with the employee data presented in a simple and functional format. The user interface will be minimal in design, and there will be limited focus on the aesthetics or advanced user interface features.

- **Error Handling and Security**: While basic error handling will be implemented, comprehensive error management and security will not be addressed in Phase 1. The project will focus on implementing basic functional calculations without implementing complex security features.


<a name="ms2"></a>


## 📌 Project Continuation & MS 2 Foundation

The repository **[cp1](https://github.com/imperionite/cp1)** serves as the **foundation for Milestone 2 (MS2)** of the MotorPH Payroll System. While Phase 1 is still in development, this repository already includes both **explicit and implicit requirements** for Phase 1, ensuring a structured approach for future enhancements.  

### **Current Status:**  
✔️ **Phase 1 requirements setup** – The core functionalities have been structured according to the initial specifications.  
✔️ **Explicit & implicit requirements considered** – Some additional design elements have been planned for seamless expansion.  
✔️ **Ongoing development** – The project is actively being improved and refined based on requirements and feedback.  

### **Next Steps:**  
🚀 **Serial Mentoring Sessions** – The project will undergo **scheduled mentoring sessions** with the assigned mentor to ensure that all requirements are met effectively and any refinements are aligned with best practices.  
📌 **Incremental Updates** – Future iterations will incorporate refinements based on both **Phase 1 requirements and MS2 objectives**.  

This repository remains a **work in progress**, with continuous development and guidance to ensure its successful completion.  

---

<a name="conclusion"></a>

### 💡 Conclusion

The **MotorPH Payroll System Phase 1** project aims to lay the groundwork for a robust, end-to-end payroll management system. Through careful planning and phased implementation, this project addresses the core requirements of displaying employee details, calculating work hours, and determining gross and net salaries. The systematic approach outlined in this project plan ensures that deliverables are met within the given timeline while maintaining quality and usability.

#### 🧠 Final Thought

Building the foundation of the payroll system in Phase 1 is not just about fulfilling technical requirements but also about understanding user needs and delivering a reliable and user-friendly solution. This phase sets the tone for future enhancements and expansions, ensuring scalability and efficiency for MotorPH.

##### 🚀 Key Takeaways

- **Phased Development Approach**: Breaking down the requirements into smaller phases allows for iterative development, ensuring better focus and quality control.
- **User-Centric Design**: Designing wireframes and implementing intuitive features ensures that the application is accessible and meets user expectations.
- **Foundation for Scalability**: By addressing the core functionalities now, the project creates a strong base for future phases, where additional features and role-based controls can be introduced.
- **Time Management**: Strict adherence to the project timeline will be critical for timely delivery and maintaining alignment with business goals.
- **Future Opportunities**: This phase provides valuable insights into system requirements, user behavior, and technical considerations, paving the way for an improved and comprehensive payroll solution in subsequent phases.










