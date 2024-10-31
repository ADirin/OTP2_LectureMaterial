# Multilingual Product Viewer Application with Database Localization

This guide details the design of a JavaFX application that demonstrates database localization for a product catalog. The application and its SQLite database will store multilingual data (e.g., English and French) for product details, which the app displays based on the user’s selected language.

---

## Application Overview

The **Multilingual Product Viewer** is a JavaFX-based application that allows users to select a language (English or French) and view product names and descriptions in that language. The JavaFX interface includes the following components:

1. **Language Selector**: A dropdown (ComboBox) to let users select their preferred language (e.g., "English" or "French").
2. **Load Products Button**: A button that, when clicked, fetches product data in the selected language from the database.
3. **Product Table**: A TableView component that displays product data with the following columns:
   - **ID**: Unique identifier for the product.
   - **Name**: The product name in the selected language.
   - **Description**: The product description in the selected language.

The application fetches product data from an SQLite database based on the language choice, demonstrating two database localization strategies: separate tables for each language and a single table with columns for multiple languages.

---

## Database Design

The SQLite database, `localizeDB`, contains product data for each supported language. Below are two design approaches for database localization.

---

### Approach 1: Separate Tables for Each Language

In this approach, each language has its own table with localized product names and descriptions. This setup is beneficial when databases expect frequent additions or edits to language-specific tables, as each table can be managed independently.

**Database Schema for Separate Tables**

- **Table 1**: `product_en`
   - **id** (INTEGER, Primary Key): Unique product identifier.
   - **name** (TEXT): Product name in English.
   - **description** (TEXT): Product description in English.

- **Table 2**: `product_fr`
   - **id** (INTEGER, Primary Key): Unique product identifier (same as in `product_en` for matching products).
   - **name** (TEXT): Product name in French.
   - **description** (TEXT): Product description in French.

**Example Data in Each Table**

- **Table `product_en`**:

| id  | name      | description                      |
|-----|-----------|----------------------------------|
| 1   | Laptop    | A portable computer              |
| 2   | Smartphone| A handheld communication device  |

- **Table `product_fr`**:

| id  | name              | description                       |
|-----|-------------------|-----------------------------------|
| 1   | Ordinateur portable | Un ordinateur portable         |
| 2   | Téléphone intelligent | Un appareil de communication portable |

**Advantages**:
- Separate tables simplify SQL queries for each language.
- Each language can be managed or updated independently.

**Disadvantages**:
- Additional management required to synchronize product IDs across tables.
- Expanding to new languages requires creating new tables for each language.

---

### Approach 2: Single Table with Columns for Each Language

This approach stores all language data in a single table. Each product has a single record, with separate columns for the name and description in each language.

**Database Schema for Single Table**

- **Table**: `product`
   - **id** (INTEGER, Primary Key): Unique product identifier.
   - **name_en** (TEXT): Product name in English.
   - **description_en** (TEXT): Product description in English.
   - **name_fr** (TEXT): Product name in French.
   - **description_fr** (TEXT): Product description in French.

**Example Data in Single Table**

| id  | name_en      | description_en                      | name_fr              | description_fr                     |
|-----|--------------|-------------------------------------|----------------------|------------------------------------|
| 1   | Laptop       | A portable computer                 | Ordinateur portable  | Un ordinateur portable             |
| 2   | Smartphone   | A handheld communication device     | Téléphone intelligent| Un appareil de communication portable |

**Advantages**:
- All language data stored in a single table, reducing the need for multiple joins.
- Simplifies schema management as there is only one table to update when adding new products.

**Disadvantages**:
- Not as scalable if there are many languages, as the table will grow horizontally with additional columns.
- Data retrieval requires conditional logic based on language selection.

---

## Workflow in the Application

1. **Application Start**:
   - The JavaFX application starts, displaying the language selection ComboBox, load button, and an empty table.

2. **Language Selection**:
   - The user selects a language (e.g., "English" or "French") from the ComboBox.

3. **Loading Products**:
   - When the user clicks **Load Products**, the application retrieves product data from the appropriate table (in Approach 1) or columns (in Approach 2) based on the selected language.
   - The database query dynamically targets the correct table or columns, depending on the language chosen.

4. **Displaying Data**:
   - The TableView is populated with products in the selected language, showing `id`, `name`, and `description` fields.

---

## Submition 

- Add the github repor link and the screen shots of the interface in oma
