# Requirements Identification Submission (RIS) - Phase 1
by: [Arnel Imperial](https://github.com/imperionite)


<a name="intro"></a>

## 📌 Introduction

This document outlines the project plan, requirements, design, and implementation details for Phase 1 of the MotorPH Payroll System. The goal of this phase is to develop a foundational system for presenting employee information and calculating salaries, with an optional enhancement for secure authentication.

The repository [imperionite/cp1](https://github.com/imperionite/cp1) serves as the initial implementation, focusing on setting up both **explicit and implicit requirements** of the project. The system is continuously developed and will undergo **serial mentoring sessions** with the assigned mentor to refine its features and ensure its alignment with best practices.

**Technology Stack**
- **Backend:** Java 17, Spring Boot 3.4.2
- **Database:** MySQL (Relational Database for payroll data storage)
- **Security:** JWT Authentication, Role-Based Access Control
- **Data Ingestion:** Spring Boot API & ApplicationRunner for initial data loading
- **Version Control:** GitHub
- **Lombok** - Reducing boilerplate code

Phase 1 establishes a foundation for future enhancements, ensuring scalability and maintainability.

### **Project Goals**
1. **Visual Representation** - Create a diagram to outline system functionality.
2. **Employee Information Display** - Implement an API to retrieve employee details (ID, name, birthday).
3. **Attendance Tracking & Hours Computation** - Process employee log-ins/log-outs to calculate weekly work hours.
4. **Gross Salary Calculation** - Compute weekly gross pay based on work hours and hourly rates.
5. **Net Salary Calculation** - Apply deductions to determine the final net salary.
6. **Testing & Revisions** - Conduct validation tests to ensure correctness.
7. **Security Implementation** - Secure sensitive payroll data.
8. **User-Friendly Interface Development** - Build an intuitive interface for admin and employee interactions.
10. **Documentation** - Maintain clear project documentation.

## 🧬 Table of Contents

1. [ Introduction ](#intro)
2. [ RIS Components ](#ris)
3. [ Project Scope](#scope)
4. [ Requirement Analysis ](#ra)
5. [ Proposed Solution ](#solution)
6. [ Effort Estimation ](#ee)
7. [ Use Case Diagram ](#uc)
8. [ Wireframe ](#wireframe)
9. [ Project Plan ](#pp)
10. [ Limitations & Delimitations ](#ld)
11. [ Project Continuation & MS 2 Foundation ](#ms2)
12. [ Conclusion ](#conclusion)

<a name="ris"></a>

## 📌 RIS Component Links

This project is divided into multiple deliverables through assignment submission. The following components form the backbone of the Milestone 1:

- [Use Case Diagram](https://drive.google.com/file/d/1fy22zh23FYo-Yga100zrazLIi1KqGD1Y/view?usp=sharing)
- [Wireframe](https://drive.google.com/file/d/1mCZ7C4M0fcWmybx1id2vGbOQQxCE_iBV/view?usp=sharing)
- [Project Plan Timeline](https://tinyurl.com/mr4bjzjm)
- [MotorPH Requirements Worksheet](https://docs.google.com/spreadsheets/d/16WVjM2qbPiA4lTBkNgSnAEH1urHDoyUGpCUNWzILGxU/edit?usp=sharing)

Each component is iteratively improved as development progresses.


<a name="scope"></a>


## 📌 Project Scope (Phase 1)

The project scope for Phase 1 has been carefully defined to focus on the core requirements of displaying employee information and performing basic salary calculations. This concise scope allows for focused development and efficient delivery within the given timeframe. While a full payroll system requires broader functionality, these are explicitly designated for future phases.

**Included:**

*   Presentation of employee details (Employee Number, Name, Birthday).
*   Automatic salary calculation (Gross and Net) based on hours worked and predefined deductions.
*   Simple UI for viewing employee information and calculations.

**Optional:**

*   Administrator E Employee (normal user) Roles
*   Employee Management Module (Add, Edit, Delete)
*   Payroll Configuration Module (Deductions)
*   User Authentication

**Excluded:**

*   Multi-level role-based access control (RBAC beyond Admin & Employee)
*   Payroll Configuration Module (Tax Rules, Tax Rules)
*   Tax Calculations
*   Reporting
*   Full HR module integration
*   Timesheet Management
*   Fully functional web-based application beyond Phase 1 requirements

### Justification

The project scope is limited to presenting employee information and basic salary calculation due to the constraints of a single developer and a limited timeframe. More complex features, such as tax calculations and reporting, have been excluded due to their complexity and the need to maintain a manageable scope for Phase 1. The focus is on the core employee experience to ensure that the essential requirements are met effectively. 

#### **1. Data Handling Approach**
Instead of integrating with the **Google Sheets API**, the project **extracts data manually** from Google Sheets and loads it into the database through:
- **Spring Boot API Endpoint** to handle data ingestion.
- **ApplicationRunner** to initialize the database with employee and attendance data.

#### **2. Justification for This Approach**
- **Efficiency:** Avoids API complexities (authentication, rate limits, error handling) and ensures streamlined payroll computation.
- **Data Integrity:** A structured database prevents inconsistencies that may arise from collaborative editing in Google Sheets.
- **Performance Optimization:** Enables fast SQL queries for payroll calculations, rather than relying on external API requests.
- **Development Focus:** Prioritizes payroll processing logic within the **10-week timeline**, leaving room for enhancements in future phases.

This structured approach ensures the system remains **robust, maintainable, and scalable**, aligning with both project requirements and development constraints.

<a name="ra"></a>

## 📌 Requirement Analysis

### Overview
MotorPH is developing an end-to-end payroll system to manage employee details, work hours, and salary calculations. The project will be built in phases, expanding capabilities over time. This document outlines the requirements for **Phase 1**, which focuses on basic employee management and payroll calculations.

### Objectives
- Design and visualize the application structure.
- Develop a Spring Boot-based backend to manage employee details.
- Implement functionality to calculate work hours, gross salary, and net salary.
- Ensure data accuracy and basic security measures.

#### ⚙️ Identification of Needs

The system addresses the following needs from the employee's perspective:

- **Ability to easily view personal information**: To ensure accuracy and transparency, empowering employees to verify their data.
- **Understand how their salary is calculated**: To build trust and ensure fair compensation by providing a clear breakdown of earnings and deductions.
- **Simple and intuitive interface**: To ensure ease of use for all employees, regardless of their technical skills.
- **Secure Access**: To protect personal and financial information from unauthorized access using a state-of-the-art way of authenticating. To build trust and integrity to the end users and clients

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
- Role-based Access Control (RBAC) for admin/system user was not mentioned or emphasized in Phase 1 initial requirements, but it might be implemented as an optional requirement. Manager's/approver's access control will not be implemented.

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

Requirements were identified based on this [link](https://sites.google.com/mmdc.mcl.edu.ph/motorph/home) and through asking our mentor.

<a name="solution"></a>

## 📌 Proposed Solution (Detailed Technical Approach)

The proposed solution is a web-based application that allows MotorPH to manage employee payroll, focusing on the features relevant to the *employee* in this initial phase. The architecture is a simple three-tier architecture consisting of a presentation layer, a business logic layer, and a data access layer.

*   **Backend:** Spring Boot with Java. Spring Boot provides a robust and scalable framework for developing the REST API and handling business logic.
    - Justification: Spring Boot's auto-configuration and embedded server simplify development and deployment, enabling efficient use of the limited timeframe.

*   **Frontend:** HTML, CSS, and JavaScript but React library might be considered.
    - Justification: These technologies provide a simple and cross-platform way to create a user interface.

*   **Database:** MySQL to persist employee data, salary information, and user credentials.
    - Justification: MySQL is a reliable and open-source database that meets the project's data storage needs.

*   **API:** A RESTful API will be created for the backend and frontend interaction.

*   **JWT Authentication**: JSON Web Tokens will be used for authentication (optional).
    - Justification: JWT provides a stateless and secure way to authenticate users, enhancing the system's security.

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

##### Main Tasks and Subtasks

### 1. Conduct Needs Analysis (Requirements Gathering)
   - Identify stakeholders' needs within MotorPH.
   - Document explicit Phase 1 requirements.
   - Assess potential constraints and dependencies.

### 2. Design Database Schema for Payroll Data Storage
   - Define tables for employee details, work hours, salary rates, and deductions.
   - Establish relationships between tables.
   - Implement initial database setup.

### 3. Implement Employee Details Presentation
   - Develop API endpoint for fetching employee details.
   - Implement UI/UX components for employee information display.

### 4. Develop Hours Worked Calculation Logic
   - Extract attendance records.
   - Write algorithms to accurately calculate weekly work hours.
   - Ensure data validation for log-in/log-out time accuracy.

### 5. Implement Gross Salary Calculation
   - Retrieve necessary data from the database (hourly wage rates, overtime rules).
   - Compute gross salary based on hours worked.
   - Validate calculations against test cases.

### 6. Implement Net Salary Calculation (After Deductions)
   - Apply generic deductions (e.g., tax, benefits).
   - Store and manage deduction rules within the database.
   - Ensure correctness of final salary computations.

### 7. Conduct Testing & Revisions
   - Conduct unit testing
   - Fix identified bugs, optimize performance and refactoring

### 8. Develop User-Friendly Interface
   - Design an intuitive UI/UX for payroll processing.
   - Ensure accessibility and ease of navigation for administrators and employees.

### 9. Refactoring & Documentation

### 10. Polishing and Final Submission


##### Knowledge Needed

To accomplish these tasks effectively:

- Familiarity with database design principles.
- Understanding of payroll calculation logic.
- Knowledge of UI/UX design principles.
- Awareness of compliance regulations affecting payroll processing (optional).
- Proficiency in programming languages suitable for web applications (e.g., Java or even Python).
- Experience with security measures like encryption and access controls.

##### Additional Help Needed

Additional resources that would be beneficial include:

1. Technical documentation and guides on database management systems (DBMS) like MySQL or PostgreSQL.
2. Mentorship from experienced developers familiar with similar projects.
3. Collaboration tools such as ClickUp.
4. Testing frameworks like JUnit, etc. for comprehensive unit testing.
5. User interface templates that can be customized according to MotorPH’s branding guidelines 

##### Estimated Time per Task

Refer to this [link](https://tinyurl.com/mr4bjzjm) for the project's timeline. 

Here are estimated times based on complexity and assuming moderate experience:

1. Conduct Needs Analysis: 8–12 hours  
2. Design Database Schema: 10–15 hours  
3. Develop Employee Details Display: 6–10 hours  
4. Implement Work Hours Calculation: 8–12 hours  
5. Integrate Gross Salary Calculation: 10–15 hours  
6. Implement Net Salary Calculation: 12–18 hours  
7. Testing & Revision: 45–60 hours  
8. User-Friendly Interface Development: 20—30 hours   
9. Refactoring & Documentation: 5—10 hours    
10. Polishing and Final Submission: 8—15 hours   

##### Estimated Project Completion

To determine the number of weeks required to complete my outputs for Phase 1 of the MotorPH Payroll System, I need to consider the estimated total hours of work and the expected weekly time commitment of 7.5 hours per week. Based on the complexity of the project, the development process involves multiple stages, including visualization, employee information display, work hours calculation, payroll computation, and system testing. If I estimate that the entire project will take approximately `75 hours to complete`, dividing this by the `7.5-hour weekly` commitment results in **10 weeks of work**. This aligns closely with the given **11-week timeline**, allowing for some flexibility in testing, refinements, and mentoring sessions. By effectively managing my time and following a structured approach, I can ensure that all Phase 1 requirements are met within the expected timeframe while maintaining high-quality output.


<a name="uc"></a>

## 📌 Use Case Diagram

### Overview
This document describes the **Use Case Diagram (UCD)** for Phase 1 of the **MotorPH Payroll System**. The system allows users to view employee details, log work hours, and calculate salaries.

#### Actor
**Employee**  
- Interacts with the system to retrieve employee details.  
- Logs work hours.  
- Triggers payroll calculations.  

##### Use Cases

###### View Employee Details
**Actor:** Employee  
**Description:** Retrieves and displays employee details such as employee number, name, and birthday.  
**Preconditions:** Employee records exist in the system.  
**Postconditions:** Employee details are displayed successfully.  

###### Log Work Hours
**Actor:** Employee 
**Description:** Users log their work hours by recording clock-in and clock-out times.  
**Preconditions:** The user is recognized by the system.  
**Postconditions:** Work hours are stored for payroll computation.  

###### Calculate Weekly Work Hours
**Actor:** Employee 
**Description:** Computes the total number of hours worked in a week based on recorded log-in and log-out times.  
**Preconditions:** Work hour records must be available.  
**Postconditions:** The system displays the calculated weekly work hours.  

###### Compute Gross Salary
**Actor:** Employee  
**Description:** Calculates the gross weekly salary based on the total hours worked and the predefined pay rate.  
**Preconditions:** Work hour records are available.  
**Postconditions:** The system displays the gross salary.  

###### Compute Net Salary
**Actor:** Employee 
**Description:** Computes the net weekly salary after applying generic deductions.  
**Preconditions:** Gross salary calculation must be completed.  
**Postconditions:** The system displays the net salary after deductions.  

##### Use Case Diagram
Refer to this [link](https://drive.google.com/file/d/1fy22zh23FYo-Yga100zrazLIi1KqGD1Y/view?usp=sharing) for the use case diagram representation of the project.

##### Justification

The UCD primarily focuses on the `Employee` actor to align with the Phase 1 requirement of demonstrating employee-facing functionality. While the Employee actor is the primary focus of the user interface and demonstrations for Phase 1, it is crucial to recognize that the Admin/System user is the logical and functional foundation of the entire payroll system. The Admin/System user possesses the privilege to configure payroll settings, manage employee data, and initiate payroll calculations for all employees. Without the Admin/System user's initial setup and ongoing management, the Employee's ability to view their information and receive accurate salary calculations would not be possible. Therefore, while the visual emphasis in Phase 1 is on the Employee interface, the underlying logic and system privileges are fundamentally dependent on the Admin/System user.


<a name="wireframe"></a>

## 📌 Wireframe

### Overview
This document provides a detailed explanation of the wireframe design for the **Employee Information and Salary Calculation Management System**. The wireframe showcases the visual layout and interaction flow of the application, focusing on Phase 1 requirements, which include presenting employee information and calculating salaries.

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
    - **Name**: Shows the full name of each employee (e.g., John Doe, Juan Dela Cruz).
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
    - **Gross Salary**: Shows the calculated gross salary in currency format.
    - **Deductions**: Displays total deductions applied.
    - **Net Salary**: Shows the final computed salary after deductions.
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

##### Justification
This wireframe provides a foundational layout for the **Employee Information and Salary Calculation Wireframe**, ensuring the application is user-friendly and fulfills the Phase 1 requirements. It effectively displays employee details and simplifies salary computation. Refer to this [link](https://drive.google.com/file/d/1mCZ7C4M0fcWmybx1id2vGbOQQxCE_iBV/view?usp=sharing) for the visual representation of the project's low-fidelity wireframe.

The design of the interface, even in this basic phase, is driven by the employee's need for clear and accessible information. Future iterations will refine the UI/UX based on feedback and expanded functionality.


<a name="pp"></a>

## 📌 Project Plan

### Overview

The **MotorPH Payroll System** aims to streamline payroll processes by managing products, employee details, and salaries. This document outlines the project plan for **Phase 1**, focusing on initial requirements and deliverables.

A structured project plan has been developed in **ClickUp**, breaking down the tasks into manageable sub-tasks with dependencies, ownership, deadlines, and tracking status. The development cycle follows an **iterative approach** to allow continuous refinement and adaptation.


#### Objectives

- **Visualization**: Develop a visual representation of the application interface.
- **Employee Information Presentation**: Display employee details, including employee number, name, and birthday.
- **Work Hours Calculation**: Compute the total number of hours an employee works in a week.
- **Gross Salary Calculation**: Determine the gross weekly salary based on hours worked.
- **Net Salary Calculation**: Calculate the net weekly salary after applying standard deductions.

### Timeline

Refer to this [link](https://tinyurl.com/mr4bjzjm) for the project plan timeline of the project 


#### **Project Summary**
- **Start Date:** January 28, 2025  
- **End Date:** March 24, 2025  
- **Duration:** **10 weeks**  
- **Estimated Hours:** **75 hours** (aligned with **7.5 hours per week**)  

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
- **Project Management**: [ClickUp](https://tinyurl.com/mr4bjzjm)

##### Risk Management

- **Scope Creep**: Maintain clear requirements and manage changes through a formal change control process.
- **Time Constraints**: Adhere to the timeline and allocate buffer time for unforeseen delays.
- **Technical Challenges**: Regularly consult documentation and seek assistance from the developer community as needed.

#### Generalization

This project plan outlines the roadmap for developing the **MotorPH Payroll System Phase 1**. By following this plan, we aim to deliver a functional and user-friendly payroll system within the stipulated timeframe.


<a name="ld"></a>

## 📌 Limitations & Delimitations


**Limitations**

- **Single Developer**: As the sole developer on this project, all tasks including system design, coding, testing, and debugging will be handled by one person. This may lead to limited bandwidth for tackling issues that arise during development, possibly impacting the speed and efficiency of completion.

- **Database Constraints**: The MySQL database will be used to store employee data, including employee details and work hours, and will run in a Docker container. The database setup is limited to Phase 1 requirements and will not include features such as: data analytics, reporting, integration with external systems, stored procedures, triggers or scheduled tasks.

- **Time Constraints**: With an 11-week timeframe, the focus will be on ensuring that the core functionality of employee information presentation, work hour and salary calculations is achieved. Time will not be allocated to expanding the system or addressing features not specified in Phase 1.

- **Testing Limitations**: Testing will be concentrated on validating the functionality of employee data presentation, work hour calculation, and salary computation. System-wide testing, user acceptance testing, load testing, stress testing, performance optimization, or security testing will not be performed in this phase.

- **Optional Features**: Any features that are not explicitly stated in the Phase 1 requirements will be considered optional elements. Their implementation will depend on time availability after fulfilling all mandatory requirements and will not be prioritized. Implementation of optional features will be at the discretion of the developer, based on available time and resources.

- **Mentor Suggestions**: The developer welcomes mentoring and feedback from the mentor and will actively seek their comments and suggestions during mentoring sessions. All suggestions will be carefully considered, with implementation decisions based on their impact on the project's timeline, feasibility, learning objectives, and available resources.


**Delimitations**

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

## 📌 Conclusion

The **MotorPH Payroll System Phase 1** project aims to lay the groundwork for a robust, end-to-end payroll management system. Through careful planning and phased implementation, this project addresses the core requirements of displaying employee details, calculating work hours, and determining gross and net salaries. The systematic approach outlined in this project plan ensures that deliverables are met within the given timeline while maintaining quality and usability.

### 🧠 Final Thought

Building the foundation of the payroll system in Phase 1 is not just about fulfilling technical requirements but also about understanding user needs and delivering a reliable and user-friendly solution. This phase sets the tone for future enhancements and expansions, ensuring scalability and efficiency for MotorPH.

### 🚀 Key Takeaways

- **Phased Development Approach**: Breaking down the requirements into smaller phases allows for iterative development, ensuring better focus and quality control.
- **User-Centric Design**: Designing wireframes and implementing intuitive features ensures that the application is accessible and meets user expectations.
- **Foundation for Scalability**: By addressing the core functionalities now, the project creates a strong base for future phases, where additional features and role-based controls can be introduced.
- **Time Management**: Strict adherence to the project timeline will be critical for timely delivery and maintaining alignment with business goals.
- **Future Opportunities**: This phase provides valuable insights into system requirements, user behavior, and technical considerations, paving the way for an improved and comprehensive payroll solution in subsequent phases.










