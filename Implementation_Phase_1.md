# **🛠️ Phase 1: Foundation and Core User System Details**

This document provides granular details for completing Phase 1: establishing the MedBridge 3-Tier architecture, setting up the database, and implementing the core User Module.

## **1\. Architectural Setup (Java/Tomcat)**

| Component | Task Detail | Notes |
| :---- | :---- | :---- |
| **Project Setup** | Initialize the Java Web Application project in NetBeans (with **Maven** or standard structure). | Ensure servlet-api.jar and mysql-connector-j.jar (via **MySQL Connector/J**) are included as dependencies. |
| **Server Config** | Deploy the project context to **Apache Tomcat 6**. | The deployment path must be correctly configured to ensure Servlets are accessible via REST-like URL mappings (e.g., /medbridge/login). |
| **Base Class** | Create a DatabaseConnectionManager.java utility class to centralize the **JDBC** connection logic (connection strings, credentials). | This class ensures connection reuse and handles initial connectivity exceptions. |

## **2\. Data Layer Schema (medbridge\_schema.sql)**

The database requires several core tables to support user roles and authentication. All tables must use appropriate primary and foreign keys.

| Table Name | Purpose | Key Fields (Example) |
| :---- | :---- | :---- |
| **User** | Central authentication table for all roles. | user\_id (PK), username, password\_hash, role\_id (FK), hint\_question, hint\_answer |
| **Role** | Stores system roles (Doctor, Pharmacist, Patient, Admin). | role\_id (PK), role\_name |
| **Patient** | Stores patient-specific demographics (General Users). | patient\_id (PK, FK from User), name, contact, address, dob |
| **Doctor** | Stores doctor specialization and availability. | doctor\_id (PK, FK from User), specialization, clinic\_hours |
| **Staff** | Base table for Pharmacists/Store Officers. | staff\_id (PK, FK from User), department |
| **Medicine** | Catalog of all medicines in the hospital. | medicine\_id (PK), name, manufacturer, unit\_price |

## **3\. Presentation Layer (Frontend Structure)**

All interfaces must be **responsive** (using Bootstrap 5\) and leverage vanilla **JavaScript** for form handling.

| File / Component | Purpose | Key Elements |
| :---- | :---- | :---- |
| login.html | Secure Login for all user roles. | Form validation via JavaScript; hint\_question link for password retrieval. |
| patient\_dashboard.html | Landing page for patients. | Menu links to **Prescription History**, **Chatbot**, **Diet Advice**. |
| doctor\_dashboard.html | Landing page for doctors. | Menu links to **New Prescription Form**, **Patient Search**. |
| admin\_dashboard.html | Landing page for administrative users. | Links to **User Management** (Create/Edit), **System Settings**. |
| style.css | Core application styling. | Customizations to Bootstrap components; ensuring visual consistency across dashboards. |

## **4\. User Module (Authentication Backend)**

The primary focus is the LoginServlet which sits in the Business Logic Layer.

| Servlet/Logic | HTTP Method | Key Action |
| :---- | :---- | :---- |
| **LoginServlet** | POST | Receives username/password, authenticates against the User table, retrieves role\_id, and redirects to the appropriate dashboard. |
| **LogoutServlet** | GET | Invalidates the current user session and redirects to login.html. |
| **Session Logic** | Java Servlets | Uses HttpSession object to store the user\_id and role\_name. This is checked on every subsequent request to ensure **login persistence** and prevent unauthorized access. |

