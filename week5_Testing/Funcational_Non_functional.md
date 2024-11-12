# Functional and Non-Functional Testing in Software Quality Assurance

Testing is a critical component of Software Quality Assurance (SQA) and is broadly categorized into **Functional** and **Non-Functional Testing**. Each type has its own objectives and techniques to ensure that software performs as intended and meets user expectations.

![Software Testing](/Images/softwareTesting.gif)

## Table of Contents
- [Introduction to Functional Testing](#introduction-to-functional-testing)
  - [Types of Functional Testing](#types-of-functional-testing)
- [Introduction to Non-Functional Testing](#introduction-to-non-functional-testing)
  - [Types of Non-Functional Testing](#types-of-non-functional-testing)
- [Differences Between Functional and Non-Functional Testing](#differences-between-functional-and-non-functional-testing)
- [Common Tools for Functional Testing](#common-tools-for-functional-testing)
- [Common Tools for Non-Functional Testing](#common-tools-for-non-functional-testing)
- [Conclusion](#conclusion)

---

## Introduction to Functional Testing

Functional Testing is a type of software testing that ensures each function of an application operates according to the specified requirements. It focuses on testing individual functions by providing specific inputs and comparing the output to expected results.

![Software Test](/Images/functionalvsnone.png)


### Types of Functional Testing

1. **Unit Testing**
   - **Description**: Tests individual components or units in isolation.
   - **Objective**: Verify that each unit of code works correctly.
   - **Example**: Testing a single function in a class to confirm it returns the correct value.
     > ![Unit Test](/Images/unitTest1.jpg)

2. **Integration Testing**
   - **Description**: Tests the interaction between integrated units or modules.
   - **Objective**: Ensure modules work together as expected.
   - **Example**: Testing how the login module interacts with the user dashboard.

3. **System Testing**
   - **Description**: Testing the complete and integrated software system.
   - **Objective**: Validate that the system meets all specified requirements.
   - **Example**: Running test cases across the entire application to confirm overall functionality.

4. **Acceptance Testing**
   - **Description**: Testing to verify that the system meets user needs and requirements.
   - **Objective**: Ensure the software is ready for delivery.
   - **Example**: User testing to confirm that all features work as expected before final release.

5. **Regression Testing**
   - **Description**: Re-running functional and non-functional tests to ensure existing features are not affected by recent changes.
   - **Objective**: Maintain product stability by detecting unintended side effects.
   - **Example**: Retesting core functions after a bug fix or new feature implementation.

---

## Introduction to Non-Functional Testing

Non-Functional Testing evaluates the performance, usability, reliability, and other non-functional aspects of an application. Unlike functional testing, it does not test specific features or functions but rather the system’s overall behavior.

### Types of Non-Functional Testing

1. **Performance Testing**
   - **Description**: Measures how the system performs under various conditions.
   - **Objective**: Ensure the system is responsive, stable, and efficient.
   - **Example**: Testing how quickly a web application responds under heavy traffic.
   
 > ![Unit Test](/Images/perfomanceTest1.jpg)

2. **Load Testing**
   - **Description**: Testing the system’s performance under expected loads.
   - **Objective**: Verify the system can handle expected user volume.
   - **Example**: Simulating 100 concurrent users on an e-commerce website.

3. **Stress Testing**
   - **Description**: Testing the system beyond normal operating conditions.
   - **Objective**: Determine system stability and identify breaking points.
   - **Example**: Increasing the load until the system crashes to find performance limits.

4. **Usability Testing**
   - **Description**: Testing the user interface and overall user experience.
   - **Objective**: Ensure the application is easy to use and intuitive.
   - **Example**: Observing users as they navigate the application to complete tasks.

5. **Security Testing**
   - **Description**: Testing the application for vulnerabilities and data protection.
   - **Objective**: Ensure the application is secure from threats and unauthorized access.
   - **Example**: Conducting penetration tests to identify security weaknesses.

6. **Compatibility Testing**
   - **Description**: Testing the application on different devices, operating systems, and browsers.
   - **Objective**: Ensure the application works well across various platforms.
   - **Example**: Checking how a mobile app behaves on Android and iOS.

---

## Differences Between Functional and Non-Functional Testing

| Aspect                | Functional Testing                             | Non-Functional Testing                        |
|-----------------------|-----------------------------------------------|-----------------------------------------------|
| **Objective**         | Validate features and functionality           | Assess performance and system behavior        |
| **Focus**             | Specific features and user requirements       | Quality attributes (speed, usability, etc.)   |
| **Example Tests**     | Login validation, data input/output accuracy  | Performance under load, security vulnerabilities |
| **Testing Techniques**| Black-box testing, manual testing             | Performance testing, automated testing        |
| **Result**            | Pass/Fail based on functionality              | Quantitative measures like response time      |

---

# Software Testing Myths: Debunking Common Misconceptions in Each Phase of Testing

Software testing is an essential part of the development lifecycle, but many myths and misconceptions surround it, often leading to misunderstandings and inefficiencies. Here, we’ll break down some common myths at each phase of the testing process to clarify the true role and value of structured software testing.

---

## 1. Test Planning

   - **Myth**: "Test planning is a one-time activity done at the beginning of a project."
   - **Reality**: Test planning is a dynamic process that may evolve as the project progresses. Changes in project scope, requirements, or timelines often require updates to the test plan. A flexible and adaptive test plan helps accommodate these shifts and ensures testing remains aligned with project goals.
   - **Myth**: "Only test managers are responsible for test planning."
   - **Reality**: While test managers lead test planning, it is a collaborative effort involving input from stakeholders, developers, testers, and product owners. This input ensures that the plan reflects real project needs, constraints, and goals.

---

## 2. Test Monitoring

   - **Myth**: "Once the tests start, monitoring them is unnecessary."
   - **Reality**: Test monitoring is crucial throughout the testing phase to track progress, measure the quality of test execution, and identify potential risks. Without monitoring, it’s difficult to assess whether testing is effective or if the project is on track.
   - **Myth**: "Test monitoring only involves tracking test cases passed or failed."
   - **Reality**: Effective test monitoring encompasses tracking a wide range of metrics, including defect density, test coverage, test effort, and risk exposure. These metrics offer a comprehensive view of the quality and readiness of the software.

---

## 3. Test Control

   - **Myth**: "Test control is only needed when a major issue arises."
   - **Reality**: Test control is an ongoing activity to ensure testing efforts align with project goals, timelines, and quality standards. Regular adjustments in response to minor issues prevent larger, more costly problems later.
   - **Myth**: "Only managers are responsible for test control."
   - **Reality**: While managers oversee test control, input from the entire testing team helps in adapting strategies based on on-ground realities. This collaborative approach makes the testing process more effective and responsive to challenges.

---

## 4. Test Analysis

   - **Myth**: "Test analysis is just about converting requirements into test cases."
   - **Reality**: Test analysis involves thoroughly examining requirements to identify potential test conditions, understanding risks, and clarifying ambiguities. It’s a detailed process aimed at ensuring that every aspect of the requirement is testable and aligns with user expectations.
   - **Myth**: "Test analysis can be skipped if requirements are well-documented."
   - **Reality**: Regardless of the quality of documentation, test analysis is essential to ensure that the requirements make sense, are complete, and feasible. It also helps uncover potential issues before they impact later testing phases, saving time and effort.

---

## 5. Test Design

   - **Myth**: "Test design only involves writing test cases."
   - **Reality**: Test design is a creative process that involves defining a wide variety of test scenarios, determining test data requirements, and creating reusable test scripts. It’s about crafting comprehensive testing that covers various input conditions, user behaviors, and edge cases.
   - **Myth**: "Good test cases don’t need to be updated."
   - **Reality**: Effective test cases are living documents that may need updating as new requirements emerge, functionalities change, or bugs are fixed. Test cases should evolve to stay relevant to the current state of the product.

---

## 6. Test Implementation

   - **Myth**: "Test implementation is just about setting up the environment and executing tests."
   - **Reality**: Test implementation involves a range of preparatory tasks, including configuring environments, setting up test data, reviewing test readiness, and validating the suitability of test tools. Skipping these steps can lead to incorrect test results and wasted effort.
   - **Myth**: "Automation in test implementation eliminates manual testing."
   - **Reality**: Automation complements but does not replace manual testing. While automation is useful for repetitive tasks, certain test cases, such as usability or exploratory tests, are best handled manually.

---

## 7. Test Execution

   - **Myth**: "Test execution is all about running test cases."
   - **Reality**: Test execution is not just about running tests but involves logging results, reporting defects, verifying fixes, and re-running tests after adjustments. Analyzing failures, isolating issues, and communicating findings are key parts of effective test execution.
   - **Myth**: "Test execution can only start after development is complete."
   - **Reality**: Testing can begin in parallel with development, using approaches like continuous testing and shift-left testing. Early execution of initial tests can catch issues sooner, reducing the cost and effort of fixing them.

---

## 8. Test Completion

   - **Myth**: "Test completion means all test cases have passed."
   - **Reality**: Test completion is not solely about passing test cases but involves ensuring that testing objectives have been met, defects have been addressed, and quality standards are achieved. It includes reporting, test case archiving, and retrospectives to identify lessons learned.
   - **Myth**: "Once testing is completed, it’s no longer needed."
   - **Reality**: Software can need retesting due to updates, patches, or new features. Test completion is the end of one testing cycle but may be followed by regression testing in future releases to ensure continued quality.

---

# The Test Process: Four Essential Steps

The software testing process is typically divided into four main stages, each with specific tasks to ensure a thorough evaluation of the software product. These stages are **Test Planning**, **Test Analysis and Design**, **Test Execution**, and **Test Evaluating and Reporting**. Let's explore each step in detail.

---

## 1. Test Planning

Test planning is the initial stage where the groundwork for the testing process is laid out. It involves determining the approach, objectives, resources, and schedule for the testing activities.

- **Determine the scope, risk, and objectives**: Define what the testing will cover, the risks involved, and the specific objectives.
- **Determine the resources, test environments, etc.**: Identify necessary resources, including personnel, software, hardware, and test environments.
- **Schedule test analysis and design tasks, test execution, and evaluation**: Plan the timeline for test analysis, design, execution, and review.
- **Determine the criteria**: Establish the criteria for success and failure, and the conditions for ending the test.

---

## 2. Test Analysis and Design

In this stage, testers define what to test, design test cases, and set up the test environment.

- **Review the SRS (Software Requirement Specification)**: Study the SRS to understand the functional and non-functional requirements.
- **Understand what the system should do**: Clarify the system's expected behaviors and features.
- **Identify test conditions and requirements**: Specify the conditions and requirements that need testing.
- **Design TEST CASES (Success/failure criteria)**: Develop detailed test cases with clear success and failure conditions.
- **Set up a test environment**: Configure the environment where testing will occur.
- **Identify and obtain required infrastructure and tools**: Gather necessary tools and infrastructure for testing.
- **Prepare the test data**: Create or collect data required to execute the test cases effectively.

---

## 3. Test Execution

This phase involves running the test cases, logging results, and identifying discrepancies between actual and expected outcomes.

- **Execute the test based on the test methodology**: Run tests as per the defined test cases and methodology.
- **Re-execute if the test failed**: Re-run the test cases that failed to verify fixes or determine recurring issues.
- **Log the outcome of the test execution and version of the software under test (Test Log)**: Record test results and relevant software version details for traceability.
- **Compare the actual results with the expected results**: Identify any differences between actual outcomes and expected results to find defects.

---

## 4. Test Evaluating and Reporting

The final stage is to evaluate the test results, analyze the root causes of defects, and report on the testing activities.

- **Analyze the root causes of defects and identify necessary actions**: Examine defect patterns and determine actions to improve product quality.
- **Write a Test Report**: Document the testing results, including details of defects found, the testing environment, and any recommendations for improvement.

---

These four steps form a comprehensive approach to software testing, ensuring a structured, systematic, and thorough process that enhances software quality and reliability.





----------------
## Common Tools for Functional Testing

1. **Selenium**
   - **Purpose**: Automated testing for web applications.
   - **Use Case**: Browser-based functional and regression testing.

2. **QTP/UFT**
   - **Purpose**: Automated functional testing.
   - **Use Case**: GUI testing for Windows and web applications.

3. **JUnit**
   - **Purpose**: Unit testing for Java applications.
   - **Use Case**: Testing individual components and functions.

4. **TestRail**
   - **Purpose**: Test case management.
   - **Use Case**: Organizing, tracking, and managing test cases and test runs.

5. **Postman**
   - **Purpose**: API testing.
   - **Use Case**: Functional testing of RESTful APIs to verify inputs and outputs.

---

## Common Tools for Non-Functional Testing

1. **Apache JMeter**
   - **Purpose**: Performance and load testing.
   - **Use Case**: Testing website and web service scalability under high traffic.

2. **LoadRunner**
   - **Purpose**: Load testing.
   - **Use Case**: Measuring system performance under load for applications.

3. **AppDynamics**
   - **Purpose**: Application performance management (APM).
   - **Use Case**: Monitoring application performance in real-time.

4. **Dynatrace**
   - **Purpose**: Performance and user experience monitoring.
   - **Use Case**: Detecting bottlenecks and tracking user satisfaction.

5. **OWASP ZAP**
   - **Purpose**: Security testing.
   - **Use Case**: Identifying security vulnerabilities in web applications.

---

## Conclusion

Functional and Non-Functional Testing play essential roles in ensuring software quality. Functional testing validates that software functions according to requirements, while non-functional testing assesses attributes like performance, usability, and security. Together, they ensure that the application not only works as expected but also provides a high-quality user experience.

Understanding and implementing both types of testing effectively helps in delivering robust, reliable, and user-friendly software.

--------------------------------------
## Sample of Test Cases


# Test Case Template

Software Engineering  
**Dr Ghazy Assassa**

---

## Test Case Template (Doc:T_01)

- **Test Case #**:
- **Test Case Name**:
- **Page**: 1 of ..

### Details
- **System**:
- **Subsystem**:
- **Designed by**:
- **Design Date**:
- **Executed by**:
- **Execution Date**:

### Short Description

---

### Pre-conditions

---

### Steps

| Step | Action                  | Expected System Response              | Pass/Fail | Comment |
|------|--------------------------|---------------------------------------|-----------|---------|
| 1    |                          |                                       |           |         |
| 2    |                          |                                       |           |         |

---

### Post-conditions

---

---

# Test Case Example 1 (Simple Test)

- **Test Case #**: 2.2
- **Test Case Name**: Change PIN
- **Page**: 1 of 1

### Details
- **System**: ATM
- **Subsystem**: PIN
- **Designed by**: ABC
- **Design Date**: 28/11/2004
- **Executed by**:
- **Execution Date**:

### Short Description
Test the ATM Change PIN service.

### Pre-conditions
- The user has a valid ATM card.
- The user has accessed the ATM by placing their ATM card in the machine.
- The current PIN is `1234`.
- The system displays the main menu.

### Steps

| Step | Action                     | Expected System Response                                                | Pass/Fail | Comment |
|------|-----------------------------|-------------------------------------------------------------------------|-----------|---------|
| 1    | Click the 'Change PIN' button | The system displays a message asking the user to enter the new PIN      |           |         |
| 2    | Enter '5555'                | The system displays a message asking the user to confirm (re-enter) the new PIN |         |
| 3    | Re-enter '5555'             | The system displays a message of successful operation. The system asks the user if they want to perform other operations |  |
| 4    | Click 'YES' button          | The system displays the main menu                                      |           |         |
| 5    | Check post-condition 1      |                                                                         |           |         |

### Post-conditions
1. The new PIN `5555` is saved in the database.

---

# Test Case Example 2 (Complex Test)

- **Test Case #**: 2.3
- **Test Case Name**: Change PIN
- **Page**: 1 of 1

### Details
- **System**: ATM
- **Subsystem**: PIN
- **Designed by**: ABC
- **Design Date**: 28/11/2004
- **Executed by**:
- **Execution Date**:

### Short Description
Test the ATM Change PIN service.

### Pre-conditions
- The user has a valid ATM card.
- The user has accessed the ATM by placing their ATM card in the machine.
- The current PIN is `1234`.
- The system displays the main menu.

### Steps

| Step | Action                      | Expected System Response                                                | Pass/Fail | Comment |
|------|------------------------------|-------------------------------------------------------------------------|-----------|---------|
| 1    | Click the 'Change PIN' button | The system displays a message asking the user to enter the new PIN      |           |         |
| 2    | Enter '5555'                 | The system displays a message asking the user to confirm (re-enter) the new PIN |   |
| 3    | Re-enter '5555'              | The system displays a message of successful operation. The system asks the user if they want to perform other operations | |
| 4    | Click 'YES' button           | The system displays the main menu                                      |           |         |
| 5    | Check post-condition 1       |                                                                         |           |         |
| 6    | Repeat steps 1,2,3 using another PIN say '6666' and click 'NO' button | The system exits and displays a greeting message asking the user to place their ATM card in the machine | |
| 7    | Check post-condition 2       |                                                                         |           |         |
| 8    | Repeat steps 1,2, using another PIN say '7777'                    | The system displays a message asking the user to confirm (re-enter) the new PIN | |
| 9    | Enter a wrong confirmation (say ‘9876’) | The system displays a message of unsuccessful operation and asks the user to confirm the correct PIN | |
| 10   | Re-enter ‘7777’              | The system displays a message of successful operation. The system asks the user if they want to perform other operations | |

### Post-conditions
1. The new PIN `5555` is saved in the database.
2. The new PIN `6666` is saved in the database.
3. The new PIN `7777` is saved in the database.

### Notes
- Test happy path.
- Test failure condition (step 9).

