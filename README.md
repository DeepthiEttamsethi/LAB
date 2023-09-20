# Employee Performance  System

## [About Employee Performance ](https://github.com/markdown-it/markdown-it-sub) 

The Employee Performance Management System is a console-based Java application that facilitates the tracking and management of employee performance evaluations within an organization. It allows administrators to add employee details, record evaluation data, update evaluation records, and view employee performance information.

## [Features ](https://github.com/markdown-it/markdown-it-sub) 


### User Authentication
Users can log in using a username and password. The system validates the login credentials against a MySQL database.

### Add Employee Details
Administrators can add new employee information, including name, email, gender, hire date, designation, salary, and mobile number.

### Add Evaluation Details
Administrators can record evaluation details for employees, such as evaluation date, rating, and feedback.

### Update Evaluation Details
Administrators can update existing evaluation records, allowing changes to evaluation date, rating, and feedback.

### Delete Employee
Administrators can remove employee records from the database based on the employee's ID.

### Delete Evaluation Details
Administrators can delete specific evaluation records by providing the evaluation ID.

### Display Employee Performance
The system allows administrators to view a list of employee performance details, including employee ID, name, email, evaluation date, rating, and feedback.

### Exit
Users can gracefully exit the application.


## [Getting the project](https://github.com/markdown-it/markdown-it-sub) 
To get and run this project, follow these 
steps


### Prerequisites

#### Java Development Kit (JDK)

Ensure you have Java JDK (Java Development Kit) installed on your system.

#### MySQL Database:
Set up a MySQL database to store employee and evaluation data. You should have MySQL installed and running.

#### MySQL JDBC Driver:
Download and include the MySQL JDBC driver in your project.

## [Project Setup ](https://github.com/markdown-it/markdown-it-sub) 
#### Clone or Download:
Clone or download the project source code from the repository.

#### Create the Database:
Create the "empperf" database in MySQL using a tool like phpMyAdmin or the MySQL command line

    CREATE DATABASE empperf;
#### Create Database Tables:

Set up the necessary database tables using the provided SQL commands in the Java code comments.


##### Login:

    CREATE TABLE LOGIN(Id INT PRIMARY KEY, USERNAME VARCHAR(30), PASSWORD VARCHAR(30));

##### Employee:

    CREATE TABLE Employee (
    Id INT AUTO_INCREMENT PRIMARY KEY,
    Name VARCHAR(50) NOT NULL,
    Email VARCHAR(40) NOT NULL,
    Gender VARCHAR(20) CHECK (Gender = 'Male' OR Gender = 'Female'),
    Hiredate DATETIME NOT NULL,
    Designation VARCHAR(40) NOT NULL,
    Salary FLOAT NOT NULL,
    Mobileno VARCHAR(15) NOT NULL);

##### Evaluation:
    CREATE TABLE Evaluation (Id INT AUTO_INCREMENT PRIMARY KEY, EvaluationDate DATETIME NOT NULL, Rating FLOAT NOT NULL, Feedback VARCHAR(100) NOT NULL, FOREIGN KEY (Id) REFERENCES Employee(Id));

#### Update Database Connection:
Update the database connection details in the Java code to match your MySQL configuration:


    conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/empperf", "root", "root");

#### Compile and Run:
Compile and run the Java application to start using the Employee Performance Management System.

#### Menu:
Utilize the menu options to interact with the system, either as an administrator or employee.


This is a basic console-based application. In a production environment, you would need to enhance security, implement error handling, and potentially create a graphical user interface (GUI) for a more user-friendly experience.
