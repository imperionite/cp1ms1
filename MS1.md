# Requirements Identification Submission (RIS) - Phase 1

by: [Arnel Imperial](https://github.com/imperionite)

<a name="intro"></a>

## 📌 Introduction

This document outlines the project plan, requirements, design, and implementation details for Phase 1 of the MotorPH Payroll System. The goal of this phase is to develop a foundational system for presenting employee information and calculating salaries, with an optional enhancement for secure authentication.

The repository [imperionite/cp1](https://github.com/imperionite/cp1) serves as the initial implementation, focusing on setting up both **explicit and implicit requirements** of the project. The system is continuously developed and will undergo **serial mentoring sessions** with the assigned mentor to refine its features and ensure its alignment with best practices.

### ⚙️ **Technology Stack**

- **Backend:** Java 17, Spring Boot 3.4.2
- **Database:** MySQL (Relational Database for payroll data storage)
- **Security:** JWT Authentication, Role-Based Access Control
- **Data Ingestion:** Spring Boot API & ApplicationRunner for initial data loading
- **Version Control:** GitHub
- **Lombok** - Reducing boilerplate code
- **Version Control**: Git
- **Project Management**: [ClickUp](https://tinyurl.com/mr4bjzjm)

Phase 1 establishes a foundation for future enhancements, ensuring scalability and maintainability.

### ⚙️ **Project Goals**

1.  **Visual Representation** - Create a diagram to outline system functionality.
2.  **Employee Information Display** - Implement an API to retrieve employee details (ID, name, birthday).
3.  **Attendance Tracking & Hours Computation** - Process employee log-ins/log-outs to calculate weekly work hours.
4.  **Gross Salary Calculation** - Compute weekly gross pay based on work hours and hourly rates.
5.  **Net Salary Calculation** - Apply deductions to determine the final net salary.
6.  **Testing & Revisions** - Conduct validation tests to ensure correctness.
7.  **Security Implementation** - Secure sensitive payroll data.
8.  **User-Friendly Interface Development** - Build an intuitive interface for admin and employee interactions.
9.  **Documentation** - Maintain clear project documentation.

### ⚙️ **Identification of Needs**

The system addresses the following needs from the employee's perspective:

- **Ability to easily view personal information**: To ensure accuracy and transparency, empowering employees to verify their data.
- **Understand how their salary is calculated**: To build trust and ensure fair compensation by providing a clear breakdown of earnings and deductions.
- **Simple and intuitive interface**: To ensure ease of use for all employees, regardless of their technical skills.
- **Secure Access**: To protect personal and financial information from unauthorized access using a state-of-the-art way of authenticating. To build trust and integrity to the end users and clients

## 🧬 Table of Contents

1.  [Introduction](#intro)
2.  [RIS Components](#ris)
3.  [Project Scope](#scope)
4.  [Requirement Analysis](#ra)
5.  [Proposed Solution](#solution)
6.  [Effort Estimation](#ee)
7.  [Use Case Diagram](#uc)
8.  [Wireframe](#wireframe)
9.  [Project Plan](#pp)
10. [Limitations & Delimitations](#ld)
11. [Project Continuation & MS 2 Foundation](#ms2)
12. [Conclusion](#conclusion)

<a name="ris"></a>

## 📌 RIS Component Links

This project is divided into multiple deliverables through assignment submission. The following components form the backbone of the Milestone 1:

- [Use Case Diagram](https://drive.google.com/file/d/1fy22zh23FYo-Yga100zrazLIi1KqGD1Y/view?usp=sharing) - _Revised to clarify scope (see explanation below)_
- [Wireframe](https://drive.google.com/file/d/1mCZ7C4M0fcWmybx1id2vGbOQQxCE_iBV/view?usp=sharing) - _Revised to include elements related to employee info and salary calculation (see explanation below)_
- [Project Plan Timeline](https://tinyurl.com/mr4bjzjm) - _Revised to include task durations in hours (see explanation below)_
- [MotorPH Requirements Worksheet](https://docs.google.com/spreadsheets/d/16WVjM2qbPiA4lTBkNgSnAEH1urHDoyUGpCUNWzILGxU/edit?usp=sharing) - _Consolidated project plan and effort estimation details here (see explanation below)_

Each component is iteratively improved as development progresses.

<a name="scope"></a>

## 📌 Project Scope (Phase 1)

The project scope for Phase 1 has been carefully defined to focus on the core requirements of displaying employee information and performing basic salary calculations. This concise scope allows for focused development and efficient delivery within the given timeframe. While a full payroll system requires broader functionality, these are explicitly designated for future phases.

**Included:**

- Presentation of employee details (Employee Number, Name, Birthday).
- Automatic salary calculation (Gross and Net) based on hours worked and predefined deductions.
- Simple UI for viewing employee information and calculations.
- JWT based authentication
- Role-based Access Control (RBAC) for admin/system user

**Excluded:**

- Multi-level role-based access control (RBAC beyond Admin & Employee)
- Payroll Configuration Module (Tax Rules, Tax Rules)
- Tax Calculations
- Reporting
- Full HR module integration
- Timesheet Management
- Fully functional web-based application beyond Phase 1 requirements

### Justification

The project scope is limited to presenting employee information and basic salary calculation due to several factors. Firstly, as an individual developer, the constraints of a limited timeframe necessitate a focused approach to ensure the core employee experience is delivered effectively.

While the recommendation to join a group was considered, the decision to proceed individually allows for a more streamlined development process and a greater degree of control over the project's direction within the given timeframe. More complex and implicit features have been excluded due to their inherent complexity and the need to maintain a manageable scope for this initial phase. The priority is to meet the essential requirements efficiently and build a solid foundation for future expansion.

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

- Apply generic deductions, specifically:
  - **Fixed Tax Rate (e.g., 10%)**
  - **Standard Benefit Contribution (e.g., PhilHealth)**
- Compute net salary after deductions.
- Ensure accurate calculations based on predefined rules.

#### Non-Functional Considerations

While not explicitly mandated in the initial Phase 1 requirements, certain non-functional aspects have been considered to ensure a solid foundation for future development and a reasonable user experience. These considerations are implemented at a basic level, focusing on efficiency and security best practices.

##### Performance

- The system is designed to handle a moderate number of employee records efficiently. API responses are optimized for reasonably quick retrieval of employee data and salary calculations. These optimizations lay the groundwork for handling larger datasets in future phases.

##### Security

- Employee data is protected through basic measures to prevent unauthorized access. API endpoints include JWT-based authentication to secure access. Role-Based Access Control (RBAC) for admin/system user is implemented to showcase the application's security, though Manager/Approver level access control is outside the scope of Phase 1.

##### Scalability

- The system architecture is designed with future scalability in mind, allowing for the accommodation of more complex payroll rules and additional employee data fields in subsequent phases. This includes using a relational database and a modular code structure.

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

The proposed solution is a web-based application that allows MotorPH to manage employee payroll, focusing on the features relevant to the _employee_ in this initial phase. The architecture is a simple three-tier architecture consisting of a presentation layer, a business logic layer, and a data access layer.

- **Backend:** Spring Boot with Java. Spring Boot provides a robust and scalable framework for developing the REST API and handling business logic.

  - Justification: Spring Boot's auto-configuration and embedded server simplify development and deployment, enabling efficient use of the limited timeframe.

- **Frontend:** HTML, CSS, and JavaScript but React library might be considered.

  - Justification: These technologies provide a simple and cross-platform way to create a user interface.

- **Database:** MySQL to persist employee data, salary information, and user credentials.

  - Justification: MySQL is a reliable and open-source database that meets the project's data storage needs.

- **API:** A RESTful API will be created for the backend and frontend interaction.
- **JWT Authentication**: JSON Web Tokens will be used for authentication (optional).

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

### Main Tasks and Subtasks

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

1.  Technical documentation and guides on database management systems (DBMS) like MySQL or PostgreSQL.
2.  Mentorship from experienced developers familiar with similar projects.
3.  Collaboration tools such as ClickUp.
4.  Testing frameworks like JUnit, etc. for comprehensive unit testing.
5.  User interface templates that can be customized according to MotorPH’s branding guidelines

##### Estimated Time per Task

Refer to this [MotorPH Requirements Worksheet](https://docs.google.com/spreadsheets/d/16WVjM2qbPiA4lTBkNgSnAEH1urHDoyUGpCUNWzILGxU/edit?usp=sharing) for the project's timeline and effort estimate in hours.

##### Estimated Project Completion

To determine the number of weeks required to complete my outputs for Phase 1 of the MotorPH Payroll System, I need to consider the estimated total hours of work and the expected weekly time commitment of 7.5 hours per week. Based on the complexity of the project, the development process involves multiple stages, including visualization, employee information display, work hours calculation, payroll computation, and system testing. If I estimate that the entire project will take approximately `75 hours to complete`, dividing this by the `7.5-hour weekly` commitment results in approximately `10 weeks to complete` the work. This timeline aligns with the expected 11-week completion timeframe.

<a name="uc"></a>

## 📌 Use Case Diagram

_(Revised Use Case Diagram - Addressing Teacher's Feedback)_

This Use Case Diagram represents the **core functionalities** included within the **scope of Phase 1**. Given the limited scope of Phase 1 (employee information and salary calculation), the diagram focuses on the key user interactions related to these features. A more comprehensive UCD will be developed in future phases as the system's functionality expands.

This diagram includes two actors

- **Admin**:
  - Manage Employee Data
- **Employee**:
  - Login
  - View Personal Information
  - View Salary Calculation

<a name="wireframe"></a>

## 📌 Wireframe

_(Revised Wireframe - Addressing Teacher's Feedback)_

The wireframe has been updated to reflect the core functionalities included in Phase 1. It primarily focuses on the UI elements required for:

- Displaying employee information (Employee Number, Name, Birthday)
- Presenting the calculated Gross and Net Salary
- Login interface
- Display Manage Employee Data

The wireframe provides a visual representation of the user interface for these core features. Given the time constraints on Phase 1, only simple UI is presented.

<a name="pp"></a>

## 📌 Project Plan

_(Revised Project Plan - Addressing Teacher's Feedback)_

The detailed project plan, including task durations in hours, has been incorporated into the [MotorPH Requirements Worksheet](https://docs.google.com/spreadsheets/d/16WVjM2qbPiA4lTBkNgSnAEH1urHDoyUGpCUNWzILGxU/edit?usp=sharing). This worksheet provides a comprehensive view of the project timeline, task dependencies, and resource allocation.

## 📌 Limitations & Delimitations

Due to the time constraints and the individual nature of the project, certain limitations have been identified:

- **Limited UI Functionality:** The UI will be basic and primarily focused on displaying data.
- **Manual Data Extraction:** Data is manually extracted, which may not be scalable in the long term.
- **Generic Deductions:** Only standard deductions are considered in Phase 1.
- **Single User Testing:** Testing is primarily conducted by the developer.

<a name="ms2"></a>

## 📌 Project Continuation & MS 2 Foundation

Phase 1 lays the foundation for future development. MS2 will focus on:

- Implementing additional modules such as Timesheet Management and Reporting.
- Integrating with external systems for automated data ingestion.
- Enhancing the UI/UX for improved user experience.
- Implementing more robust security measures.

<a name="conclusion"></a>

## 📌 Conclusion

Phase 1 of the MotorPH Payroll System project successfully addresses the core requirements of employee information display and basic salary calculation. The project follows a well-defined plan, utilizes appropriate technologies, and lays a solid foundation for future expansion. By focusing on the essential features and managing the project scope effectively, this phase ensures a successful delivery within the given timeframe.
