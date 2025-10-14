# **🧠 Phase 2: Core Functionality & System Integration Details**

This document details the implementation of the core business logic modules and the necessary Servlet interactions for full system operation.

## **1\. Prescription Module Workflow**

This module enables doctors to record diagnosis, prescribe medicine, and generate a patient history view.

| Servlet / Logic | Role | Key Functionality |
| :---- | :---- | :---- |
| **PrescribeServlet** | Doctor | **POST:** Receives form data (patient\_id, diagnosis, medicine\_list, dosage). Persists data to the Prescription and Prescription\_Details tables in MySQL via JDBC. |
| **ViewHistoryServlet** | Patient/Doctor | **GET:** Queries the database to retrieve all prescriptions linked to a specific patient\_id. **JSON response** is sent back to the frontend for dynamic rendering via AJAX. |
| **Data Integrity** | Database (Triggers/Views) | A **View** (Vw\_Patient\_Prescription) is created to simplify retrieving the full prescription record (patient info \+ medicine details). |

## **2\. Inventory Module Workflow**

This module tracks stock levels and handles medicine distribution, critical for pharmacists and store officers.

| Servlet / Logic | Role | Key Functionality |
| :---- | :---- | :---- |
| **StockUpdateServlet** | Store Officer | **POST:** Handles adding newly purchased inventory to the Medicine\_Stock table. |
| **DispenseServlet** | Pharmacist | **POST:** Reads an active prescription. On dispensing, updates the Medicine\_Stock table (decrements quantity). |
| **Low-Stock Alert** | Database (Trigger) | A MySQL **Trigger** is implemented on the Medicine\_Stock table. If a quantity update results in a stock level below a predefined threshold, an alert log is generated. |
| **Report Generation** | Store Officer | Logic to pull stock movement data and aggregate for the Report Module. |

## **3\. Chatbot Module (Rule-Based Logic)**

The AI module uses simple conditional logic within a dedicated Java class to provide first-level assistance.

| Component | Technology | Key Implementation Detail |
| :---- | :---- | :---- |
| **Chatbot Class** | **Java (ChatbotLogic.java)** | Contains predefined symptom-to-remedy mapping (e.g., if query contains "fever" and "body ache," suggest Paracetamol and rest). |
| **ChatServlet** | Java Servlet | **POST (AJAX):** Receives the user's plain text query. Passes the query to ChatbotLogic.java and returns the suggested response immediately to the frontend via AJAX. |
| **Frontend Integration** | HTML/JS/AJAX | The patient's dashboard uses an AJAX loop to send the query and receive the response, creating a smooth chat interface without page reloads. |

## **4\. System Integration and Robustness**

| Aspect | Implementation Focus | Rationale |
| :---- | :---- | :---- |
| **AJAX Integration** | All data-intensive displays (Prescription History, Stock View, Chatbot response) must use **AJAX** to update only the necessary parts of the dashboard. | Fulfills the abstract requirement for "Asynchronous refresh of dashboard data" for a modern user experience. |
| **Exception Handling** | Implement try-catch blocks within all Servlets (especially around JDBC calls) to log errors and prevent **server crashes**. | Ensures the system remains stable and available, even when facing database or network issues. |
| **Final Testing** | **Integration Testing:** Verify the flow from prescription generation to stock reduction is accurate and concurrent. | Confirms that all interlinked modules function correctly as a single system. |

