# Student Management System

A comprehensive desktop application for managing student records built with Java, JDBC, MySQL, and Swing GUI. This system provides a user-friendly interface for performing CRUD (Create, Read, Update, Delete) operations on student data.

## Problem Statement

Educational institutions face challenges in efficiently managing student information, including enrollment details, academic records, and personal information. Manual record-keeping is time-consuming, error-prone, and difficult to maintain. This Student Management System addresses these challenges by providing a centralized, digital solution for storing, retrieving, updating, and managing student data efficiently.

## Objectives

- Develop a robust database-driven application for student record management
- Implement CRUD operations with an intuitive graphical user interface
- Ensure data integrity and security through proper database design
- Provide search and filter functionality for quick data retrieval
- Apply object-oriented programming principles and MVC architecture
- Demonstrate practical implementation of JDBC for database connectivity

## Features

- **Add Student**: Register new students with complete details including enrollment number, personal information, course details, and academic performance
- **View Students**: Display all student records in a tabular format with sortable columns
- **Update Student**: Modify existing student information with real-time validation
- **Delete Student**: Remove student records with confirmation prompts
- **Search Functionality**: Search students by name or enrollment number
- **Status Management**: Track student status (Active/Inactive)
- **Data Validation**: Input validation for dates, CGPA, and required fields
- **Responsive GUI**: Clean and intuitive Swing-based user interface

## Technologies Used

| Technology | Purpose |
|------------|---------|
| **Java SE** | Core programming language |
| **JDBC (Java Database Connectivity)** | Database connection and operations |
| **MySQL** | Relational database management system |
| **Swing** | GUI framework for desktop application |
| **Eclipse IDE** | Development environment |
| **Git/GitHub** | Version control and collaboration |

## System Architecture

The application follows the **MVC (Model-View-Controller)** pattern:

- **Model**: `Student.java` - Represents student entity with all attributes
- **DAO (Data Access Object)**: `StudentDAO.java` - Handles all database operations
- **Controller/View**: `StudentManagementGUI.java` - Manages UI and user interactions
- **Utility**: `DatabaseConnection.java` - Manages database connectivity

## Database Schema

### Students Table Structure

CREATE TABLE students (
student_id INT PRIMARY KEY AUTO_INCREMENT,
enrollment_no VARCHAR(20) UNIQUE NOT NULL,
name VARCHAR(100) NOT NULL,
email VARCHAR(100),
phone VARCHAR(15),
date_of_birth DATE,
gender ENUM('Male', 'Female', 'Other'),
address TEXT,
course VARCHAR(50),
semester INT,
cgpa DECIMAL(4,2),
admission_date DATE,
status ENUM('Active', 'Inactive') DEFAULT 'Active',
created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);



## Installation and Setup

### Prerequisites

- Java JDK 8 or higher
- MySQL Server 5.7 or higher
- Eclipse IDE (or any Java IDE)
- MySQL Connector/J (JDBC Driver)

### Step-by-Step Installation

**1. Clone the Repository**

```
git clone https://github.com/aditichoudhary2712/StudentManagementSystem.git
cd StudentManagementSystem
```


**2. Database Setup**

Open MySQL Workbench and execute:

-- Create database
CREATE DATABASE student_management_db;
USE student_management_db;

