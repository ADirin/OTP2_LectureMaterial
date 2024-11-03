# Creating a Java Application with MongoDB in IntelliJ IDEA

This guide will help you set up a Java application that connects to a MongoDB database using IntelliJ IDEA.

## Prerequisites

- **Java Development Kit (JDK)**: Make sure you have JDK installed (Java 8 or higher recommended).
- **IntelliJ IDEA**: Download and install IntelliJ IDEA Community Edition from [JetBrains](https://www.jetbrains.com/idea/download/).
- **MongoDB**: Download and install MongoDB Community Server from [MongoDB Download Center](https://www.mongodb.com/try/download/community).
- **MongoDB Driver**: This will be added in the project setup.

## Step 1: Install MongoDB

1. Download the MongoDB installer for your operating system.
2. Follow the installation instructions specific to your OS:
   - For **Windows**, use the MSI installer.
   - For **macOS**, you can use Homebrew: `brew tap mongodb/brew && brew install mongodb-community`.
   - For **Linux**, follow the instructions for your distribution.
3. After installation, start MongoDB:
   - **Windows**: Run `mongod` in Command Prompt.
   - **macOS/Linux**: Open a terminal and run `mongod`.

## Step 2: Set Up Your Java Project in IntelliJ IDEA

1. Open IntelliJ IDEA.
2. Click on `New Project`.
3. Select `Java` from the left panel, then select your JDK.
4. Click `Next`, then name your project (e.g., `MongoDBJavaApp`).
5. Click `Finish`.

## Step 3: Add MongoDB Dependency

1. Open the `pom.xml` file (for Maven projects).
2. Add the following MongoDB driver dependency inside the `<dependencies>` tag:

```xml
   <dependency>
       <groupId>org.mongodb</groupId>
       <artifactId>mongodb-driver-sync</artifactId>
       <version>4.8.0</version> <!-- Check for the latest version -->
   </dependency>
```
## Step 4: Create a MongoDB Database and Collection
1. Open a terminal and run the MongoDB shell by typing mongo.
2. Create a new database:

```javascript
use myDatabase

```
3. Create a new collection (e.g., users):
```javascript
db.createCollection("users")

```
4. Insert a sample document into the users collection:
```javascript
db.users.insertOne({ name: "John Doe", age: 30, email: "john.doe@example.com" })
```
## Step 5: Write Java Code to Connect to MongoDB
1. In IntelliJ IDEA, create a new Java class (e.g., MongoDBApp.java).
2. Write the following code to connect to MongoDB and retrieve data:

```java
import com.mongodb.MongoClient;
import com.mongodb.MongoClientURI;
import com.mongodb.client.MongoCollection;
import com.mongodb.client.MongoDatabase;
import org.bson.Document;

public class MongoDBApp {
    public static void main(String[] args) {
        // Connect to MongoDB
        MongoClientURI uri = new MongoClientURI("mongodb://localhost:27017");
        MongoClient mongoClient = new MongoClient(uri);
        MongoDatabase database = mongoClient.getDatabase("myDatabase");
        MongoCollection<Document> collection = database.getCollection("users");

        // Fetch and print all documents in the collection
        for (Document doc : collection.find()) {
            System.out.println(doc.toJson());
        }

        // Close the client
        mongoClient.close();
    }
}

```
## Step 6: Run Your Application
1. In IntelliJ IDEA, right-click on MongoDBApp.java and select Run 'MongoDBApp.main()'.
2. You should see the output in the console displaying the document(s) you inserted earlier.
