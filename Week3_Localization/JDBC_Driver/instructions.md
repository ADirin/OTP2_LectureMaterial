# Adding JDBC Driver in Maven Project in IntelliJ

Here’s a quick guide to adding a JDBC driver to your Maven project in IntelliJ IDEA. There are multiple ways to accomplish this, depending on your project setup and preferences.

## Solution 1: Add JDBC Dependency in `pom.xml`

1. **Open `pom.xml`:** Locate the `pom.xml` file in your project root.
2. **Add Dependency:** Inside the `<dependencies>` section, add the JDBC dependency for the database you are using. Here are some examples:

   - **MySQL:**
     ```xml
     <dependency>
         <groupId>mysql</groupId>
         <artifactId>mysql-connector-java</artifactId>
         <version>8.0.33</version>
     </dependency>
     ```
   - **PostgreSQL:**
     ```xml
     <dependency>
         <groupId>org.postgresql</groupId>
         <artifactId>postgresql</artifactId>
         <version>42.3.1</version>
     </dependency>
     ```

3. **Sync Dependencies:** After adding, IntelliJ may prompt you to import changes or re-sync. Click on **Reload Maven** (or **Reload All Maven Projects**) on the Maven tool window or the notification that appears.

## Solution 2: Add Dependency Using IntelliJ’s Maven Tool Window

1. **Open the Maven Tool Window:** Go to **View > Tool Windows > Maven** (or use **Alt + F12**).
2. **Search for JDBC Driver:** In the **Maven Tool Window**, look for **Dependencies**. You can right-click and add a new dependency, or use the **+** icon.
3. **Enter Dependency Information:** Enter the `groupId`, `artifactId`, and `version` of the JDBC driver. For example, for MySQL:
   - **groupId**: `mysql`
   - **artifactId**: `mysql-connector-java`
   - **version**: `8.0.33`
4. **Reload Project:** Click **Reload Maven** to update dependencies in the project.

## Solution 3: Manually Add Driver JAR and Link in `pom.xml`

If the driver is not available in a Maven repository, you can add it manually:

