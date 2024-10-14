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
Confirm that all tests pass successfully.

## Submission
1. Submit the github repor
2. Submit the screenshot of the unit test

## Notes
Encoding: Make sure all .properties files use UTF-8 encoding to prevent character corruption in non-Latin languages.
Testing: Run tests on a system that supports UTF-8 characters if using a terminal or command line.

```
