# Requirements Identification Submission (RIS) - Phase 1

by: [Arnel Imperial](https://github.com/imperionite)

<a name="intro"></a>

## 📌 Introduction

This document outlines the _team details (as a sole member), MotorPH requirements, effort estimate, use case diagram (UCD), wireframe, project plan, and other essential details for Phase 1 of the MotorPH Payroll System_. The goal of this phase is to develop a foundational system for presenting employee information and calculating salaries, with an optional enhancement for secure authentication.

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
12. [Key Justifications](#kj)
13. [Conclusion](#conclusion)

<a name="ris"></a>

## 📌 RIS Component Links

This project is divided into multiple deliverables through assignment submission. The following components form the backbone of the Milestone 1:

- [Use Case Diagram](https://drive.google.com/file/d/1fy22zh23FYo-Yga100zrazLIi1KqGD1Y/view?usp=sharing) - _Revised to clarify scope (see explanation below)_
- [Wireframe](https://drive.google.com/file/d/1mCZ7C4M0fcWmybx1id2vGbOQQxCE_iBV/view?usp=sharing) - _Revised to include elements related to employee info and salary calculation (see explanation below)_
- [Project Plan Timeline](https://tinyurl.com/mr4bjzjm) - _Revised to include task durations in hours (see explanation below)_
- [MotorPH Requirements Worksheet](https://docs.google.com/spreadsheets/d/16WVjM2qbPiA4lTBkNgSnAEH1urHDoyUGpCUNWzILGxU/edit?usp=sharing) - _Consolidated requirement identification, project plan and effort estimation details are merge on this project as one (see specific section below)_

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

- **Frontend:** HTML, CSS, and JavaScript but React library might be considered.

- **Database:** MySQL to persist employee data, salary information, and user credentials.

- **API:** A RESTful API will be created for the backend and frontend interaction.

- **JWT Authentication**: JSON Web Tokens will be used for authentication (optional).

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

Refer to this [link](https://tinyurl.com/mr4bjzjm) for the project's timeline and effort estimate in hours.

##### Estimated Project Completion

To determine the number of weeks required to complete my outputs for Phase 1 of the MotorPH Payroll System, I need to consider the estimated total hours of work and the expected weekly time commitment of 7.5 hours per week. Based on the complexity of the project, the development process involves multiple stages, including visualization, employee information display, work hours calculation, payroll computation, and system testing. If I estimate that the entire project will take approximately `75 hours to complete`, dividing this by the `7.5-hour weekly` commitment results in approximately `10 weeks to complete` the work. This timeline aligns with the expected 11-week completion timeframe.

<a name="uc"></a>

## 📌 Use Case Diagram

_[UCD link](https://drive.google.com/file/d/1fy22zh23FYo-Yga100zrazLIi1KqGD1Y/view?usp=sharing)_

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

_[Wireframe link](https://drive.google.com/file/d/1mCZ7C4M0fcWmybx1id2vGbOQQxCE_iBV/view?usp=sharing)_

The wireframe has been updated to reflect the core functionalities included in Phase 1. It primarily focuses on the UI elements required for:

- Displaying employee information (Employee Number, Name, Birthday)
- Presenting the calculated Gross and Net Salary
- Login interface
- Display Manage Employee Data

The wireframe provides a visual representation of the user interface for these core features. Given the time constraints on Phase 1, only simple UI is presented.

<a name="pp"></a>

## 📌 Project Plan

_[Project plan timeline link](https://tinyurl.com/mr4bjzjm)_

A structured project plan has been developed in ClickUp, breaking down the tasks into manageable sub-tasks with dependencies, ownership, deadlines, and tracking status. The development cycle follows an iterative approach to allow continuous refinement and adaptation.

<a name="ld"></a>

## 📌 Scope Delimitations and Known Limitations

To ensure a clear understanding of the boundaries of this Phase 1 implementation, this section outlines the specific functionalities that are explicitly excluded from the scope of this phase (Scope Delimitations), as well as acknowledges the known areas for future improvement in the current implementation (Known Limitations). This is intended to manage expectations and provide context for future development efforts.

**Limitations**

- **Single Developer:** As the sole developer on this project, all tasks including system design, coding, testing, and debugging are handled by one person. This may lead to limited bandwidth for tackling issues that arise during development, potentially impacting the speed and efficiency of completion.
- **Database Constraints:** The MySQL database is used to store employee data, including employee details and work hours, and runs in a Docker container. However, the database setup is limited to Phase 1 requirements and does not include features such as data analytics, reporting, integration with external systems, stored procedures, triggers, or scheduled tasks.
- **Time Constraints:** With an 11-week timeframe, the focus is on ensuring that the core functionality of employee information presentation, work hour, and salary calculations is achieved. Time is not allocated to expanding the system or addressing features not specified in Phase 1.
- **Testing Limitations:** Testing is concentrated on validating the functionality of employee data presentation, work hour calculation, and salary computation. System-wide testing, user acceptance testing, load testing, stress testing, performance optimization, or comprehensive security testing are not performed in this phase.
- **Optional Features:** Any features that are not explicitly stated in the Phase 1 requirements are considered optional elements. Their implementation depends on time availability after fulfilling all mandatory requirements and is at the discretion of the developer, based on available time and resources.
- **Reliance on Mentor Suggestions:** The developer welcomes mentoring and feedback from the mentor and actively seeks their comments and suggestions during mentoring sessions. However, implementation decisions are based on their impact on the project's timeline, feasibility, learning objectives, and available resources.

**Delimitations**

- **Focus on Mandatory Phase 1 Requirements:** The system will be developed strictly to meet the objectives defined in the Phase 1 requirements. Features and functionalities beyond those requirements are explicitly excluded from this phase.
- **Limited User Roles:** Phase 1 includes only basic employee details and salary calculations. Basic user roles, such as admin or system user and employee-level will be implemented though not emphasized. Based on my Phase 1 Use Case Diagram that prioritizes the Employee actor to showcase employee-facing functionalities. 
While the Admin/System user's actions aren't visually emphasized, their role is essential for system configuration, data management, and payroll initiation – prerequisites for employee access and accurate calculations. Therefore, despite Phase 1's visual focus on the Employee, the underlying system logic is intrinsically linked to the Admin/System user.
- **Data Structure Focused on Core Information:** The MySQL database will be used solely to store employee information (employee number, name, birthday) and work hours for calculation purposes. Additional data models or relationships (such as employee benefits, payroll history, or detailed logs) are excluded from Phase 1.
- **Minimal User Interface:** Phase 1 focuses on backend functionality, and the user interface will be minimal in design. The application will operate primarily as a backend service, with employee data presented in a simple and functional format. There will be limited focus on aesthetics or advanced user interface features.
- **Limited Error Handling and Security:** While basic error handling will be implemented, comprehensive error management and security measures will not be addressed in Phase 1. The project focuses on implementing core functional calculations without implementing complex security features.

<a name="ms2"></a>

## 📌 Project Continuation & MS 2 Foundation

The repository **[cp1](https://github.com/imperionite/cp1)** serves as the **foundation for Milestone 2 (MS2)** of the MotorPH Payroll System. While Phase 1 is still in development, this repository already includes both **explicit and implicit requirements** for Phase 1, ensuring a structured approach for future enhancements.

### **Current Status:**

✔️ **Phase 1 requirements setup** – The core functionalities have been structured according to the initial specifications.  
✔️ **Explicit & implicit requirements considered** – Some additional design elements have been planned for seamless expansion.  
✔️ **Ongoing development** – The project is actively being improved and refined based on requirements and feedback.

### **Next Steps:**

🚀 **Serial Mentoring Sessions** – The project will undergo **scheduled mentoring sessions** with the assigned mentor to ensure that all requirements are met effectively and any refinements are aligned with best practices.  
🚀 **Incremental Updates** – Future iterations will incorporate refinements based on both **Phase 1 requirements and MS2 objectives**.

This repository remains a **work in progress**, with continuous development and guidance to ensure its successful completion.

<a name="kj"></a>

## 📌 Key Justifications

This project is meticulously designed to align with the requirements, expectations, and constraints of all stakeholders involved, including MotorPH, the project evaluators (based on the rubrics), and the instructor (based on provided feedback). The following justifications provide a comprehensive overview of the key decisions made throughout the project and the rationale behind them, demonstrating a commitment to delivering a well-aligned and successful Phase 1 outcome.

- **1. Focused Project Scope (Adherence to Phase 1 Core Requirements):**

  - **Justification:** The project scope is intentionally limited to the core functionalities of presenting employee information and performing basic salary calculations, as explicitly defined in MotorPH's Phase 1 requirements. This strategic decision allows for efficient resource allocation, a manageable development timeline, and a reduced risk of scope creep.
  - **Alignment:**
    - **MotorPH Requirements:** Directly addresses the Phase 1 focus on foundational employee data management and payroll processing.
    - **Project Rubrics:** Demonstrates a clear understanding of project scope, effective prioritization of requirements, and efficient resource management.

- **2. Pragmatic Data Handling Approach (Manual Data Extraction from Google Sheets):**

  - **Justification:** The decision to manually extract data from Google Sheets and load it into the database via Spring Boot API and ApplicationRunner, instead of integrating directly with the Google Sheets API, is driven by several practical considerations. This approach avoids the complexities associated with API integration (authentication, rate limits, error handling), streamlines payroll computation, ensures data integrity through a structured database, enables fast SQL queries for efficient data retrieval, and prioritizes the development of core payroll processing logic within the limited 10-week timeline.
  - **Alignment:**
    - **MotorPH Requirements:** Facilitates the efficient implementation of basic salary calculations, a key objective of Phase 1.
    - **Project Rubrics:** Demonstrates adaptability, problem-solving skills, and the ability to make informed decisions based on project constraints.

- **3. Strategic Technology Stack Selection (Spring Boot, MySQL, JWT Authentication):**

  - **Justification:** The selection of Spring Boot (for the backend), MySQL (for the database), and JWT Authentication (for security) is based on their suitability for the project's requirements, their industry-standard nature, and their ability to provide a solid foundation for future expansion. Spring Boot's auto-configuration and embedded server simplify development and deployment, MySQL offers a reliable and open-source data storage solution, and JWT Authentication provides a stateless and secure way to protect the data.
  - **Alignment:**
    - **MotorPH Requirements:** Provides a robust, scalable, and secure platform for building the payroll system.
    - **Project Rubrics:** Demonstrates technical expertise in selecting appropriate technologies and designing a well-architected system.

- **4. Intentional Simplicity of User Interface (Focus on Essential Data Presentation):**

  - **Justification:** The UI is intentionally designed to be simple and focused on presenting essential employee information and salary calculations. This approach allows for efficient development, reduces complexity, and aligns with the Phase 1 requirement of a "basic presentation."
  - **Alignment:**
    - **MotorPH Requirements:** Directly addresses the need for a clear and concise presentation of employee data and salary information.
    - **Project Rubrics:** Demonstrates an understanding of the importance of prioritizing tasks within a limited timeframe and focusing on delivering core functionality.

- **5. Proactive Consideration of Non-Functional Aspects (Performance, Security, Scalability):**

  - **Justification:** While not explicitly mandated in the initial Phase 1 requirements, certain non-functional aspects, such as performance, security, and scalability, have been proactively considered during the design and implementation phases. This forward-thinking approach ensures that the system is built on a solid foundation, allowing for future enhancements and expansion without requiring significant rework. Basic JWT Authentication implementation ensures the security and state-of-the-art protection of the data of the application.
  - **Alignment:**
    - **MotorPH Requirements:** Demonstrates a commitment to building a robust and maintainable system that can evolve over time.
    - **Project Rubrics:** Showcases a comprehensive understanding of system design principles and the importance of considering both functional and non-functional aspects.

<a name="conclusion"></a>

## 📌 Conclusion

Phase 1 of the MotorPH Payroll System project successfully addresses the core requirements of employee information display and basic salary calculation. The project follows a well-defined plan, utilizes appropriate technologies, and lays a solid foundation for future expansion. By focusing on the essential features and managing the project scope effectively, this phase ensures a successful delivery within the given timeframe.
