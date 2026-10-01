# 🛒 ShopSphere Test Automation

> **A scalable Java-based test automation framework designed to validate critical e-commerce workflows through maintainable, reusable, and structured automated tests.**

[![Java](https://img.shields.io/badge/Java-17%2B-orange?logo=openjdk)](https://www.java.com/)
[![Maven](https://img.shields.io/badge/Maven-Build-red?logo=apachemaven)](https://maven.apache.org/)
[![Selenium](https://img.shields.io/badge/Selenium-Web%20Automation-43B02A?logo=selenium)](https://www.selenium.dev/)
[![TestNG](https://img.shields.io/badge/TestNG-Test%20Framework-FF6F00)](https://testng.org/)
[![Git](https://img.shields.io/badge/Git-Version%20Control-F05032?logo=git)](https://git-scm.com/)

---

## 📌 Project Overview

**ShopSphere Test Automation** is a Java-based test automation project created to demonstrate a structured approach to testing an e-commerce application.

The framework focuses on building reusable automation components, organizing test scenarios into maintainable suites, generating execution reports, and following automation best practices that can be extended as application coverage grows.

### 🎯 Objectives

* Automate critical e-commerce user workflows
* Build reusable and maintainable test components
* Separate test logic from test data and configuration
* Organize tests into executable suites
* Generate execution reports for test analysis
* Establish a foundation that can be extended for CI/CD execution

---

## ✨ Key Highlights

| Area                  | Implementation                          |
| --------------------- | --------------------------------------- |
| 🧪 Test Automation    | Automated UI test scenarios             |
| ☕ Language            | Java                                    |
| 🌐 Browser Automation | Selenium WebDriver                      |
| 🔬 Test Framework     | TestNG                                  |
| 📦 Build Management   | Maven                                   |
| 📊 Reporting          | Automated execution reports             |
| 🗂️ Test Organization | Test suites and structured test classes |
| 🔄 Maintainability    | Reusable automation components          |
| 🛠️ Version Control   | Git                                     |

---

## 🧪 Testing Scope

The framework is designed around common e-commerce workflows such as:

* 🔐 User authentication
* 🛍️ Product navigation
* 🔎 Product search
* 📦 Product selection
* 🛒 Cart operations
* 💳 Checkout workflows
* 📋 Order-related validations
* ❌ Negative and validation scenarios

> The test coverage can be expanded as additional application functionality is introduced.

---

## 🏗️ Framework Structure

```text
ShopSphere-Test-Automation/
│
├── src/
│   └── test/
│       └── java/
│           └── ...
│
├── testSuites/
│   └── ...
│
├── reports/
│   └── ...
│
├── test-output/
│   └── ...
│
├── pom.xml
├── .gitignore
└── README.md
```

### 📂 Directory Purpose

**`src/test/java`**

Contains the Java automation code and test implementations.

**`testSuites`**

Contains TestNG suite configurations used to organize and execute selected groups of tests.

**`reports`**

Contains generated test execution reports.

**`test-output`**

Contains TestNG execution output and related test artifacts.

**`pom.xml`**

Defines project dependencies, build configuration, and Maven-based test execution.

---

## ⚙️ Technology Stack

### ☕ Programming

* Java

### 🌐 UI Automation

* Selenium WebDriver

### 🧪 Test Execution

* TestNG

### 📦 Build & Dependency Management

* Maven

### 🔧 Development Tools

* Git
* GitHub
* Eclipse / IntelliJ IDEA

---

## 🚀 Getting Started

### Prerequisites

Make sure the following are installed:

* Java JDK
* Maven
* Git
* A supported web browser
* IDE such as IntelliJ IDEA or Eclipse

Verify the installations:

```bash
java -version
mvn -version
git --version
```

---

## 📥 Clone the Repository

```bash
git clone https://github.com/Kartikahalawat/ShopSphere-Test-Automation.git
```

Navigate into the project:

```bash
cd ShopSphere-Test-Automation
```

---

## 📦 Install Dependencies

Maven manages the project dependencies defined in `pom.xml`.

```bash
mvn clean install
```

---

## ▶️ Execute Tests

Run the automated test suite using Maven:

```bash
mvn test
```

You can also execute the required TestNG suite directly through your IDE or configured Maven/TestNG configuration.

---

## 📊 Test Reports

After execution, generated artifacts are available under the project's reporting/output directories.

```text
reports/
test-output/
```

These reports can be used to review:

* Passed tests
* Failed tests
* Skipped tests
* Execution details
* Test execution results

---

## 🧩 Automation Design Principles

The framework is structured with maintainability and reusability in mind.

### ♻️ Reusable Components

Common automation operations should be centralized and reused instead of duplicating browser interaction logic across individual test cases.

### 🧪 Independent Test Scenarios

Tests should remain as independent as possible so that individual scenarios can be executed, debugged, and maintained without unnecessary dependencies.

### 📋 Test Suite Organization

TestNG suites provide a structured way to group related scenarios and control which tests are executed.

### 📊 Execution Visibility

Test reports and execution artifacts provide visibility into automation results and help identify failures during debugging.

---

## 🔄 Automation Workflow

```text
             ┌──────────────────────┐
             │   Test Scenario      │
             └──────────┬───────────┘
                        │
                        ▼
             ┌──────────────────────┐
             │    TestNG Suite      │
             └──────────┬───────────┘
                        │
                        ▼
             ┌──────────────────────┐
             │ Selenium WebDriver   │
             └──────────┬───────────┘
                        │
                        ▼
             ┌──────────────────────┐
             │  ShopSphere Web App  │
             └──────────┬───────────┘
                        │
                        ▼
             ┌──────────────────────┐
             │ Assertions & Results │
             └──────────┬───────────┘
                        │
                        ▼
             ┌──────────────────────┐
             │   Test Reports       │
             └──────────────────────┘
```

---

## 📈 Future Enhancements

The framework can be further extended with additional automation capabilities:

* 🔹 Page Object Model (POM)
* 🔹 Data-driven testing
* 🔹 Cross-browser execution
* 🔹 Parallel test execution
* 🔹 Parameterized TestNG tests
* 🔹 API automation with REST Assured
* 🔹 Advanced HTML reporting
* 🔹 Jenkins CI/CD integration
* 🔹 Dockerized test execution
* 🔹 Screenshot capture on failures
* 🔹 Environment-specific configuration
* 🔹 Playwright-based automation

---

## 🧪 Example Test Execution

A typical automation flow follows:

```text
Launch Browser
      ↓
Navigate to Application
      ↓
Perform User Action
      ↓
Validate Expected Result
      ↓
Capture Test Result
      ↓
Generate Report
```

---

## 📚 What This Project Demonstrates

This project demonstrates practical experience with:

* Selenium WebDriver automation
* Java-based test development
* TestNG test execution
* Maven project management
* Test suite organization
* Automated validation
* Test reporting
* Reusable automation design
* Git-based project management

---

## 🤝 Contributing

Contributions and suggestions are welcome.

1. Fork the repository
2. Create a feature branch

```bash
git checkout -b feature/new-test-scenario
```

3. Commit your changes

```bash
git commit -m "Add new automation scenario"
```

4. Push the branch

```bash
git push origin feature/new-test-scenario
```

5. Open a Pull Request

---

## 👨‍💻 Author

### Kartik Ahalawat

**SDET | Quality Engineering & Test Automation | Java | Selenium | Playwright | API Testing**

🔗 **GitHub:**
https://github.com/Kartikahalawat

---

## ⭐ Support

If you find this project useful for learning or exploring test automation, consider giving the repository a ⭐.

---

### 📌 Project Status

**Active Development 🚀**

The framework is being continuously enhanced with additional automation patterns, test coverage, and modern testing practices.

