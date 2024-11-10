# Exercise: Applying Six Sigma to Improve Software Quality of your group project

### Objective:
In this exercise, you’ll apply Six Sigma principles to analyze, identify, and resolve issues in **your software engineering project**. The goal is to assess the current state of your project, identify defects, and work to resolve these defects within the next three weeks.

### Scenario (EXAMPLE):
Let’s consider a software project for a **car rental application**. The main functionalities include searching for available cars, booking rentals, managing rental records, and supporting various languages. However, the product is only partially complete, with several features like **UI localization** and **database localization for Japanese** still missing.

---

## Steps

### 1. **Define**: Understand the Problem and Set Clear Objectives
   - **Objective**: Improve the car rental application by identifying current defects and setting achievable improvement targets.
   - **Goal**: Complete missing features and ensure that the app functions smoothly without critical errors. Specific areas of improvement:
     - Implement **UI localization** for Japanese.
     - Complete **database localization** for Japanese.
     - Improve existing functionalities to ensure seamless operation.

#### Example Problem Statement:
- "The car rental application is not fully localized for Japanese users, impacting usability and customer satisfaction in Japan."

#### Example Goal:
- "Implement UI and database localization for Japanese within three weeks, and reduce user-reported defects related to localization issues by 80%."

---

### 2. **Measure**: Collect Data to Understand the Current State
   - **Baseline Metrics**:
     - Number of defects currently logged related to localization or usability.
     - User experience data, if available, on language issues or database errors.
     - Time taken to access the app for Japanese-speaking users.

#### Example Data Collection:
   - Log localization issues, track UI elements missing in Japanese, and document database entries not yet translated.
   - Review error logs to see where localization is failing.

---

### 3. **Analyze**: Identify Root Causes of Defects
   - **Root Cause Analysis**:
     - **UI Localization**: Missing translations or layout issues in Japanese.
     - **Database Localization**: Fields or records not translated properly for Japanese customers, leading to poor user experience.

#### Example Root Cause Analysis:
- **5 Whys Analysis for UI Localization**:
   1. Why is the UI not fully translated? → Because translation files are missing for certain sections.
   2. Why are translation files missing? → Because the localization process is incomplete.
   3. Why is the localization process incomplete? → Because there was no dedicated time for localization during initial development.
   4. Why wasn’t time allocated? → Because localization was planned for later phases.
   5. Why was it delayed? → Due to focus on core functionality over localization.

---

### 4. **Improve**: Develop and Implement Solutions
   - **Solution Development**:
     - **UI Localization**: Translate the remaining sections of the UI, ensuring all menu items, buttons, and messages appear correctly in Japanese.
     - **Database Localization**: Localize database entries for items like car models, booking terms, and customer data.
     - **Testing**: Conduct testing with native Japanese speakers to ensure translations are correct and that the UI layout is consistent.

#### Example Solutions:
- **For UI Localization**: Use a translation management tool to complete all missing translations and regularly check for untranslated sections.
- **For Database Localization**: Implement a language-specific table or column in the database to store Japanese entries and make sure the correct language setting loads for Japanese users.
- **Testing**: Create test cases to verify that every page displays properly in Japanese and that all text appears as expected.

---

### 5. **Control**: Ensure the Improvements Are Sustained
   - **Monitoring**:
     - Set up automated tests to check for localization errors and untranslated strings.
     - Track localization-related user complaints after implementation to gauge the impact.
   
   - **Documentation and Continuous Improvement**:
     - Document the changes made to the localization process and use this as a reference for future localization efforts.
     - Use feedback from Japanese users to make further refinements.

#### Example Control Plan:
- **Automated Testing**: Set up automated testing tools to scan for untranslated text.
- **Feedback Loop**: Collect feedback from Japanese users to catch any additional localization issues and continuously improve localization quality.

---

## Example Solution Summary for Car Rental App

1. **Goal**: Localize UI and database for Japanese and reduce localization-related issues.
2. **Defects Identified**:
   - Missing UI translations.
   - Incorrectly formatted database entries for Japanese text.
3. **Root Causes**:
   - Lack of dedicated resources for localization during early development.
   - No systematic approach to track localization progress.
4. **Implemented Solutions**:
   - Used a translation management tool to complete all UI translations.
   - Adjusted database structure to support Japanese entries and ensure correct display.
   - Performed user testing with native Japanese speakers.
5. **Control Measures**:
   - Automated tests for detecting untranslated text.
   - Continuous feedback collection from Japanese-speaking users.

---

## Expected Outcome:
After completing this exercise, your car rental application should be fully localized for Japanese users, providing a smooth and user-friendly experience. Additionally, you should gain insights into using Six Sigma to systematically identify and resolve issues in software projects.

---

## Submission (in OMA)
- **Report**: Submit a report detailing each step, the defects identified, and the solutions implemented.
- **Screenshots**: Provide before-and-after screenshots showcasing the improvements.
- **Reflection**: Include a brief reflection on how Six Sigma helped improve your project’s quality and what you would consider for future projects.

---

This exercise will help you apply Six Sigma to a real-world software project, identifying areas for improvement, and working systematically to implement and sustain quality enhancements.
