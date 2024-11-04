# Database Localization in Relational Databases

Localization in databases refers to adapting data to suit the language, cultural, and regional preferences of different users. In relational databases, localization becomes essential when applications serve a global audience and require support for multiple languages and regions.

This learning material covers the basics of database localization with a focus on relational databases, strategies for data and schema design, and implementation best practices.

## 1. Introduction to Localization in Relational Databases

**What is Database Localization?**
Database localization is the process of adapting database content, schemas, and queries to support different languages and regions. Localization in relational databases may involve storing translated text, managing date and time formats, currency conversion, and even providing region-specific content.



**Why is Localization Important?**
In global applications, localization improves user experience by presenting data in a familiar format and language. For businesses, localization can increase user engagement and market reach by creating a personalized experience for users in different regions.

## 2. Key Concepts in Database Localization

**Key Concepts**
1. Internationalization (i18n): Preparing the database and application to support multiple languages, regions, and formats without needing significant changes for each new locale.

2. Localization (l10n): Adapting the database to meet specific regional or cultural preferences, often involving translations and format adjustments.

3. Locale: A combination of language and country or region (e.g., en_US for American English, fr_FR for French in France) that determines language and formatting preferences.

4. Character Encoding: A way to represent text in different languages. UTF-8 is commonly used for supporting multilingual text in databases.

## 3. Localization Approaches in Relational Databases

**Approach 1: Field  localization**

![*Example of field localization*] (https://github.com/ADirin/field_localization_demonstration)

**Approach 2: Separate Tables for Each Language**

In this approach, each language has its own table, which is queried based on the user’s language preference.

**Pros:**
  -- Simplifies structure by separating each language completely.

**Cons:**

  -- Increases the number of tables and complicates database management.

**Approach 3: Columns for Each Language**

A single table contains additional columns for each language, with each column holding data in a specific language.

**Pros:**

  -- Reduces the number of tables and keeps data in a single table.

**Cons:**

  -- Increases table width and wastes space if some languages aren’t used.

** Approach 4: Translation Table (Recommended)**

A translation table holds all translations for localizable content, with each entry tied to a specific locale. This approach uses a main table with reference keys to the translation table.

**Pros:**

  -- Scales well and is efficient when adding new languages.

**Cons:**

  -- Requires JOIN operations, which may impact performance for large datasets.

## 4. Schema Design Strategies

**Strategy 1: Using a Translation Table**

1. Main Table: Stores all general information and IDs for localized content.
   
3. Translation Table: Stores translations for each localizable column with fields for locale, field_name, and translated_value.

Example Schema
```sql
CREATE TABLE Product (
    product_id INT PRIMARY KEY,
    category_id INT,
    price DECIMAL(10, 2),
    created_at TIMESTAMP
);

CREATE TABLE ProductTranslation (
    product_id INT,
    locale VARCHAR(5),
    field_name VARCHAR(50),
    translated_value TEXT,
    PRIMARY KEY (product_id, locale, field_name),
    FOREIGN KEY (product_id) REFERENCES Product(product_id)
);


```
**Strategy 2: Using JSON Columns**
For databases that support JSON data types (e.g., PostgreSQL), translations can be stored as JSON in a single column.

 ```sql
CREATE TABLE Product (
    product_id INT PRIMARY KEY,
    category_id INT,
    price DECIMAL(10, 2),
    created_at TIMESTAMP,
    translations JSONB -- stores translations in JSON format
);


```
**Note:** JSON allows storing translations in a single column but makes it harder to filter and sort based on specific language values directly within SQL queries.

**Strategy 3: Adding Columns for Each Language (for Small-Scale Applications)**
For simpler applications with limited languages, you can add separate columns for each language directly in the main table.

 ```sql
CREATE TABLE Product (
    product_id INT PRIMARY KEY,
    category_id INT,
    price DECIMAL(10, 2),
    name_en VARCHAR(255),
    name_fr VARCHAR(255),
    name_es VARCHAR(255),
    created_at TIMESTAMP
);


```
**Note:** This approach does not scale well but is manageable for two to three languages.

------------------------

# 5. Implementation Examples

### Example 1: Querying the Translation Table
To fetch a product name in a user’s preferred language:

```sql
SELECT p.product_id, COALESCE(t.translated_value, p.default_name) AS name
FROM Product p
LEFT JOIN ProductTranslation t 
ON p.product_id = t.product_id 
AND t.locale = 'fr_FR'
WHERE p.product_id = 1;

```
### Example 2: Using JSON for Translations in PostgreSQL
If translations are stored in JSON, querying can be done with JSON-specific operators:

```sql

SELECT product_id, translations->>'name_en' AS name 
FROM Product 
WHERE product_id = 1;


```
### Example 3: Handling Date and Time Localization
For date and time, consider storing timestamps in UTC and handling formatting at the application layer. This ensures time consistency and easier localization based on user locale.

-----------------------------------

# 6. Best Practices for Localized Database Design
1. Use UTF-8 Encoding: Ensure all tables and columns are configured to use UTF-8 encoding to support various languages.
2. Separate Translations from Core Data: Use a translation table or JSON to avoid schema modifications every time a new language is added.
3. Index Locale Columns: When using a translation table, index the locale column to improve performance in querying translations.
4. Store Dates and Times in UTC: Store all timestamps in UTC and convert to the user's local time as needed.
5. Consider Caching Translations: For applications with high read traffic, cache translations to reduce database load.
6. Test for Special Characters: Different languages introduce special characters that may cause encoding issues. Regularly test data input and output for various locales.
7. Plan for Non-Translatable Data: Some fields, like numeric codes or IDs, should remain unchanged across locales. Consider marking non-translatable fields clearly in the schema.
----------------------------------------

# Lecture Demo
## Field Localization
```sql
EATE TABLE employees (
    emp_id INT PRIMARY KEY,
    name_en VARCHAR(255) character SET UTF8mb4, -- English name
    name_fa VARCHAR(255) character SET UTF8MB4, -- Farsi name
    name_ja VARCHAR(255) character SET UTF8MB4, -- Japanese name
    age INT,
    salary DECIMAL(10, 2)
);

```
See the code:
https://github.com/ADirin/field_localization_demonstration.git

**JDBC Driver** 

  - https://github.com/ADirin/OTP2_LectureMaterial/blob/main/Week3_Localization/JDBC_Driver/instructions.md

```sql
-- Retrieve employee names in Farsi
SELECT emp_id, name_fa, age, salary FROM employees;

-- Retrieve employee names in Japanese
SELECT emp_id, name_ja, age, salary FROM employees;


```
## Row_loacalization

```sql
CREATE TABLE employees_row (
    emp_id INT,
    language_code VARCHAR(2), -- Language code (e.g., en, fa, ja)
    name VARCHAR(255), -- Employee name
    age INT,
    salary DECIMAL(10, 2),
    PRIMARY KEY (emp_id, language_code)
);
![image](https://github.com/user-attachments/assets/b6af6ac3-24f6-43cf-94d1-da8263a2da69)


```

[Java code:] https://github.com/ADirin/row_localization_demonstration.git

## POM.Depencencies for driver 
```xml

<dependencies>

    <dependency>
        <groupId>mysql</groupId>
        <artifactId>mysql-connector-java</artifactId>
        <version>8.0.31</version>

    </dependency>

    <dependency>
        <groupId>org.mariadb.jdbc</groupId>
        <artifactId>mariadb-java-client</artifactId>
        <version>3.4.1</version>

    </dependency>
    </dependencies>


```