1. **Download JDBC JAR:** Download the JDBC driver `.jar` file for your database from the vendor’s website.
2. **Add JAR to Project Structure:** Copy the `.jar` to a `libs` folder within your project directory.
3. **Edit `pom.xml`:** In your `pom.xml`, specify the driver as a system-scoped dependency, referencing the path where you stored it:
   ```xml
   <dependency>
       <groupId>com.example</groupId>
       <artifactId>your-jdbc-driver</artifactId>
       <version>1.0</version>
       <scope>system</scope>
       <systemPath>${project.basedir}/libs/your-jdbc-driver.jar</systemPath>
   </dependency>
-------------------------------------

# Manually Adding JDBC Driver as a Library in IntelliJ IDEA

## Step 1: Download the JDBC Driver

1. **Download the JDBC Driver:**
   - Go to the official website of your database (e.g., MySQL, PostgreSQL, Oracle) and download the JDBC driver `.jar` file.
   - Save the `.jar` file to a known location on your filesystem.

## Step 2: Create a Library in IntelliJ

1. **Open IntelliJ IDEA.**
2. **Go to Project Structure:**
   - Click on `File` in the menu bar.
   - Select `Project Structure` (or use the shortcut `Ctrl + Alt + Shift + S`).
3. **Add a New Library:**
   - In the `Project Structure` window, navigate to the **Libraries** section.
   - Click the **+** icon (or **Add** button) to add a new library.
   - Choose **Java** from the dropdown menu.
4. **Select the JDBC Driver JAR:**
   - In the dialog that appears, locate and select the JDBC driver `.jar` file you downloaded.
   - Click **OK** to add the library.
5. **Specify Library Name (Optional):**
   - Optionally, you can rename the library to something descriptive (like "MySQL JDBC Driver" or "PostgreSQL JDBC Driver").

## Step 3: Associate the Library with Your Project

1. **Select Your Module:**
   - In the `Project Structure` window, click on the **Modules** section on the left panel.
   - Select the module where you want to use the JDBC driver.
2. **Add Library to Module:**
   - Click on the **Dependencies** tab for the selected module.
   - Click the **+** icon (or **Add** button) and select **Library**.
   - From the list, choose the library you just created and click **OK**.

## Step 4: Confirm and Apply Changes

1. **Confirm Changes:**
   - Review your changes to ensure the library is correctly added to your module.
2. **Apply Changes:**
   - Click the **Apply** button, then **OK** to close the `Project Structure` window.

## Step 5: Using the JDBC Driver in Your Code

Now you can use the JDBC driver in your Java code. Here’s a simple example of how to connect to a MySQL database:

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

public class MySQLConnection {
    public static void main(String[] args) {
        String url = "jdbc:mysql://localhost:3306/mydatabase";
        String user = "myusername";
        String password = "mypassword";

        try {
            Connection connection = DriverManager.getConnection(url, user, password);
            System.out.println("Connection successful!");
            connection.close();
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
---------------------------
# Manually Adding JDBC Driver as a Library in IntelliJ IDEA

## Step 1: Download the JDBC Driver

1. **Download the JDBC Driver:**
   - Go to the official website of your database (e.g., MySQL, PostgreSQL, Oracle) and download the JDBC driver `.jar` file.
   - Save the `.jar` file to a known location on your filesystem.

## Step 2: Create a Library in IntelliJ

1. **Open IntelliJ IDEA.**
2. **Go to Project Structure:**
   - Click on `File` in the menu bar.
   - Select `Project Structure` (or use the shortcut `Ctrl + Alt + Shift + S`).
3. **Add a New Library:**
   - In the `Project Structure` window, navigate to the **Libraries** section.
   - Click the **+** icon (or **Add** button) to add a new library.
   - Choose **Java** from the dropdown menu.
4. **Select the JDBC Driver JAR:**
   - In the dialog that appears, locate and select the JDBC driver `.jar` file you downloaded.
   - Click **OK** to add the library.
5. **Specify Library Name (Optional):**
   - Optionally, you can rename the library to something descriptive (like "MySQL JDBC Driver" or "PostgreSQL JDBC Driver").

## Step 3: Associate the Library with Your Project

1. **Select Your Module:**
   - In the `Project Structure` window, click on the **Modules** section on the left panel.
   - Select the module where you want to use the JDBC driver.
2. **Add Library to Module:**
   - Click on the **Dependencies** tab for the selected module.
   - Click the **+** icon (or **Add** button) and select **Library**.
   - From the list, choose the library you just created and click **OK**.

## Step 4: Confirm and Apply Changes

1. **Confirm Changes:**
   - Review your changes to ensure the library is correctly added to your module.
2. **Apply Changes:**
   - Click the **Apply** button, then **OK** to close the `Project Structure` window.

## Step 5: Add JDBC Settings in IntelliJ

1. **Open Database Tool Window:**
   - Go to `View` > `Tool Windows` > `Database`.
2. **Add a New Data Source:**
   - Click the **+** icon in the Database tool window.
   - Choose your database type (e.g., MySQL, PostgreSQL).
3. **Configure the Data Source:**
   - Enter the necessary connection details, including the JDBC URL, username, and password.
   - If prompted, select the JDBC driver you added earlier.
4. **Test the Connection:**
   - Click the **Test Connection** button to ensure that the settings are correct.
   - Once successful, click **OK** to save the data source.

## Step 6: Install Plugins (If Necessary)

1. **Open Plugin Settings:**
   - Click on `File` in the menu bar and select `Settings` (or use `Ctrl + Alt + S`).
2. **Navigate to Plugins:**
   - In the Settings window, click on **Plugins** in the left panel.
3. **Browse Repositories:**
   - Click on the **Marketplace** tab to search for JDBC-related plugins (e.g., Database Navigator).
4. **Install a Plugin:**
   - Find the desired plugin and click **Install**.
   - Restart IntelliJ IDEA if prompted.

## Step 7: Using the JDBC Driver in Your Code

Now you can use the JDBC driver in your Java code. Here’s a simple example of how to connect to a MySQL database:

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

public class MySQLConnection {
    public static void main(String[] args) {
        String url = "jdbc:mysql://localhost:3306/mydatabase";
        String user = "myusername";
        String password = "mypassword";

        try {
            Connection connection = DriverManager.getConnection(url, user, password);
            System.out.println("Connection successful!");
            connection.close();
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
