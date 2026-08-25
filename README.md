<h1 align="center">🗃️ Task 2 – SQL Queries</h1>
<p align="center"><b>Machine Learning Internship – Hunar Intern</b></p>

📌 Project Overview
This repository contains my completed submission for Problem 2 of the Machine Learning Internship Assignment offered by Hunar Intern.

The objective of this task is to create a Student and Course database, insert sample records, and perform SQL queries to extract meaningful information from the database. [file:2]

✅ Task Highlights
🗄️ Created a database for student and course records.

📚 Created Student and Course tables.

🔗 Used a primary key and foreign key relationship.

✍️ Inserted sample student and course data.

🔍 Retrieved records using SELECT queries.

📊 Used filtering, sorting, aggregate functions, grouping, and joins.

🎓 Displayed student details along with their enrolled courses.

🛠️ Technologies Used
Tool	Purpose
MySQL	Database management system
SQL	Creating tables and retrieving data
MySQL Workbench / phpMyAdmin	Executing and testing queries
📁 Files Included
File Name	Description
problem_2_sql.sql	SQL script containing table creation, data insertion, and queries
README.md	Documentation for the project
⚙️ Requirements
MySQL Server or another SQL-compatible database system.

MySQL Workbench, phpMyAdmin, or a similar SQL editor.

▶️ How to Run
Open MySQL Workbench or another SQL editor.

Open the problem_2_sql.sql file.

Execute the complete script.

Run the queries individually to view their results.

💻 SQL Code
1. Create the Database
sql
CREATE DATABASE StudentCourseDB;

USE StudentCourseDB;
2. Create the Course Table
sql
CREATE TABLE Course (
    course_id INT PRIMARY KEY,
    course_name VARCHAR(100) NOT NULL,
    duration_months INT NOT NULL,
    fees DECIMAL(10, 2) NOT NULL
);
3. Create the Student Table
sql
CREATE TABLE Student (
    student_id INT PRIMARY KEY,
    student_name VARCHAR(100) NOT NULL,
    age INT,
    gender VARCHAR(10),
    email VARCHAR(100) UNIQUE,
    course_id INT,
    marks DECIMAL(5, 2),
    FOREIGN KEY (course_id) REFERENCES Course(course_id)
);
4. Insert Data into the Course Table
sql
INSERT INTO Course
(course_id, course_name, duration_months, fees)
VALUES
(101, 'Machine Learning', 6, 25000.00),
(102, 'Data Science', 8, 35000.00),
(103, 'Web Development', 5, 20000.00),
(104, 'Artificial Intelligence', 10, 45000.00);
5. Insert Data into the Student Table
sql
INSERT INTO Student
(student_id, student_name, age, gender, email, course_id, marks)
VALUES
(1, 'Aarav Sharma', 20, 'Male', 'aarav@example.com', 101, 87.50),
(2, 'Priya Verma', 21, 'Female', 'priya@example.com', 102, 92.00),
(3, 'Rohan Gupta', 19, 'Male', 'rohan@example.com', 103, 76.00),
(4, 'Ananya Singh', 22, 'Female', 'ananya@example.com', 104, 95.00),
(5, 'Vivek Kumar', 20, 'Male', 'vivek@example.com', 101, 81.50);
🔍 SQL Queries Performed
Display all students
sql
SELECT * FROM Student;
Display all courses
sql
SELECT * FROM Course;
Display students who scored more than 80 marks
sql
SELECT student_id, student_name, marks
FROM Student
WHERE marks > 80;
Display female students
sql
SELECT *
FROM Student
WHERE gender = 'Female';
Display students in alphabetical order
sql
SELECT *
FROM Student
ORDER BY student_name ASC;
Display students with their course names
sql
SELECT
    Student.student_id,
    Student.student_name,
    Course.course_name,
    Student.marks
FROM Student
INNER JOIN Course
ON Student.course_id = Course.course_id;
Find the average marks of all students
sql
SELECT AVG(marks) AS average_marks
FROM Student;
Find the highest marks
sql
SELECT MAX(marks) AS highest_marks
FROM Student;
Find the lowest marks
sql
SELECT MIN(marks) AS lowest_marks
FROM Student;
Count the total number of students
sql
SELECT COUNT(*) AS total_students
FROM Student;
Count students enrolled in each course
sql
SELECT
    Course.course_name,
    COUNT(Student.student_id) AS number_of_students
FROM Course
LEFT JOIN Student
ON Course.course_id = Student.course_id
GROUP BY Course.course_id, Course.course_name;
Display students enrolled in Machine Learning
sql
SELECT
    Student.student_name,
    Student.email,
    Student.marks
FROM Student
INNER JOIN Course
ON Student.course_id = Course.course_id
WHERE Course.course_name = 'Machine Learning';
Display courses with fees greater than ₹25,000
sql
SELECT *
FROM Course
WHERE fees > 25000;
Find the student with the highest marks
sql
SELECT student_name, marks
FROM Student
WHERE marks = (
    SELECT MAX(marks)
    FROM Student
);
Search for students whose names begin with “A”
sql
SELECT *
FROM Student
WHERE student_name LIKE 'A%';
📤 Example Output
The student-course join query produces output similar to this:

Student ID	Student Name	Course	Marks
1	Aarav Sharma	Machine Learning	87.50
2	Priya Verma	Data Science	92.00
3	Rohan Gupta	Web Development	76.00
4	Ananya Singh	Artificial Intelligence	95.00
5	Vivek Kumar	Machine Learning	81.50
The student with the highest marks is Ananya Singh, with 95.00 marks.

🧠 Concepts Used
CREATE DATABASE and USE

CREATE TABLE

Primary keys and foreign keys

INSERT INTO

SELECT statements

WHERE filtering

ORDER BY sorting

INNER JOIN and LEFT JOIN

Aggregate functions: AVG(), MAX(), MIN(), and COUNT()

GROUP BY

Subqueries

Pattern matching using LIKE

💡 What I Learned
How to design a simple relational database.

How to create tables with appropriate constraints.

How to establish relationships between tables using foreign keys.

How to retrieve specific information using SQL queries.

How to combine records from multiple tables using joins.

How to summarize data using aggregate functions.

How databases can organize and support machine learning data workflows.

🔗 Social Sharing
🎥 I have also recorded a short video walkthrough of my solution and posted it on LinkedIn.

Feel free to connect and view the project there:

🔗 https://www.linkedin.com/in/raghavendra-challapalli-234a2231b?utm_source=share_via&utm_content=profile&utm_medium=member_android

🏷️ Tags
#HunarIntern #HunarTech #MachineLearning #SQL #MySQL #Database #Python #InternshipProject

<p align="center">✨ Thank you for visiting ✨</p>
