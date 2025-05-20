# 📦 Test Plan – API Testing for Product Catalog

## 📘 Overview

| Field    | Details                      |
|----------|------------------------------|
| **Title**  | Product Catalog API Test Plan |
| **Module** | Catalog Management           |
| **Type**   | API Testing                 |
| **Tools**  | Postman, REST Assured (Java), Swagger |
| **Author** | Vinayak D.                  |
| **Date**   | May 2025                    |
| **Status** | ✅ In Progress / Completed  |

---

## 🎯 Objective

To ensure the Product Catalog APIs function as expected under various scenarios — including product creation, retrieval, update, and deletion — by validating response status codes, response bodies, data formats, and error handling.

---

## 🧪 Scope

### ✅ In Scope
- Testing REST endpoints related to Product Catalog  
- Positive and negative test cases  
- CRUD operations and data validation  
- Authentication (if applicable)  

### 🚫 Out of Scope
- UI testing  
- Performance or load testing  
- Database validation beyond API response  

---

## 🔍 Test Scenarios

| #  | Scenario                             | Method  | Endpoint              | Expected Result              |
|-----|------------------------------------|---------|-----------------------|-----------------------------|
| 1   | Get all products                   | GET     | /api/products         | 200 OK, list of products    |
| 2   | Get product by valid ID            | GET     | /api/products/{id}    | 200 OK, product details     |
| 3   | Get product by invalid ID          | GET     | /api/products/9999    | 404 Not Found               |
| 4   | Create new product with valid data | POST    | /api/products         | 201 Created, product object |
| 5   | Create product with missing fields | POST    | /api/products         | 400 Bad Request             |
| 6   | Update existing product            | PUT     | /api/products/{id}    | 200 OK, updated object      |
| 7   | Delete existing product            | DELETE  | /api/products/{id}    | 204 No Content              |
| 8   | Delete non-existing product        | DELETE  | /api/products/9999    | 404 Not Found               |
| 9   | Validate JSON schema of GET response | GET   | /api/products/{id}    | Schema match                |
| 10  | Unauthorized access to protected endpoint | GET | /api/products         | 401 Unauthorized            |

---

## 🧾 Sample Payloads

### ✅ Create Product – Request Body (POST /api/products)

json
{
  "name": "Wireless Mouse",
  "description": "Compact USB wireless mouse",
  "price": 799.99,
  "stock": 150,
  "category": "Electronics"
}

---

## 🧪 Test Data

| Name           | Price  | Stock | Expected Status |
|----------------|--------|-------|-----------------|
| Valid Product  | 599.99 | 100   | 201             |
| Missing Name   | 749.50 | 50    | 400             |
| Negative Price | -10.00 | 25    | 400             |
| Empty Category | 199.00 | 10    | 400             |

---

## 🔐 Authentication (If Required)

| Header Type  | Key           | Value           |
|--------------|---------------|-----------------|
| Bearer Token | Authorization | Bearer &lt;token&gt; |

---

## ⚙️ Environment Setup

| Component     | Configuration           |
|-------------- |-------------------------|
| Tool          | Postman / REST Assured   |
| Base URL      | https://api.myapp.com    |
| Auth Required | Yes (JWT Token)          |
| Data Format   | JSON                    |
| Schema Tool   | Postman / JSONSchema.net |

---

## ✅ Entry Criteria

- API server is up and running  
- Swagger or API docs are accessible  
- Auth token generated (if needed)  

---

## 🚫 Exit Criteria

- All test cases executed  
- Results documented  
- Bugs logged (if any)  

---

## 📤 Deliverables

- API Test Plan Document  
- Postman Collection or REST Assured scripts  
- JSON Schema for validation  
- Execution Summary Report  

---

## ✅ Status Reporting

| Metric           | Value                |
|------------------|----------------------|
| Total Test Cases | 10                   |
| Passed           | 8                    |
| Failed           | 2                    |
| Bugs Reported    | 2 (Invalid Error Msg)|
| Coverage         | 100% of endpoints    |

---

## 🔗 Related Links

- [Back to Test Plan Index](./index.md)

---

## 👨‍💻 Prepared By

**Name:** Pratik Joshi 

