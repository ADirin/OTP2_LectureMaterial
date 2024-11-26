# Software Engineering Documentation Template for Students (Your project final Report, group work)

This template provides a basic structure for documentation based on the type of software engineering project. It is designed to guide you in creating thorough, organized, and clear documentation for your software project.

````mermaid
flowchart TD
    A[Software Project Documentation] --> B[Project Overview]
    A --> C[Design & Architecture]
    A --> D[Development]
    A --> E[Testing]
    A --> F[Deployment]
    A --> G[Maintenance]

    B --> B1[Project Description]
    B --> B2[Objectives]

    C --> C1[System Design]
    C --> C2[Architecture Diagrams]

    D --> D1[Code Structure]

    E --> E1[Test Plan]

    F --> F1[Deployment Process]

    G --> G1[Bug Tracking]

````

## Instructions for Using the Template:

*This document should cover both courses SEP1 and SEP2*
- Fill in the sections as they apply to your project.
- Make sure the documentation is **clear**, **concise**, and **up-to-date**.
- Customize the sections based on the specific type of software project you are working on.
- If certain sections do not apply, feel free to omit them or leave them blank.
- Include diagrams, code snippets, and links to external resources as necessary.
- Include your group member's name and the hours spend during each sprint
- Include the repository and Trello links, and add the link of your solutions if it is online.
  
---

# 1. **Project Overview**
Provide an introduction to your project, including its purpose, goals, and scope. Describe the problem you're solving and how your software addresses it.

### Example:
- **Project Name**: My Cool Web Application
- **Description**: A web application designed to help users manage their daily tasks and increase productivity.
- **Goals**: Simplify task management through an intuitive user interface.
- **Scope**: This project includes user registration, task creation, due dates, and notifications.

---

# 2. **System Architecture**
Describe the overall architecture of the system, including key components and how they interact. Include any software tools, platforms, or frameworks used.

### Example:
- **Architecture Type**: Client-Server architecture with RESTful API
- **Components**:
  - Frontend: React.js for the user interface.
  - Backend: Node.js with Express for server-side logic.
  - Database: MongoDB for data storage.
- **External Services**: Firebase for authentication.

### Diagram:
Include a diagram (e.g., a flowchart or UML diagram) that illustrates how the system components interact.

---

# 3. **Technologies Used**
List all the technologies, programming languages, frameworks, and tools used in the project. 

### Example:
- **Frontend**: HTML, CSS, JavaScript, React.js
- **Backend**: Node.js, Express.js
- **Database**: MongoDB
- **Authentication**: Firebase Auth
- **Version Control**: Git, GitHub
-  **CI/CD**: Jenkins
-  **Virtual Environment**: Docker, VM

---

# 4. **Software Design**
Provide detailed descriptions of the system's design, including major classes, functions, and algorithms. Describe the rationale behind design choices.

### Example:
- **User Authentication Flow**: Users can log in using Google Authentication through Firebase. On successful login, a token is generated, which is used for secure access to user-specific data.
- **Task Management**: Users can create, edit, and delete tasks. Tasks are stored in MongoDB with fields for title, description, due date, and status.

---

# 5. **Database Schema**
Explain the database structure, including tables/collections, fields, and relationships between data.

### Example:
- **Users Collection**:
  - `_id` (ObjectId)
  - `name` (String)
  - `email` (String, unique)
  - `password` (String)
- **Tasks Collection**:
  - `_id` (ObjectId)
  - `user_id` (ObjectId, reference to Users collection)
  - `title` (String)
  - `description` (String)
  - `due_date` (Date)
  - `status` (String: "pending", "completed")

---

# 6. **API Documentation**
Document the API endpoints provided by the backend. Include method types (GET, POST, PUT, DELETE), endpoint descriptions, parameters, and responses.

### Example:

#### **POST /api/users/login**
- **Description**: Log in a user using their email and password.
- **Request Body**:
```json
  {
    "email": "user@example.com",
    "password": "password123"
  }
````
- **Response: **
````json
{
  "status": "success",
  "token": "jwt_token_here"
}
````
- **Status Codes**
  - 200: Success
  - 400: Invalid input
  - 401: Unauthorized

# 7. **Testing Strategy**
Describe the testing approach for the project, including unit tests, integration tests, and user acceptance testing. Explain the tools and frameworks used for testing.

**Example:**
  - Unit Testing: Jest for testing individual functions and components.
  - Coverage Testing
  - Integration Testing: Postman for testing API endpoints.
  - User Acceptance Testing: Manual testing by project team members and feedback from real users.
    
# 8. **Deployment Process**
Explain the steps required to deploy the software to a production environment, including setting up servers, databases, and any third-party services.

**Example:**
  - Step 1: Push code to GitHub.
  - Step 2: Deploy frontend to Netlify.
  - Step 3: Deploy backend to Heroku.
  - Step 4: Set up MongoDB Atlas for database hosting.

# 9. **User Documentation**
Provide guidance for end-users on how to interact with your software. Include installation steps, usage instructions, and troubleshooting tips.

**Example:**
- **Installation:**
  1. Clone the repository.
  2. Run npm install to install dependencies.
  3. Set up environment variables (.env file).
  4. Run npm start to launch the application.
- **Usage:**
    - Create Task: Click the "Create Task" button and fill in the required fields.
    - Mark Task as Completed: Check the box next to a task to mark it as completed.

# 10. **Maintenance plan**

# 11. **Conclusion**
Summarize the goals achieved by the project and its impact. Discuss any challenges faced during development and areas for improvement in future iterations.

**Example:**
  - Challenges: Integration of Firebase Auth was difficult due to conflicting dependencies.
  - Future Improvements: Add email reminders for tasks and implement dark mode.

-----------------------------------

# Submision
  - Upload the document as a PDF into designated folder in Oma after the final presentation (09.12.2024 at 23.59)
  - *NOTE*: Add the project repository and Trello links to the project document.

