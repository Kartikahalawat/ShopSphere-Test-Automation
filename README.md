# Selenium Test Automation Framework

A scalable and maintainable **Selenium WebDriver automation framework** built using **Java, TestNG, Cucumber, Maven, and Page Object Model (POM)**.

The framework is designed to demonstrate practical SDET automation practices including reusable page components, data-driven testing, BDD, parallel execution, retry handling, failure screenshots, and HTML reporting.

---

## 🚀 Tech Stack

* **Java 8**
* **Selenium WebDriver 4.3.0**
* **TestNG 6.14.3**
* **Cucumber 7.5.0**
* **Maven**
* **WebDriverManager**
* **Jackson Databind**
* **Extent Reports**
* **Git / GitHub**

---

## 🏗️ Framework Architecture

The framework follows the **Page Object Model (POM)** to separate test logic from application-specific UI interactions.

```text
                    ┌─────────────────────┐
                    │   Test Execution    │
                    │  TestNG / Cucumber  │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │    Test Classes     │
                    │  & Step Definitions │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │     Page Objects    │
                    │   UI Interactions   │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Selenium WebDriver│
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Web Application   │
                    └─────────────────────┘
```

---

## 📂 Project Structure

```text
SeleniumFrameworkDesign/
│
├── pom.xml
│
├── reports/
│   ├── index.html
│   ├── LoginErrorValidation.png
│   ├── ProductErrorValidation.png
│   └── submitOrder.png
│
├── src/
│   ├── main/
│   │   └── java/
│   │       └── rahulshettyacademy/
│   │           │
│   │           ├── AbstractComponents/
│   │           │   └── AbstractComponent.java
│   │           │
│   │           ├── pageobjects/
│   │           │   ├── LandingPage.java
│   │           │   ├── ProductCatalogue.java
│   │           │   ├── CartPage.java
│   │           │   ├── CheckoutPage.java
│   │           │   ├── ConfirmationPage.java
│   │           │   └── OrderPage.java
│   │           │
│   │           └── resources/
│   │               ├── ExtentReporterNG.java
│   │               └── GlobalData.properties
│   │
│   └── test/
│       └── java/
│           │
│           ├── cucumber/
│           │   ├── SubmitOrder.feature
│           │   ├── ErrorValidations.feature
│           │   └── TestNGTestRunner.java
│           │
│           └── rahulshettyacademy/
│               ├── data/
│               │   ├── DataReader.java
│               │   └── PurchaseOrder.json
│               │
│               ├── stepDefinitions/
│               │   └── StepDefinitionImpl.java
│               │
│               ├── TestComponents/
│               │   ├── BaseTest.java
│               │   ├── Listeners.java
│               │   └── Retry.java
│               │
│               └── tests/
│                   ├── SubmitOrderTest.java
│                   └── ErrorValidationsTest.java
│
├── testSuites/
│   ├── testng.xml
│   ├── Purchase.xml
│   └── ErrorValidationTests.xml
│
└── target/
```

---

# ✨ Key Features

## 1. Page Object Model

The framework follows the **Page Object Model** design pattern.

Each application page has its own class containing:

* Locators
* Page-specific actions
* Reusable methods
* Page navigation

Example:

```java
LandingPage
    ↓
ProductCatalogue
    ↓
CartPage
    ↓
CheckoutPage
    ↓
ConfirmationPage
```

This keeps test cases clean and improves framework maintainability.

---

## 2. Reusable Test Components

Common functionality is centralized in reusable components such as:

* `BaseTest`
* `AbstractComponent`
* `Listeners`
* `Retry`

The `BaseTest` class handles common WebDriver initialization and test setup/teardown.

---

## 3. Data-Driven Testing

Test data is externalized into JSON instead of hard-coding it inside test cases.

```text
PurchaseOrder.json
```

The framework uses **Jackson Databind** to read JSON test data.

TestNG `DataProvider` is then used to execute the same test flow with different data.

Example:

```java
@Test(dataProvider = "getData", groups = {"Purchase"})
public void submitOrder(HashMap<String, String> input) {
    // Test execution
}
```

---

## 4. TestNG Groups

Tests are organized into logical groups.

Examples:

```text
Purchase
ErrorHandling
```

This allows specific categories of tests to be executed independently.

---

## 5. Retry Mechanism

The framework includes a custom TestNG retry implementation.

```java
retryAnalyzer = Retry.class
```

This allows failed tests to be automatically retried based on the configured retry logic.

---

## 6. Failure Screenshot Capture

The framework captures screenshots when a test fails.

Screenshots are stored under:

```text
reports/
```

Example:

```text
LoginErrorValidation.png
ProductErrorValidation.png
submitOrder.png
```

The screenshots can also be attached to the Extent HTML report.

---

## 7. Extent Reports

The framework uses **Extent Reports** for HTML-based test execution reporting.

Report location:

```text
reports/index.html
```

The report provides visibility into:

* Passed tests
* Failed tests
* Test execution details
* Exceptions
* Failure screenshots

---

## 8. Cucumber BDD

The framework supports **Behavior Driven Development (BDD)** using Cucumber.

Feature files:

```text
SubmitOrder.feature
ErrorValidations.feature
```

The scenarios are implemented through step definitions in:

