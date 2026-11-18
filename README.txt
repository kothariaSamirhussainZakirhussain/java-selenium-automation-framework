# 🚀 Selenium Automation Framework

## 📌 Overview

This repository contains a **robust, enterprise-ready Selenium automation framework** built using **Java, Selenium 4, TestNG, and Maven**, with support for:

* ✅ UI Automation (Selenium WebDriver)
* ✅ API Automation (Rest-Assured)
* ✅ Data-Driven Testing (Excel + TestNG DataProvider)
* ✅ Parallel Execution (ThreadLocal + TestNG)
* ✅ Advanced Reporting (Extent Reports + Allure)
* ✅ Retry Mechanism for flaky actions

This framework is designed following **industry best practices** and is suitable for **SDET / QA Automation roles**.

---

## 🧱 Tech Stack

| Tool / Technology | Usage                               |
| ----------------- | ----------------------------------- |
| Java 17           | Programming language                |
| Selenium 4        | UI Automation                       |
| TestNG            | Test execution & parallelization    |
| Maven             | Build & dependency management       |
| Rest-Assured      | API testing    |
| Extent Reports    | HTML reporting                      |
| Allure            | Advanced reporting                  |
| Apache POI        | Excel data handling                 |
| Selenium Grid     | Remote & parallel browser execution |
| Log4j2            | Logging                             |

---

## 📁 Project Structure

```
Seleniumdemo7/
│
├── src/
│
│   ├── main/
│   │   ├── java/
│   │   │
│   │   │   ├── api/
│   │   │   │   └── Testbase.java
│   │   │   │       └─ Base class for API testing
│   │   │   │          (common API setup,
│   │   │   │           request/response handling,
│   │   │   │           shared API configurations)
│   │   │
│   │   │   ├── base/
│   │   │   │   ├── BrowserSetup.java
│   │   │   │   │   └─ Handles browser-level setup
│   │   │   │      (browser launch,
│   │   │   │       maximize window,
│   │   │   │       navigation to application URL)
│   │   │   │
│   │   │   │   └── My_Screen_Recorder.java
│   │   │   │       └─ Handles screen recording functionality
│   │   │   │          (start/stop screen recording
│   │   │   │           during test execution)
│   │   │
│   │   │   ├── pages/
│   │   │   │   └── LoginPage.java
│   │   │   │       └─ Page Object Model class for Login page
│   │   │   │          (username, password, login button locators,
│   │   │   │           login-related actions,
│   │   │   │           uses ActionUtils for interactions)
│   │   │
│   │   │   ├── utils/
│   │   │   │   ├── ActionUtils.java
│   │   │   │   │   └─ Reusable Selenium UI actions
│   │   │   │      (sendKeys, clear, click,
│   │   │   │       validations,
│   │   │   │       retry integration,
│   │   │   │       logging & reporting)
│   │   │   │
│   │   │   │   ├── BrowserUtils.java
│   │   │   │   │   └─ Browser-related helper utilities
│   │   │   │      (browser-specific actions,
│   │   │   │       utility wrappers over WebDriver)
│   │   │   │
│   │   │   │   ├── CheckUtils.java
│   │   │   │   │   └─ Validation & verification utilities
│   │   │   │      (element displayed checks,
│   │   │   │       boolean validations,
│   │   │   │       reusable assertions)
│   │   │   │
│   │   │   │   ├── CommonUtils.java
│   │   │   │   │   └─ Common reusable helper methods
│   │   │   │      (generic utilities shared across framework)
│   │   │   │
│   │   │   │   ├── ConfigReader.java
│   │   │   │   │   └─ Reads configuration values
│   │   │   │      (loads properties files,
│   │   │   │       environment handling,
│   │   │   │       provides config values to framework)
│   │   │   │
│   │   │   │   ├── DataUtils.java
│   │   │   │   │   └─ Data-related helper utilities
│   │   │   │      (data handling logic used by tests)
│   │   │   │
│   │   │   │   ├── DropdownandcheckboxUtils.java
│   │   │   │   │   └─ Handles dropdowns and checkboxes
│   │   │   │      (select, deselect, multi-select logic)
│   │   │   │
│   │   │   │   ├── DropdownUtils.java
│   │   │   │   │   └─ Dropdown-specific utilities
│   │   │   │      (select by text, value, index)
│   │   │   │
│   │   │   │   ├── ExcelUtils.java
│   │   │   │   │   └─ Excel utility using Apache POI
│   │   │   │      (read Excel files,
│   │   │   │       fetch data for DataProviders)
│   │   │   │
│   │   │   │   ├── FileUploadUtils.java
│   │   │   │   │   └─ Handles file upload functionality
│   │   │   │      (upload files using Selenium logic)
│   │   │   │
│   │   │   │   ├── JsonReader.java
│   │   │   │   │   └─ Reads JSON test data
│   │   │   │      (parse JSON files,
│   │   │   │       supply data to tests)
│   │   │   │
│   │   │   │   ├── ReportUtils.java
│   │   │   │   │   └─ Central reporting utility
│   │   │   │      (Extent Reports,
│   │   │   │       Allure integration,
│   │   │   │       ThreadLocal test handling,
│   │   │   │       screenshot on failure)
│   │   │   │
│   │   │   │   ├── RetryUtils.java
│   │   │   │   │   └─ Retry mechanism for flaky steps
│   │   │   │      (retry with configurable attempts,
│   │   │   │       wait between retries)
│   │   │   │
│   │   │   │   ├── Utilities.java
│   │   │   │   │   └─ General-purpose helper utilities
│   │   │   │      (screenshots,
│   │   │   │       random data generation)
│   │   │   │
│   │   │   │   └── WaitUtils.java
│   │   │   │       └─ Custom wait utilities
│   │   │   │          (hard waits and reusable wait logic)
│   │   │
│   │   ├── resources/

│   │   │   ├── data/
│   │   │   │   ├── Excels/
│   │   │   │   │   ├── file.xlsx
│   │   │   │   │   └── Logindataprovider.xlsx
│   │   │   │   │       └─ Excel test data files
│   │   │   │
│   │   │   │   └── Jsons/
│   │   │   │       └── Normalfile.json
│   │   │   │           └─ JSON test data file
│   │   │   │
│   │   │   ├── environments/
│   │   │   │   ├── LiveEnvironment.properties
│   │   │   │   └── QAEnvironment.properties
│   │   │   │       └─ Environment-specific configuration files
│   │   │
│   │   │   └── log4j2.properties
│   │   │       └─ Log4j2 logging configuration
│
│   ├── test/
│   │   ├── java/
│   │   │   ├── apitest/
│   │   │   │   └── User_Api_Tests.java
│   │   │   │       └─ API test cases
│   │   │   │          (validates API responses,
│   │   │   │           uses Testbase)
│   │   │
│   │   │   ├── pagestest/
│   │   │   │   ├── Login.java
│   │   │   │   │   └─ UI test cases for Login functionality
│   │   │   │
│   │   │   │   ├── LoginExceldataprovider.java
│   │   │   │   │   └─ Login tests using Excel DataProvider
│   │   │   │
│   │   │   │   └── LoginJson.java
│   │   │   │       └─ Login tests using JSON test data
│   │   │
│   │   ├── resources/
│   │   │   ├── config.properties
│   │   │   │   └─ Test execution configuration
│   │   │
│   │   │   ├── regression.xml
│   │   │   │   └─ TestNG regression suite file
│   │   │
│   │   │   ├── smoke.xml
│   │   │   │   └─ TestNG smoke suite file
│   │   │
│   │   │   ├── testng-All_in_one.xml
│   │   │   │   └─  Combined TestNG suite configuration
│   │   │   │ 
│   │   │   └── testng-master.xml
│   │   │       └─  Combined TestNG suite 
│
├── Reports/
│   └─ Generated Extent reports and screenshots
|
|
├── Maven_&_Allure_Commands_to_run
│   └─ Commands to run xmls and open allure reports
│
├── pom.xml
│   └─ Maven project configuration
│
└── README.md
    └─ Framework documentation
```

