# Excel-Driven API Automation Framework

This project is a **JUnit 5-based API Testing Framework** that uses **Excel as a data source** to dynamically execute REST API requests and validate responses. It leverages the power of **RestAssured** for HTTP interactions and **Allure Reports** for rich visual reporting.

---

## Features

- 🚀 Data-driven testing using Excel
- 🔁 Supports multiple HTTP methods (GET, POST, PUT, DELETE)
- 🔐 Header and body customization per test case
- ✅ Status code assertions
- 📊 Allure Report integration
- 📂 Easy to extend and configure

---

---

## 📁 Excel Format (`test-data.xlsx`)

| Method | Endpoint      | Header             | Body                   | ExpectedStatus |
|--------|---------------|--------------------|------------------------|----------------|
| GET    | /api/users/2  | application/json   |                        | 200            |
| POST   | /api/users    | application/json   | {"name":"Hari"}        | 201            |
| PUT    | /api/users/2  | application/json   | {"job":"Engineer"}     | 200            |
| DELETE | /api/users/2  | application/json   |                        | 204            |

---

## ⚙️ How It Works

1. `ExcelArgumentsProvider` reads each row from the Excel sheet.
2. The test method `testApiRequestsFromExcel` runs once for each row.
3. The test sends API requests dynamically based on Excel input.
4. Response status codes are validated against expected ones.
5. Allure annotations are used for reporting and steps.

---

## 🧰 Technologies Used

- Java 21 (Corretto)
- JUnit 5 (Jupiter)
- RestAssured
- Apache POI (for reading Excel)
- Maven
- Allure Reporting
- IntelliJ IDEA

---

# Getting Started

### 1. Clone the Repository


git clone https://github.com/your-username/FlowCheck.git
cd FlowCheck


###  2. Update config.properties
Inside src/main/resources/config.properties:

properties
Copy
Edit
baseURI=https://reqres.in
Replace with your actual API base URL.

### 3. Run Tests
Via Maven:

bash
Copy
Edit
mvn clean test
Or run using IntelliJ's JUnit test runner.

### 4. View Allure Reports
Step 1: Install Allure CLI
Follow the Allure Installation Guide

Step 2: Generate and open the report
bash
Copy
Edit
allure serve target/allure-results