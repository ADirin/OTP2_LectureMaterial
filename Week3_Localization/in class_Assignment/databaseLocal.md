
-------------------------------------------------------------------------

# Home Assignment: Localized Database

## Database Structure
Establish a database containing a table named `employee` with the following attributes, localized in three different languages (English, Farsi, and Japanese):

```sql
CREATE TABLE employee_en (
    id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    email VARCHAR(100)
);

CREATE TABLE employee_fa (
    id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    email VARCHAR(100)
);

CREATE TABLE employee_ja (
    id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    email VARCHAR(100)
);
```

## Database Overview
This example showcases a database structure with separate tables for each language.

![The UI](/Images/jfxh3_1.png)

## User Interface for Language Selection
Develop a user interface that enables users to select their preferred language (English, Farsi, or Japanese). The labels and the save button within the UI should dynamically adapt according to the chosen language, as illustrated below:

![The UI](/Images/jfxh3_2.png)

## Sample Updates
The following are sample updates to the tables based on the selected language.

![The UI](/Images/jfxh3_3.png)

## Localization Options
Based on the lecture content, consider the following approaches for database localization:

1. **Field Localization**
2. **Row Localization**
3. **Table-Based Localization**
4. **Translation Table**

## Task and Submission
- Implement one or all of the above localization approaches using your programming skills.
- Use Git to manage your codebase and submit the GitHub link on Oma.
- Include a brief `README` in the GitHub repository explaining your solution.
- Additionally, provide screenshots of the localized UIs and the database structure, compiled in a PDF file.

**Deadline**: Submit both the GitHub link and the PDF file to the dedicated folder in Oma by **XXXX X, 2024**.




