# student Management system
A comprehensive desktop application for managing student records built with Java, JDBC, MySQL, and Swing GUI. This system provides a user-friendly interface for performing CRUD (Create, Read, Update, Delete) operations on student data.

Problem Statement
Educational institutions face challenges in efficiently managing student information, including enrollment details, academic records, and personal information. Manual record-keeping is time-consuming, error-prone, and difficult to maintain. This Student Management System addresses these challenges by providing a centralized, digital solution for storing, retrieving, updating, and managing student data efficiently.

Objectives
Develop a robust database-driven application for student record management
Implement CRUD operations with an intuitive graphical user interface
Ensure data integrity and security through proper database design
Provide search and filter functionality for quick data retrieval
Apply object-oriented programming principles and MVC architecture
Demonstrate practical implementation of JDBC for database connectivity
Features
Add Student: Register new students with complete details including enrollment number, personal information, course details, and academic performance
View Students: Display all student records in a tabular format with sortable columns
Update Student: Modify existing student information with real-time validation
Delete Student: Remove student records with confirmation prompts
Search Functionality: Search students by name or enrollment number
Status Management: Track student status (Active/Inactive)
Data Validation: Input validation for dates, CGPA, and required fields
Responsive GUI: Clean and intuitive Swing-based user interface
Technologies Used
Technology	Purpose
Java SE	Core programming language
JDBC (Java Database Connectivity)	Database connection and operations
MySQL	Relational database management system
Swing	GUI framework for desktop application
Eclipse IDE	Development environment
Git/GitHub	Version control and collaboration
System Architecture
The application follows the MVC (Model-View-Controller) pattern:

Model: Student.java - Represents student entity with all attributes
DAO (Data Access Object): StudentDAO.java - Handles all database operations
Controller/View: StudentManagementGUI.java - Manages UI and user interactions
Utility: DatabaseConnection.java - Manages database connectivity
Database Schema
Students Table Structure
CREATE TABLE students ( student_id INT PRIMARY KEY AUTO_INCREMENT, enrollment_no VARCHAR(20) UNIQUE NOT NULL, name VARCHAR(100) NOT NULL, email VARCHAR(100), phone VARCHAR(15), date_of_birth DATE, gender ENUM('Male', 'Female', 'Other'), address TEXT, course VARCHAR(50), semester INT, cgpa DECIMAL(4,2), admission_date DATE, status ENUM('Active', 'Inactive') DEFAULT 'Active', created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP );

Installation and Setup
Prerequisites
Java JDK 8 or higher
MySQL Server 5.7 or higher
Eclipse IDE (or any Java IDE)
MySQL Connector/J (JDBC Driver)
Step-by-Step Installation
1. Clone the Repository

git clone https://github.com/aditichoudhary2712/StudentManagementSystem.git
cd StudentManagementSystem
2. Database Setup

Open MySQL Workbench and execute:

-- Create database CREATE DATABASE student_management_db; USE student_management_db;

-- Create table CREATE TABLE students ( student_id INT PRIMARY KEY AUTO_INCREMENT, enrollment_no VARCHAR(20) UNIQUE NOT NULL, name VARCHAR(100) NOT NULL, email VARCHAR(100), phone VARCHAR(15), date_of_birth DATE, gender ENUM('Male', 'Female', 'Other'), address TEXT, course VARCHAR(50), semester INT, cgpa DECIMAL(4,2), admission_date DATE, status ENUM('Active', 'Inactive') DEFAULT 'Active', created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP );

-- Insert sample data (optional) INSERT INTO students (enrollment_no, name, email, phone, date_of_birth, gender, address, course, semester, cgpa, admission_date) VALUES ('21BCE0001', 'Rahul Sharma', 'rahul@vit.ac.in', '9876543210', '2003-05-15', 'Male', 'Mumbai', 'BTech CSE', 3, 8.50, '2021-08-01'), ('21BCE0002', 'Priya Singh', 'priya@vit.ac.in', '9876543211', '2003-07-20', 'Female', 'Delhi', 'BTech CSE', 3, 7.80, '2021-08-01');

3. Configure Database Connection

Update credentials in DatabaseConnection.java:

private static final String URL = "jdbc:mysql://localhost:3306/student_management_db"; private static final String USER = "root"; // Your MySQL username private static final String PASSWORD = ""; // Your MySQL password

4. Add MySQL Connector to Project

Download MySQL Connector/J from: https://dev.mysql.com/downloads/connector/j/
In Eclipse: Right-click project → Build Path → Configure Build Path → Libraries → Add External JARs
Select the downloaded mysql-connector-j-x.x.x.jar file
5. Run the Application

Open StudentManagementGUI.java
Right-click → Run As → Java Application
How to Use
Adding a New Student
Fill in all required fields in the left panel
Enter dates in YYYY-MM-DD format (e.g., 2003-05-15)
Click Add button
Student will be added to the database and displayed in the table
Updating Student Information
Click on a student row in the table to select
Modify the fields as needed
Click Update button
Changes will be saved to the database
Deleting a Student
Select a student from the table
Click Delete button
Confirm deletion in the popup dialog
Searching Students
Enter student name or enrollment number in the search box
Click Search button
Matching results will be displayed
Refreshing Data
Click Refresh button to reload all student records from the database
Project Structure
StudentManagementSystem/ │ ├── src/ │ └── com/ │ └── student/ │ └── management/ │ ├── DatabaseConnection.java # Database connectivity │ ├── Student.java # Student model class │ ├── StudentDAO.java # Database operations │ └── StudentManagementGUI.java # GUI application │ ├── lib/ │ └── mysql-connector-j-8.x.x.jar # JDBC driver │ ├── screenshots/ # Application screenshots ├── recordings/ # Demo videos (if any) └── README.md # Project documentation
