📝 LOG BOOK
Semester Project - III (Sem-V, 2024-25)

📅 Weekly Progress
| Week | Date Range          | Tasks Completed                                              | Next Steps                           |
|------|---------------------|---------------------------------------------------------------|--------------------------------------|
| 1    | --------------------   | Introduction: Background, Motivation                          | Finalize problem statement          |
| 2    | --------------------  | Introduction: Problem Statement, Objectives                    | Literature survey planning          |
| 3    | ===================    | Literature Survey: Reviewed existing systems, limitations      | Tabulate findings                   |
| 4    | --------------------  | Proposed System: Architecture, Algorithm design               | Finalize technology stack           |
| 5    |--------------------   | Requirements: Software (Kotlin, TensorFlow Lite), Hardware (Android devices) | Begin UI prototyping                |
| 6    | --------------------  | Methodology: Workflow design, dataset selection               | Start UI implementation             |
| 7    |--------------------- | Module 1: UI Prototype (Figma) → Android Studio conversion    | Integrate ASL dataset               |
| 8    |----------------------| Module 2: Gesture recognition (TensorFlow Lite model training)| Speech-to-text API integration      |
| 9    | -------------------- | Module 3: Backend logic, output synchronization              | Testing & optimization              |
| 10   | ---------------------  | Outcome: Final testing, report writing, deployment prep       | Cross-device checks                 |


## MedBridge: A Smart and Connected Hospital Ecosystem


# 1. Introduction

## 1.1 Background and Motivation

Healthcare systems worldwide are under increasing pressure due to rising patient volumes, limited medical personnel, and the growing demand for high-quality, accessible services. Traditional hospital workflows are largely manual, paper-based, and fragmented, often resulting in delays, errors, and inefficiencies.
The concept of a "smart hospital" leverages digital technology and automation to optimize healthcare delivery, improve patient experience, and enhance operational efficiency. With the proliferation of web-based systems and advancements in cloud computing, it is now possible to connect hospitals, patients, doctors, and administrative staff on a single, unified platform.
MedBridge is developed with this motivation: to integrate hospitals into a smart ecosystem that enables real-time tracking, management, and interaction. By combining intuitive UI/UX design, robust backend architecture, and automated processes, MedBridge aims to streamline hospital operations and provide patients with seamless healthcare access.

## 1.2 Problem Statement and Objectives

# Problem Statement

Despite the availability of digital tools, many hospitals still rely on legacy systems that operate in silos. There is a lack of synchronization between patient information, appointment scheduling, bed availability, and doctor consultation systems. Additionally, in emergency scenarios, the inefficiency of manual systems can lead to critical delays.

# Objectives

•	To develop a web-based platform that provides real-time hospital data including bed availability, doctor schedules, and patient records.
•	To implement role-based dashboards for patients, doctors, and hospital administrators.
•	To reduce the burden of manual data entry and improve accuracy through automated workflows.
•	To ensure scalability and customization based on individual hospital requirements.
•	To provide emergency appointment handling and intelligent search functionalities.

________________________________________

# 2. Literature Survey

## 2.1 Reviewed Existing Systems

Several hospital management systems exist today, ranging from proprietary ERP solutions to cloud-based patient engagement apps. Examples include:

•	e-Hospital by NIC (India): A government-initiated platform focusing on administrative processes in public hospitals. While it offers core functionalities, it lacks user-friendly interfaces and customization.
•	Apollo 24/7 & Practo: These platforms focus more on patient engagement and remote consultations but are limited in terms of backend hospital workflow integration.
•	Commercial ERP Systems: Solutions like Meditech, Cerner, and EPIC are widely used in private hospitals but are costly, complex, and not easily adaptable for smaller hospitals.

## 2.2 Limitations Identified

•	Lack of real-time data access, especially for bed and emergency resource availability.
•	No unified view for patients to interact with hospital systems.
•	High operational costs and technical complexity for deployment.
•	Poor accessibility and adaptability for Tier 2 and Tier 3 city hospitals.
These limitations underline the need for a scalable, web-based, open architecture solution like MedBridge.

________________________________________

# 3. Proposed System

## 3.1 System Overview

MedBridge is a smart hospital management system built on a three-tier architecture:
•	Presentation Layer: User interfaces for different roles, developed using HTML, CSS, Bootstrap, and JavaScript.
•	Application Layer: Java-based servlets and JSP pages deployed on Apache Tomcat handle business logic.
•	Database Layer: MySQL database to persist information such as user credentials, patient records, appointments, and hospital resources.

## 3.2 Features

•	Appointment Booking: Patients can search doctors by specialization and availability.
•	Bed Management: Live updates on bed status and allocation.
•	Emergency Handling: Prioritized workflows for emergency bookings.
•	User Role Dashboards: Customized access for admins, doctors, and patients.
•	Review System: Patients can leave reviews for doctors and hospitals.
•	Search Filters: By location, specialization, and hospital services.

