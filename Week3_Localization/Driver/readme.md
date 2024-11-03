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
