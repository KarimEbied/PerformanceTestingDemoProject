# PerformanceTestingDemoProject
## 📌 Overview
This repository contains a **JMeter test plan** for simulating a full user journey on the **PetStore website** and executing API performance tests for the **Restful Booker API**.

## 📋 Test Scenarios

### 1️⃣ **User Journey Simulation (PetStore)**
The JMeter script simulates a complete user journey:
- Navigate to  ([Petstore](https://petstore.octoperf.com/actions/Catalog.action))
- Click "Sign In" → "Register Now"
- Fill out the registration form
- Browse products → Select Fish → Choose Product & Item ID
- Add to cart and update quantity
- Proceed to checkout & confirm the order
- Validate order submission (Assertion: "Thank you, your order has been submitted.")

### 2️⃣ **API Testing ([Restful-booker](https://restful-booker.herokuapp.com/apidoc/index.html#api-Auth-CreateToken))**
The script covers the following API calls:
- **POST** `/auth` → Create authentication token
- **POST** `/booking` → Create a booking
- **GET** `/booking` → Retrieve all booking IDs
- **PUT** `/booking/{id}` → Update a booking using dynamic extraction

## ⚙️ Setup & Execution

### 🔹 Prerequisites
Ensure you have:
- [Apache JMeter](https://jmeter.apache.org/download_jmeter.cgi) installed
- JMeter Plugins Manager installed (optional but recommended)

### 🔹 Running the Test
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/jmeter-assignment.git
   cd jmeter-assignment
   ```
2. Open **JMeter_Assignment.jmx** in JMeter
3. Load the **Test_Data.csv** in `CSV Data Set Config`
4. Configure **Thread Group** parameters as needed
5. Click **Start** to execute the test

## ✅ Best Practices Implemented
- **Parameterization**: Replaced hardcoded values with variables and CSV data
- **Assertions**: Response text validation for correctness
- **Environment Independence**: Used HTTP Request Defaults
- **Realistic Delays**: Implemented Constant Timers
- **Session Handling**: Cache & Cookie Manager to maintain proper state