## 3.3 Algorithmic Logic

•	Doctor Availability Check: A query engine that scans doctor schedules and flags available slots.
•	Bed Allocation Algorithm: A FIFO-based real-time system that assigns beds upon booking.
•	Emergency Prioritization: Emergency flags override default queues.
•	Session Handling: Secure session tracking for multi-role login architecture.

________________________________________

# 4. Requirements

## 4.1 Software Requirements

•	Frontend Technologies: HTML5, CSS3, JavaScript, Bootstrap
•	Backend Technologies: Java, JSP, Servlets
•	Database: MySQL
•	Server: Apache Tomcat 9.x
•	Development Tools: Eclipse IDE, Visual Studio Code, XAMPP
•	Version Control: Git

## 4.2 Hardware Requirements

•	Minimum 4GB RAM
•	Multi-core processor (Intel i5 or better)
•	100GB storage
•	Network adapter with stable internet access

________________________________________

# 5. Methodology

## 5.1 Workflow Design

The overall methodology follows the SDLC (Software Development Life Cycle) model, incorporating the following stages:
1.	Requirement Analysis: Stakeholder interviews, use case preparation
2.	Design: UI mockups, database schema design, system flowcharts
3.	Implementation: Frontend and backend coding
4.	Testing: Unit, Integration, and System Testing
5.	Deployment: Packaging WAR files, server configuration
6.	Maintenance: Error handling, documentation updates
   
## 5.2 Dataset Selection (Pending)

Though the platform architecture supports medical datasets, full implementation is pending. Future datasets may include:
•	Patient medical histories
•	Doctor performance analytics
•	Hospital resource usage
•	Symptom-to-treatment correlation datasets
Open-source or synthetic datasets will be used during the integration phase to simulate realistic data.
________________________________________

# 6. Module Descriptions

## Module 1: UI Prototype to Web Interface

•	UI wireframes were created using Figma.
•	Elements include login forms, dashboards, appointment calendars, and search filters.
•	Implemented in HTML/CSS with Bootstrap 5.
•	Responsive design for mobile and desktop viewing.
•	Integrated JavaScript for dynamic components.

## Module 2: Hospital Functionalities (Backend)

•	Appointment Scheduling: Java servlets query the MySQL database and return available doctors.
•	Patient Management: Add/edit/delete patient records.
•	Bed Allocation System: Tracks occupied vs. available beds.
•	Review Module: Collects and displays patient reviews.
•	Admin Panel: Controls hospital-wide settings and records.

## Module 3: Synchronization & Backend Logic

•	All modules are interlinked via JDBC.
•	Session management implemented for login persistence.
•	Real-time validation of form inputs.
•	Asynchronous refresh of dashboard data using AJAX.
•	Exception handling to prevent server crashes.
________________________________________

# 7. Outcome

## 7.1 Testing & Validation

•	Unit Testing: Every servlet and JSP component was tested in isolation.
•	Integration Testing: Combined testing of UI with backend and database.
•	Functional Testing: Verified against requirements checklist.
•	Security Testing: SQL injection, XSS, and session hijacking mitigation.

## 7.2 Documentation and Reporting

•	A comprehensive user manual is provided for admins.
•	Developer documentation covers deployment and module details.
•	All modules documented with flowcharts and pseudo code.

## 7.3 Deployment Preparation

•	WAR file generated for Apache Tomcat.
•	Database schema exported in SQL format.
•	Localhost and cloud-based testing completed.
•	Setup guide written for future deployment.
________________________________________

# 8. Conclusion and Future Work

## Conclusion:

MedBridge offers a practical solution to the challenges faced by traditional hospital management systems. By providing a centralized, user-friendly, and modular web platform, the system improves workflow efficiency, enhances patient satisfaction, and enables data-driven decision-making.

## Future Enhancements:

•	Mobile App Integration: Build Android/iOS apps for better accessibility.
•	AI Chatbot Integration: Suggest treatments or direct patients to specialists.
•	Big Data Analytics: Use hospital data for performance improvement.
•	Gesture-Based Accessibility: For differently-abled users using computer vision.
•	Full Dataset Integration: Populate with anonymized real-world data to simulate complete workflows.
________________________________________

# Appendices:

•	UI Screenshots
•	ER Diagram
•	Flowcharts
•	Sample SQL Queries
•	Figma Wireframe Links

# References:

1.	e-Hospital by NIC – www.nhm.gov.in
2.	Meditech – www.meditech.com
3.	Cerner – www.cerner.com
4.	Practo – www.practo.com
5.	Bootstrap – getbootstrap.com
6.	Java Servlet Docs – docs.oracle.com