-- Create table
CREATE TABLE students (
student_id INT PRIMARY KEY AUTO_INCREMENT,
enrollment_no VARCHAR(20) UNIQUE NOT NULL,
name VARCHAR(100) NOT NULL,
email VARCHAR(100),
phone VARCHAR(15),
date_of_birth DATE,
gender ENUM('Male', 'Female', 'Other'),
address TEXT,
course VARCHAR(50),
semester INT,
cgpa DECIMAL(4,2),
admission_date DATE,
status ENUM('Active', 'Inactive') DEFAULT 'Active',
created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Insert sample data (optional)
INSERT INTO students (enrollment_no, name, email, phone, date_of_birth, gender, address, course, semester, cgpa, admission_date)
VALUES
('21BCE0001', 'Rahul Sharma', 'rahul@vit.ac.in', '9876543210', '2003-05-15', 'Male', 'Mumbai', 'BTech CSE', 3, 8.50, '2021-08-01'),
('21BCE0002', 'Priya Singh', 'priya@vit.ac.in', '9876543211', '2003-07-20', 'Female', 'Delhi', 'BTech CSE', 3, 7.80, '2021-08-01');


**3. Configure Database Connection**

Update credentials in `DatabaseConnection.java`:

private static final String URL = "jdbc:mysql://localhost:3306/student_management_db";
private static final String USER = "root"; // Your MySQL username
private static final String PASSWORD = ""; // Your MySQL password


**4. Add MySQL Connector to Project**

- Download MySQL Connector/J from: https://dev.mysql.com/downloads/connector/j/
- In Eclipse: Right-click project → Build Path → Configure Build Path → Libraries → Add External JARs
- Select the downloaded `mysql-connector-j-x.x.x.jar` file

**5. Run the Application**

- Open `StudentManagementGUI.java`
- Right-click → Run As → Java Application

## How to Use

### Adding a New Student

1. Fill in all required fields in the left panel
2. Enter dates in `YYYY-MM-DD` format (e.g., 2003-05-15)
3. Click **Add** button
4. Student will be added to the database and displayed in the table

### Updating Student Information

1. Click on a student row in the table to select
2. Modify the fields as needed
3. Click **Update** button
4. Changes will be saved to the database

### Deleting a Student

1. Select a student from the table
2. Click **Delete** button
3. Confirm deletion in the popup dialog

### Searching Students

1. Enter student name or enrollment number in the search box
2. Click **Search** button
3. Matching results will be displayed

### Refreshing Data

- Click **Refresh** button to reload all student records from the database

## Project Structure

StudentManagementSystem/
│
├── src/
│ └── com/
│ └── student/
│ └── management/
│ ├── DatabaseConnection.java # Database connectivity
│ ├── Student.java # Student model class
│ ├── StudentDAO.java # Database operations
│ └── StudentManagementGUI.java # GUI application
│
├── lib/
│ └── mysql-connector-j-8.x.x.jar # JDBC driver
│
├── screenshots/ # Application screenshots
├── recordings/ # Demo videos (if any)
└── README.md # Project documentation


## Screenshots

*Screenshots of application*

Main Interface
<img width="1480" height="859" alt="image" src="https://github.com/user-attachments/assets/e5f6be46-d9d8-430e-af98-77e581242936" />

<img width="1919" height="1021" alt="image" src="https://github.com/user-attachments/assets/4434250f-36e5-40bb-869b-e9e0b0bc2f13" />


## Development Process

This project was developed following a structured software development approach:

1. **Problem Definition**: Identified the need for efficient student record management
2. **Requirement Analysis**: Defined functional and non-functional requirements
3. **Database Design**: Created normalized database schema
4. **System Design**: Designed class diagrams and application architecture
5. **Implementation**: Developed modules incrementally (Model → DAO → GUI)
6. **Testing**: Performed unit testing and integration testing
7. **Documentation**: Created comprehensive README and code comments

## Challenges Faced

- **Database Connectivity**: Resolved JDBC driver configuration issues
- **Date Formatting**: Implemented proper date parsing and validation
- **GUI Responsiveness**: Optimized table refresh and data loading
- **Input Validation**: Added comprehensive error handling for user inputs


## Learning Outcomes

Through this project, I gained hands-on experience with:

- JDBC API for database connectivity and operations
- Java Swing for building desktop GUI applications
- MySQL database design and SQL query optimization
- MVC design pattern implementation
- Exception handling and input validation
- Git version control and GitHub collaboration
- Software development lifecycle and best practices

## Academic Information

**Course**: Flipped Course Project  
**Institution**: VIT Bhopal University  
**Submission Deadline**: November 25, 2025  
**Domain**: Education & Technology  

## Author

**Name: Arnav Singhal**  
**Reg No: 24BSA10023**

**BTech Computer Science Engineering**  
**VIT Bhopal University**  

GitHub:  arnavsinghal006-star
Repository: README.md

## License

This project is developed for academic purposes as part of coursework at VIT Bhopal University.

## Acknowledgments

- Dr. Mayuri AVR, Associate Professor, School of Computing Science and Engineering
- VIT Bhopal University for providing the learning platform
- MySQL and Oracle for comprehensive documentation
- Open-source community for valuable resources and tutorials

---

**Note**: This project demonstrates practical application of database management, object-oriented programming, and GUI development concepts learned during the course.
