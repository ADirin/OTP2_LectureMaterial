# Localization in Java
In Java, a ResourceBundle is used to manage localization, allowing applications to support multiple languages and regions. 
It helps by separating the application's locale-specific data (like strings for messages) from the main code. 
Instead of hardcoding messages or other resources in the application, you store them externally in files or classes. 
At runtime, the correct version of the resources (depending on the locale) is selected automatically.

## How ResourceBundle Works:

![Resource Bundle](/Images/rBundle2.png)

1. Resource Bundle Files:


   - Resource bundles are typically properties files (or classes) that contain key-value pairs for different locales.
   - They are named in a specific pattern: baseName_languageCode_countryCode.properties. For example:
      - Messages.properties (default, for any locale)
      - Messages_en_US.properties (for U.S. English)
      - Messages_fr_FR.properties (for French)

3. Loading the Correct Resource Bundle: The Java ResourceBundle class will load the correct file based on the user's locale.

4. Retrieving Values: The keys from the resource bundle are used to retrieve the locale-specific values in the application code.

[Reference](https://phrase.com/blog/posts/a-beginners-guide-to-java-internationalization/)

--------------------------
# Localization Assignment: Extend Language Support with Farsi
In this assignment, you'll add Farsi localization to a Java application, configure UTF-8 encoding, and create unit tests to verify each language. Follow each step carefully to ensure successful localization implementation.



Tasks


## Task 1: Add Farsi Language Support
### Extend lecture assignment with aditional bundle for farsi:
   `MessagesBundle_fa_IR`
```css
greeting= سلام! به برنامه ما خوش آمدید
```
Ensure that the file structure looks like this (without any nested packages):

```css
LocalizedGreetingApp
├── src
│   └── LocalizedGreeting.java
└── resources
    ├── MessagesBundle_en_US.properties
    ├── MessagesBundle_fr_FR.properties
    ├── MessagesBundle_es_ES.properties
    └── MessagesBundle_fa_IR.properties


```
## Task 2: Configure UTF-8 Encoding in IntelliJ
- To ensure Farsi characters display correctly, verify that IntelliJ IDEA is set to UTF-8 encoding:

- Go to File > Settings > File Encoding (or IntelliJ IDEA > Preferences > File Encoding on macOS).
- Set both Project Encoding and Default Encoding for Properties Files to UTF-8.
- Save your settings.

## Task 3: Verify Farsi Text in the Properties File
- Open MessagesBundle_fa_IR.properties.

- Confirm that the greeting text appears correctly as:
```css
greeting=سلام! به برنامه ما خوش آمدید

```
**Note:** If you see garbled text (e.g., greeting= ???? ????? ??????), re-enter the text manually and save the file in UTF-8 encoding.

## Task 4: Create Unit Tests for All Languages
In the src/test/java directory, create a test class named LocalizedGreetingTest.

- Write JUnit test methods for each language to confirm the correct messages are loaded. Use the following *Sample code*
```java
public class LocalizedGreetingTest {

    @Test
    void testEnglishLocale() {
        Locale locale = new Locale("en", "US");
        ResourceBundle messages = ResourceBundle.getBundle("MessagesBundle", locale);
        assertEquals("Hello! Welcome to our application.", messages.getString("greeting"));
    }

```
### Run the Tests:

- In IntelliJ, right-click on LocalizedGreetingTest and select Run 'LocalizedGreetingTest'.
1. Confirm that all Unit tests are pass successfully.
2. Create a JaCOCO report

## Task 5. Add a Dockfile to the project and run the file locally
## Task 6. Create a Jenkins pipeline with a name `OTP2_VK1_LocalDemo1` and create application image which upload in *hub.docker.com* test your image in *https://labs.play-with-docker.com/*

## Submission
1. Submit the github repor
2. Submit the screenshot of the JaCoCo result
3. Screenshot of the Docker Image from docker desktop
4. Screenshot of the -labs.play- output
## Notes
Encoding: Make sure all .properties files use UTF-8 encoding to prevent character corruption in non-Latin languages.
Testing: Run tests on a system that supports UTF-8 characters if using a terminal or command line.

```
