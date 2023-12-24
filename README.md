# coded-task

Your job is to create a back end of task manager that will allow users to manage their things to do.

## Prerequisistes
1. You have to download [MySQL](https://dev.mysql.com/downloads/workbench/)
2. You need Java JDK and Maven
3. An HTTP client such as [Postman](https://www.postman.com/downloads/)

## Create the project:
The easiest way to create a new project is to use the spring project starter website: start.spring.io.
We need three dependencies:
* The Spring Web: Build web, including RESTful. Uses Apache Tomcat as the default embedded container.
* The Spring Data JPA: Persist data in SQL stores with Java Persistence API using Spring Data and Hibernate.
* MySQL Driver for Java: The MySQL driver makes it possible to interact with a database from a Java application.

## Requirements:
1. Create MySql database with table of the following schema:

 ![image](https://github.com/MohammedHydr/coded-task/assets/93540731/e566afd3-3d3c-4124-83df-9d91c870817e)

2. Create a Spring Boot application that provides the following RESTful endpoints:

![image](https://github.com/MohammedHydr/coded-task/assets/93540731/6d5ebd8e-d342-48bc-891a-e2e1be2b5497)

* POST /tasks
  * Purpose: Add a new task to the system.
  * Details: Accept a JSON object containing task information and store it.

* GET /tasks
  * Purpose: List all tasks.
  * Details: Retrieve and display a list of all tasks stored.

* GET /tasks/{id}
  * Purpose: Get details of a specific task.
  * Details: Fetch and show a single task by its ID.

* PUT /tasks/{id}
  * Purpose: Update an existing task.
  * Details: Modify a task's details using its ID.

* DELETE /tasks/{id}
  * Purpose: Remove a task from the system.
  * Details: Delete the task associated with the provided ID.

* Guidelines:
  * Use an ArrayList to store tasks in memory.
  * Each task should have an ID, title, and description.
  * Assume that the ID is automatically generated.
  * No database or UI is required; focus on the backend logic.

* Expected Output:
  * When testing your endpoints through a tool like Postman, you should be able to create, retrieve, update, and delete tasks.

## Structuring the code:
1. Create a package named entities then create a class called Task to store the argements of the tasks.
2. configure the application to connect to the database and perform database table creation (Hibernate under the hood). Open the application configuration file src/resources/application.properties
3. Note: Set the value of the property spring.jpa.hibernate.ddl-auto to validate after the tables are created to prevent them from being deleted and then re-created when starting the application
4. Create a package called repositories then create a file TaskRepository.java (The JPA repository for an entity acts as the interface between our application entity and the database. It will be responsible for transforming CRUD operations to SQL queries to execute against the database.)
5. Create a package called services then create a file TaskService.java (The service for an entity is where to write the business logic. If there are any requirements to be met before creating/updating a task, they are expressed here.)
6. Create a package called controllers then a file called TaskController.java