---

## ⚙️ Framework Key Features

### 🔹 1. Parallel Execution (Thread-Safe)

* Uses `ThreadLocal<WebDriver>`
* Supports parallel execution at:

  * Methods
  * Classes
  * Tests level
* Prevents driver & log collision

---

### 🔹 2. Reporting

#### 📊 Extent Reports

* One consolidated HTML report
* Screenshots on failure
* Thread-safe reporting using `ThreadLocal<ExtentTest>`

#### 📈 Allure Reports

* Step-level reporting
* Screenshots attached on failure
* API & UI step visibility

---

### 🔹 3. Retry Mechanism

* Custom retry logic for flaky UI actions
* Configurable retry count via `config.properties`
* Centralized retry handling

---

### 🔹 4. Data-Driven Testing

* Excel-based test data
* TestNG `@DataProvider`
* Parallel-safe execution with multiple datasets

---

### 🔹 5. Logging

* Log4j2 based logging
* Thread name + Test context included
* Clean and readable logs during parallel runs

Example log:

```
[TestNG-test-RegressionTests-1] [Valid Login Test] Successfully clicked Login
```

---

### 📄 config.properties

```
src/test/resources/config.properties
```

```properties
Environment=QA
headless=false
Waittime=5
color=blue
Recording=no
retry.count=3
reuseBrowser=no
useSeleniumGrid=no
seleniumGridUrl=http://localhost:4444/wd/hub
```

---

### ▶️ Local Execution

```properties
useSeleniumGrid=no
```

* Runs on local machine
* Local browser is used
* Browser UI opens if `headless=false`

---

## ▶️ How to Run Tests

### 🔹 Run Locally

```bash
mvn clean test
```

Run specific TestNG XML:

```bash
mvn clean test -DsuiteXmlFile=src/test/resources/regression.xml
mvn clean test -DsuiteXmlFile=src/test/resources/smoke.xml
mvn clean test -DsuiteXmlFile=src/test/resources/testng-All_in_one.xml
```

---

## 📂 Reports

Extent reports are generated at:

```
Reports/ExtentReport_<timestamp>/ExtentReport.html
```

Allure reports (if enabled):

```bash
allure serve allure-results
```

---

## ⚠️ Known Warnings (Expected)

```
WARNING: Unable to find CDP implementation matching <Chrome_Version>
```

* This is a **Selenium compatibility warning**
* Does NOT affect test execution
* Safe to ignore or suppress via logging config

---

## 🧠 Best Practices Followed

* Clean Page Object Model (POM)
* Single responsibility for utilities
* No static WebDriver usage
* Thread-safe reporting & logging

---

## 🎯 Suitable For

* SDET / QA Automation Engineers
* Parallel UI automation projects

---
