# Understanding (DBMS) and MySQL

## Table of Contents

1. [Introduction to DBMS](#introduction-to-dbms)
2. [Role of DBMS](#role-of-dbms)
3. [Key Features of DBMS](#key-features-of-dbms)
4. [Popular DBMS Examples](#popular-dbms-examples)
5. [SQL: The Common Language](#sql-the-common-language)
6. [Advantages of DBMS](#advantages-of-dbms)
7. [Constraints and Security](#constraints-and-security)
8. [Types of Database Management Systems (DBMS)](#types-of-database-management-systems-dbms)
9. [Different Ways to Store Data](#different-ways-to-store-data)
10. [Types of DBMS by Data Structure](#types-of-dbms-by-data-structure)
11. [Relational Database Management Systems (RDBMS)](#relational-database-management-systems-rdbms)
12. [Installing MySQL and Using the MySQL Console](#installing-mysql-and-using-the-mysql-console)
13. [Accessing the MySQL Console](#accessing-the-mysql-console)
14. [Imperative vs. Declarative Programming](#imperative-vs-declarative-programming)
15. [Basic MySQL Commands](#basic-mysql-commands)
16. [Practical Example](#practical-example)

## Introduction to DBMS

A **Database Management System (DBMS)** is a software layer that sits between applications and the stored database. It provides the necessary tools and interfaces to manage and interact with the database efficiently.

## Role of DBMS

- **Data Storage**: The data in databases is stored in files, and the DBMS manages access to these files.
- **Interface Layer**: Acts as an intermediary between end-users or applications and the database.
- **Query Processing**: Provides software to process queries and retrieve data.
- **Data Management**: A collection of programs that manage the database, ensuring smooth data retrieval and storage.

## Key Features of DBMS

- **Easy Data Access**: Allows users to query, process, access, add, update, and delete data efficiently.
- **Data Integrity**: Ensures that the data stored is accurate and consistent.
- **Concurrency Control**: Manages simultaneous access to the database by multiple users.
- **Security**: Implements measures to protect data from unauthorized access.
- **Backup and Recovery**: Provides mechanisms for data backup and recovery.

## Popular DBMS Examples

- **MySQL**: An open-source relational database management system.
- **PostgreSQL (pgSQL)**: An advanced, open-source relational database known for its extensibility and standards compliance.
- **SQLite**: A lightweight, self-contained SQL database engine.

## SQL: The Common Language

- **Structured Query Language (SQL)**: The standard language used to interact with relational databases.
- **Compatibility**: Most DBMSs understand and use SQL, although implementations may vary slightly.
- **Operations**: SQL allows for creating, reading, updating, and deleting (CRUD) data in the database.

## Advantages of DBMS

- **Reduced Redundancy**: Eliminates duplicate data, saving storage space.
- **Consistency**: Ensures that all users see the same data.
- **Scalability**: Supports the development of large, scalable applications.
- **Complex Architectures**: Facilitates the creation of complex and modern applications.
- **Data Sharing**: Enables easy sharing of data among multiple users and applications.
- **Backup and Recovery**: Provides robust mechanisms for data backup and recovery.

## Constraints and Security

- **Data Constraints**: Allows setting rules for data entry, such as specifying that a value must be an integer or a string of a certain length.
- **Security Measures**: Implements access controls and encryption to protect data from unauthorized access and breaches.

# Types of Database Management Systems (DBMS)

## Different Ways to Store Data
- DBMS systems store data in various structural forms
- The storage model varies based on the type of DBMS

## Types of DBMS by Data Structure
- **Tabular form**: Data stored in tables with rows and columns
- **Key-value pairs**: Data stored as associated pairs of keys and values
- **Document-based**: Data stored as documents (often in formats like JSON)

## Relational Database Management Systems (RDBMS)
- One of the most important and widely used types of DBMS
- Stores data in the form of tables
- **Example**: MySQL is a popular RDBMS

### Structure of RDBMS
1. **Tables**: Each table represents an entity
   - Example entities: Actors, Theaters, Movies

2. **Columns**: Represent properties/attributes of the entities
   - For Actors table: name, age, gender, etc.

3. **Rows**: Each row represents a unique entity instance (actual data)
   - A single actor with their specific attributes

### Data Operations in RDBMS
- **New data**: Creates a new row
- **New property**: Creates a new column
- **New entity type**: Creates a new table

### The "Relational" in RDBMS
- Tables are related to each other through relationships
- **Example**: Actors table is related to Movies table
- These relationships connect the data across tables
- Core-coupled data (data with many relationships) works well with RDBMS

# Installing MySQL and Using the MySQL Console

## Installing MySQL

To install MySQL on Windows, you can follow these steps:

1. **Medium Articles**: Search for "top medium articles mysql installation windows" to find detailed guides.
2. **YouTube Tutorials**: Search for "mysql installation windows youtube" to find video tutorials.

## Accessing the MySQL Console

### REPL Consoles

- **REPL**: Read-Eval-Print Loop, an interactive programming environment.
- **Examples**: Browser consoles for JavaScript, MySQL console for SQL commands.
- **Usage**: Allows you to input commands and see the output immediately.

### Steps to Access MySQL Console

1. **Open Command Prompt or Git Bash**:
   ```sh
   C:\Users\mad> mysql --version
   ```

2. **Log in to MySQL**:
   ```sh
   C:\Users\mad> mysql -u root -p
   ```
   - Enter your username and password when prompted.

3. **MySQL Console**:
   - You will be inside the MySQL console, ready to execute SQL commands.

## Imperative vs. Declarative Programming

- **Imperative Programming**: Specifies a sequence of steps to achieve a goal (e.g., JavaScript, Java, C, C++).
- **Declarative Programming**: Specifies the desired outcome, and the system handles the steps (e.g., SQL).
- **MySQL**: Uses declarative programming; you specify what you want, and MySQL handles the execution.

## Basic MySQL Commands

### Showing Databases

- **Command**:
  ```sql
  SHOW DATABASES;
  ```
  - Lists all databases in the MySQL server.

### Clearing the Console

- **Command**:
  ```sql
  \! clear
  ```
  - Clears the console screen.

- **List Files**:
  ```sql
  \! ls
  ```
  - Lists files in the current directory.

### Creating a Database

- **Command**:
  ```sql
  CREATE DATABASE FILMSDATABASE;
  ```
  - Creates a new database named `FILMSDATABASE`.

### Dropping a Database

- **Command**:
  ```sql
  DROP DATABASE FILMSDATABASE;
  ```
  - Deletes the database named `FILMSDATABASE`.

### Creating a Table

1. **Select Database**:
   ```sql
   USE FILMSDATABASE;
   ```
   - Ensures that subsequent commands are executed in the `FILMSDATABASE` context.

2. **Create Table**:
   ```sql
   CREATE TABLE MOVIES (NAME VARCHAR(50), RATING INT);
   ```
   - Creates a table named `MOVIES` with columns `NAME` (string) and `RATING` (integer).

### Describing a Table

- **Command**:
  ```sql
  DESC MOVIES;
  ```
  - Displays the structure of the `MOVIES` table, including column names and data types.

## Practical Example

### Creating and Managing a Database

1. **Create Database**:
   ```sql
   CREATE DATABASE UniversityDB;
   ```

2. **Select Database**:
   ```sql
   USE UniversityDB;
   ```

3. **Create Tables**:
   ```sql
   CREATE TABLE Students (
       StudentID INT PRIMARY KEY,
       Name VARCHAR(100),
       Age INT,
       Major VARCHAR(50)
   );

   CREATE TABLE Courses (
       CourseID INT PRIMARY KEY,
       CourseName VARCHAR(100),
       Instructor VARCHAR(100)
   );

   CREATE TABLE Enrollments (
       EnrollmentID INT PRIMARY KEY,
       StudentID INT,
       CourseID INT,
       FOREIGN KEY (StudentID) REFERENCES Students(StudentID),
       FOREIGN KEY (CourseID) REFERENCES Courses(CourseID)
   );
   ```