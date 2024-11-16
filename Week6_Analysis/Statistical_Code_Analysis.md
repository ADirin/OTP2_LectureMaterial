# Software Statistical Code Analysis

Statistical code analysis is an essential practice in software quality assurance that leverages statistical methods to assess code quality and maintainability. It provides insights into software complexity, potential vulnerabilities, and adherence to coding standards. This learning material covers the principles, techniques, and tools involved in statistical code analysis.

## Table of Contents
- [Introduction to Statistical Code Analysis](#introduction-to-statistical-code-analysis)
- [Key Metrics in Statistical Code Analysis](#key-metrics-in-statistical-code-analysis)
- [Techniques for Statistical Code Analysis](#techniques-for-statistical-code-analysis)
- [Tools for Statistical Code Analysis](#tools-for-statistical-code-analysis)
- [Benefits of Statistical Code Analysis](#benefits-of-statistical-code-analysis)
- [Challenges in Statistical Code Analysis](#challenges-in-statistical-code-analysis)
- [Conclusion](#conclusion)

---

## Introduction to Statistical Code Analysis

Statistical code analysis involves the application of statistical methods to measure and analyze code characteristics, aiming to improve software quality. It helps in identifying code smells, assessing code complexity, and predicting potential issues in the codebase.

### Why Use Statistical Code Analysis?

- **Automated Insights**: Provides automated metrics that facilitate quick decision-making.
- **Early Detection**: Helps identify problems early in the development cycle, reducing long-term costs.
- **Improved Maintainability**: Enhances code readability and maintainability through consistent coding practices.
- Applying company styles such as indents, spaces, tabs, and standards
- Produce metrics indicative of code quality 
- Detect errors in boundary conditions, security, logic, and others
- Provide documentations 
- It increases the safety and quality  (e.g., identify NULL pointers)

> ![Sonar Lint](/Images/sonarLint1.jpg)


---

## Key Metrics in Statistical Code Analysis

1. **Lines of Code (LOC)**
   - **Definition**: Total number of lines in the codebase.
   - **Purpose**: A basic measure of the code size and complexity.

2. **Cyclomatic Complexity**
   - **Definition**: A metric that measures the number of linearly independent paths through a program's source code.
   - **Purpose**: Indicates the complexity of a program and helps identify areas that may be difficult to maintain.

3. **Code Churn**
   - **Definition**: The percentage of code added, modified, or deleted over a specific period.
   - **Purpose**: A measure of code stability and indicates potential volatility.

4. **Comment Density**
   - **Definition**: The ratio of comment lines to the total lines of code.
   - **Purpose**: Assesses code documentation quality and maintainability.

5. **Duplication Ratio**
   - **Definition**: The percentage of code that is duplicated within the codebase.
   - **Purpose**: Identifies code smells and areas where refactoring is needed.

6. **Test Coverage**
   - **Definition**: The percentage of code that is tested by automated tests.
   - **Purpose**: Indicates the effectiveness of tests and the likelihood of undetected bugs.

---

## Techniques for Statistical Code Analysis

1. **Static Code Analysis**
   - **Description**: Analyzing code without executing it to identify potential errors and adherence to coding standards.
   - **Example Tools**: SonarQube, Checkstyle, and PMD.

2. **Dynamic Code Analysis**
   - **Description**: Analyzing the code during execution to assess performance and detect runtime errors.
   - **Example Tools**: Valgrind and AppDynamics.

3. **Code Reviews**
   - **Description**: Peer reviews of code changes to identify issues and ensure coding standards.
   - **Purpose**: Improve code quality and foster knowledge sharing among team members.

4. **Metrics Visualization**
   - **Description**: Graphically representing code metrics to identify trends and areas for improvement.
   - **Purpose**: Facilitate understanding and communication of code quality to stakeholders.

---

## Tools for Statistical Code Analysis


> ![Sonar Lint](/Images/checkStyle.jpg)

1. **SonarQube**
   - **Purpose**: Continuous inspection of code quality.
   - **Features**: Measures code quality metrics, detects code smells, and tracks technical debt.

2. **Checkstyle**
   - **Purpose**: Static code analysis for Java.
   - **Features**: Ensures adherence to coding standards and best practices through customizable rules.

3. **PMD**
   - **Purpose**: Static analysis for Java and other languages.
   - **Features**: Detects common programming flaws, such as unused variables and empty catch blocks.

4. **FindBugs / SpotBugs**
   - **Purpose**: Analyzes Java bytecode to identify potential bugs.
   - **Features**: Provides insights into code quality and possible issues based on static analysis.

5. **Code Climate**
   - **Purpose**: Automated code review and analysis.
   - **Features**: Supports multiple languages and provides quality metrics and maintainability scores.

6. **Coverity**
   - **Purpose**: Static analysis tool for identifying security vulnerabilities and defects.
   - **Features**: Supports a wide range of programming languages and integrates with CI/CD pipelines.

7. **ESLint**
   - **Purpose**: Static code analysis for JavaScript.
   - **Features**: Identifies problematic patterns in JavaScript code and enforces coding standards.
8. **Lint**
   - Lint is a generic term used to describe static analysis tools across various programming languages. Originally, it was a tool for C code, but now it's commonly used for other languages like Java, JavaScript, and more.
   - Lint tools analyze source code to detect potential errors, bugs, and stylistic issues.
   - In the context of Java development, lint tools perform similar functions to Checkstyle, FindBugs, and PMD but may have different focuses or capabilities.
   - These tools are valuable for identifying and addressing issues early in the development process, helping to improve code quality, maintainability, and reliability.
   - They are often integrated into the software development workflow and used alongside other testing and quality assurance practices.



---

## Benefits of Statistical Code Analysis

- **Improved Code Quality**: Identifies and addresses issues early, leading to cleaner, more maintainable code.
- **Enhanced Collaboration**: Facilitates communication among team members about code quality and standards.
- **Reduced Technical Debt**: Helps teams manage and reduce technical debt by identifying areas needing improvement.
- **Informed Decision Making**: Provides data-driven insights that inform development and project management decisions.

---

## Challenges in Statistical Code Analysis

- **False Positives**: Tools may flag non-issues, leading to wasted time addressing irrelevant warnings.
- **Integration Complexity**: Integrating analysis tools into existing workflows can be challenging.
- **Metric Interpretation**: Misinterpretation of metrics can lead to incorrect conclusions about code quality.
- **Resistance to Change**: Developers may resist adopting new practices and tools due to existing workflows.

---

## Conclusion

Statistical code analysis is a vital practice for maintaining high-quality software. By applying various techniques and leveraging tools, teams can gain valuable insights into code quality, identify potential issues, and foster a culture of continuous improvement. The combination of functional and non-functional testing, along with statistical analysis, leads to the development of robust and maintainable software products.

By embracing statistical code analysis, software teams can significantly enhance their coding practices, leading to improved product quality and user satisfaction.

--------------------------------------------------------------------
# **Student Guide: Setting Up and Using Checkstyle in IntelliJ**

This guide will help you set up and use Checkstyle in IntelliJ IDEA to ensure your code adheres to consistent coding standards.

---

## **1. Install Checkstyle Plugin**
1. Open IntelliJ IDEA.
2. Go to `File > Settings` (or `Preferences` on macOS).
3. Navigate to `Plugins`.
4. Search for **Checkstyle** in the plugin marketplace.
5. Click `Install` and restart IntelliJ IDEA if prompted.

---

## **2. Configure Checkstyle**


1. Go to `File > Settings > Tools > Checkstyle`.
2. Click the **+** icon to add a new configuration.
3. Intellij has by default two styles (sun or google) pick one of these
> ![Tools](/Images/checkStyleDefault.jpg)

4. Incase you have your customized style sheet:
   - create config/checkstyle folder at the root of your project and add an xml file *(stylecheck.xml)*
   - then configure the customized style check as follows--> setting-->tools--> check style 
   - > ![Tools](/Images/checkStyleTools.jpg)
   - Choose `Use a local Checkstyle file` and browse to locate your `checkstyle.xml` file.
   - You can download a sample `checkstyle.xml` file from [Checkstyle GitHub](https://github.com/checkstyle/checkstyle/blob/master/src/main/resources/google_checks.xml).
7. Name the configuration (e.g., *Google Style*).
8. Click **OK** to save the configuration.

---

## **3. Enable Checkstyle in a Project**
1. Open your project in IntelliJ IDEA.
2. Navigate to `File > Settings > Tools > Checkstyle`.
3. Under **Scan Scope**, select `Whole project` or `Current file`.
4. Set your preferred configuration as the default by checking the box next to it.
5. Click **OK** to save.

---

## **4. Write a Simple Java Class**
Let’s create a simple Java class and see how Checkstyle enforces coding standards.

### Example Code (`Student.java`):
```java
public class Student {

    private String name;
    private int age;

    // Constructor
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Getter for name
    public String getName() {
        return name;
    }

    // Setter for name
    public void setName(String name) {
        this.name = name;
    }

    // Getter for age
    public int getAge() {
        return age;
    }

    // Setter for age
    public void setAge(int age) {
        this.age = age;
    }

    // Method to display student info
    public void displayInfo() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
}
````

## **5. Analyze Code with Checkstyle**
Right-click on your project folder or file and select Checkstyle > Scan with Checkstyle.
Checkstyle will analyze your code and display warnings/errors in the Checkstyle Results window.

------------

## **6.Fixing Common Checkstyle Errors**

Example Error **1: Missing Javadoc Comments**
 - Issue: Public classes and methods must have Javadoc comments.
 - Fix: Add Javadoc to your class and methods:
````java

/**
 * Represents a Student with a name and age.
 */
public class Student {
    // ...
}

/**
 * Displays student information.
 */
public void displayInfo() {
    System.out.println("Name: " + name + ", Age: " + age);
}

````

Example Error **2: Line Length Exceeds Limit**
   - Issue: A line exceeds the configured maximum length (e.g., 100 characters).
   - Fix: Break long lines into multiple lines for better readability:
````java
System.out.println(
    "Name: " + name + ", Age: " + age
);


````
## **7. Run Checkstyle Again**
After making changes, run Checkstyle again to ensure the issues are resolved.

---

## **8. Benefits of Using Checkstyle**
- Enforces coding standards, such as naming conventions and line length.
- Improves code readability and maintainability.
- Identifies potential errors early in development.

---------------------------------------


# Using FindBugs in IntelliJ IDEA

## Introduction to FindBugs
FindBugs is a static analysis tool that detects bugs in Java code by analyzing bytecode. It helps identify potential issues like null pointer dereferences, code smells, and performance issues. Although FindBugs is no longer actively maintained, its functionalities can still be accessed via IntelliJ IDEA using compatible plugins like **Find Security Bugs** (an extended version of FindBugs).

---

## Installing FindBugs Plugin in IntelliJ IDEA

1. **Open Plugin Settings**:
   - Navigate to `File > Settings > Plugins` (Windows/Linux) or `IntelliJ IDEA > Preferences > Plugins` (Mac).

2. **Search for FindBugs**:
   - In the search bar, type **FindBugs** or **Find Security Bugs** (recommended as it’s updated with security checks).

3. **Install Plugin**:
   - Select the plugin from the results and click **Install**.

4. **Restart IntelliJ**:
   - Restart the IDE to activate the plugin after installation.

---

## Configuring FindBugs in IntelliJ

1. **Enable FindBugs Inspection**:
   - Go to `File > Settings > Editor > Inspections`.
   - Expand the `FindBugs` section in the **Inspections** tree.
   - Enable desired inspections by checking their boxes.

2. **Customize Inspection Settings**:
   - Select an inspection and click the **gear icon** to configure its severity level and rules.
   - Use the **scope selector** to limit the inspection to specific files, directories, or modules.

3. **Set Custom Filters** (Optional):
   - Create or edit `.fbexclude` files to filter out specific classes or methods from the analysis.

---

## Running FindBugs Analysis

1. **Run Inspection on Code**:
   - Right-click on the project or a specific file in the Project Explorer.
   - Select `Analyze > Run Inspection by Name`.
   - Type **FindBugs** and choose the desired inspection.

2. **View Results**:
   - The results will appear in the **Inspection Results** tab.
   - Detected issues are categorized by severity, such as warnings, errors, and informational messages.

3. **Fix Issues**:
   - Click on a reported issue to navigate directly to the corresponding line of code.
   - Use IntelliJ's built-in quick fixes or manually refactor your code.

---

## Integrating FindBugs in Build Tools

### For Maven Projects
Add the FindBugs Maven plugin to your `pom.xml`:
```xml
<plugin>
    <groupId>org.codehaus.mojo</groupId>
    <artifactId>findbugs-maven-plugin</artifactId>
    <version>3.0.5</version>
    <executions>
        <execution>
            <phase>verify</phase>
            <goals>
                <goal>check</goal>
            </goals>
        </execution>
    </executions>
</plugin>
````
## Best Practices

- **Regular Analysis**:  
  Run FindBugs frequently to catch issues early during development.

- **Combine with Other Tools**:  
  Use IntelliJ's built-in inspections and additional tools like PMD or SonarLint for comprehensive analysis.

- **Suppress Warnings**:  
  If a specific issue is a false positive or not critical, use `@SuppressWarnings("FindBugs")` to suppress it.

- **Automate in CI/CD**:  
  Integrate FindBugs into your Continuous Integration pipeline to enforce quality checks.

---

## Limitations of FindBugs

- FindBugs analyzes bytecode, so certain issues detectable only in source code might be missed.
- It doesn’t actively support modern Java language features (Java 9+).

For a more modern alternative, consider using **SpotBugs**, which is actively maintained and provides updated rules.



### Example

- Create a java class and follow the instructions for testing

```java
public class Example {

    private static String message;

    public static void main(String[] args) {
        System.out.println("Welcome to FindBugs Example!");

        // Potential bug: NullPointerException risk
        System.out.println(message.toLowerCase());

        // Potential bug: Unused variable
        int unusedVariable = 42;
    }
}


```

### 2. Install and Configure FindBugs Plugin

#### Install the Find Security Bugs Plugin:
1. Go to `File > Settings > Plugins`.
2. Search for **"Find Security Bugs"** and install the plugin.
3. Restart IntelliJ IDEA.

#### Enable Inspections for FindBugs:
1. Go to `File > Settings > Editor > Inspections`.
2. Expand the **FindBugs** section.
3. Enable inspections like **Potential null pointer dereference** and **Unused variables**.

---

### 3. Run FindBugs Analysis

1. Right-click on the `src` folder or the `Example` class in the Project Explorer.
2. Select `Analyze > Run Inspection by Name`.
3. Type **FindBugs** and select the inspection type to run (e.g., **Potential null pointer dereference**).
4. Click **OK** to start the analysis.

---

### 4. View and Resolve Issues

#### View Issues:
- The results will appear in the **Inspection Results** tab:
  - **Warning 1**: Null pointer dereference risk on `message.toLowerCase()`.
  - **Warning 2**: Unused variable `unusedVariable`.

#### Fix the Issues:
1. **Initialize `message`** to avoid the null pointer dereference:
```java
   private static String message = "Default Message";
````

2. ***Remove or use the unused variable:

```java

int unusedVariable = 42;
System.out.println("Unused variable value: " + unusedVariable);

```

---------------------------------------------