```text
StepDefinitionImpl.java
```

The Cucumber execution is handled by:

```text
TestNGTestRunner.java
```

---

# 🧪 Test Scenarios

## Positive Test Flow

The framework automates an end-to-end purchase workflow:

```text
Login
  ↓
Select Product
  ↓
Add Product to Cart
  ↓
Validate Cart
  ↓
Proceed to Checkout
  ↓
Select Country
  ↓
Submit Order
  ↓
Validate Order Confirmation
  ↓
Validate Order History
```

---

## Negative Test Scenarios

The framework also validates application error handling.

### Invalid Login

Validates the application error message for incorrect credentials.

Expected message:

```text
Incorrect email or password.
```

### Product Validation

Validates product availability and expected product behavior during the purchase flow.

---

# ⚙️ Configuration

Browser and framework configuration is maintained through:

```text
GlobalData.properties
```

The browser can also be provided through the command line.

Example:

```bash
mvn test -Dbrowser=chrome
```

For headless Chrome:

```bash
mvn test -Dbrowser=chromeheadless
```

Firefox can be selected using:

```bash
mvn test -Dbrowser=firefox
```

---

# ▶️ How to Run

## Prerequisites

Make sure the following are installed:

* Java JDK 8+
* Maven
* Git
* Chrome / Firefox / Edge
* IntelliJ IDEA / Eclipse / VS Code

Verify Java:

```bash
java -version
```

Verify Maven:

```bash
mvn -version
```

---

## Clone the Repository

```bash
git clone <repository-url>
```

Navigate to the project:

```bash
cd SeleniumFrameworkDesign
```

---

## Run All Tests

```bash
mvn test
```

---

## Run Regression Suite

```bash
mvn test -PRegression
```

---

## Run Purchase Tests

```bash
mvn test -PPurchase
```

---

## Run Error Validation Tests

```bash
mvn test -PErrorValidation
```

---

## Run Cucumber Tests

```bash
mvn test -PCucumberTests
```

---

# 🔄 Test Execution Lifecycle

```text
@BeforeMethod
      ↓
Initialize WebDriver
      ↓
Load Configuration
      ↓
Launch Application
      ↓
Execute Test
      ↓
Test Passed?
   ↙       ↘
 YES       NO
 ↓          ↓
Report   Screenshot
            ↓
         Exception
            ↓
        Extent Report
      ↓
@AfterMethod
      ↓
Close Browser
```

---

# 📊 Reporting

After execution, the Extent report can be opened from:

```text
reports/index.html
```

Cucumber execution generates:

```text
target/cucumber.html
```

Failure screenshots are stored inside:

```text
reports/
```

---

# ⚡ Parallel Execution

The framework supports TestNG parallel execution through the suite configuration.

Example:

```xml
<suite parallel="tests" thread-count="5">
```

This provides the ability to execute independent test groups concurrently and can help reduce overall execution time.

For larger-scale parallel execution, WebDriver isolation using `ThreadLocal<WebDriver>` can be introduced.

---

# 🧩 Design Practices Used

The framework demonstrates the following automation engineering practices:

* Page Object Model
* Separation of test and UI interaction logic
* Reusable components
* Centralized WebDriver setup
* Externalized configuration
* Data-driven testing
* JSON-based test data
* TestNG DataProvider
* TestNG Groups
* TestNG Listeners
* Retry Analyzer
* Cucumber BDD
* Explicit waits
* Failure screenshot capture
* HTML reporting
* Maven profiles
* Parallel test execution

---

# 🔐 Test Data & Credentials

The project uses demo application credentials for automation.

For real-world projects, sensitive credentials should **not** be committed to source control.

Recommended approach:

```text
Environment Variables
        ↓
Configuration
        ↓
Test Framework
        ↓
Test Execution
```

For production frameworks, credentials can be managed through:

* Environment variables
* CI/CD secrets
* Secret management platforms
* Encrypted configuration

---

# 📈 Possible Future Enhancements

The framework can be further extended with:

* Selenium Grid
* Docker-based execution
* Jenkins / GitHub Actions CI/CD
* Cross-browser execution
* Thread-safe WebDriver management
* API automation using REST Assured
* Allure reporting
* Log4j2 / SLF4J logging
* Video recording for failed tests
* Environment-specific configuration
* Parallel DataProvider execution
* Cloud execution using BrowserStack / LambdaTest
* Automated test execution through CI/CD pipelines

---

# 🎯 Framework Highlights

This project demonstrates practical **SDET / Test Automation Engineering** concepts:

```text
Java
  +
Selenium WebDriver
  +
Page Object Model
  +
TestNG
  +
Cucumber
  +
Data-Driven Testing
  +
Maven
  +
Retry & Listeners
  +
Failure Screenshots
  +
Extent Reports
```

The framework is designed with a focus on **reusability, maintainability, scalability, and clean separation of test responsibilities**.

---

# 👨‍💻 Author

## Kartik Ahalawat

**SDET / Test Automation Engineer**

**Java | Selenium | Playwright | API Testing | SQL | CI/CD**

---

## 📄 License

This project is created for **learning, portfolio demonstration, and test automation practice**.

If you reuse this framework, update the application URL, test data, credentials, and project-specific configuration accordingly.
