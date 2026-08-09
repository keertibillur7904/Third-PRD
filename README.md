1. Project Description
Colleges need a simple way to check a student's marks, attendance, and fee status.

In this project, you will build CampusTrack, a basic Student Result Management System. The program will accept the details of one student, calculate the result, and display a final semester report.

The project handles only one student during one program execution. It does not require a database, file storage, arrays, methods, or object-oriented programming.

2. Programming Task
Create a Java console program that:

Reads the student's basic details.
Uses a menu to select the course.
Accepts marks for three subjects.
Validates marks using loops.
Calculates total marks and average.
Checks whether the student passed every subject.
Assigns a grade using if-else-if.
Checks the student's attendance.
Calculates the pending semester fee.
Produces the final semester status.
Displays a clear student report.
3. Concepts Used
Required concepts
Java program structure
Variables and primitive data types
String
Scanner
Arithmetic operators
Relational and logical operators
if, else if, and else
switch
Ternary operator
while loop for validation
print, println, and printf
Concepts not allowed
Arrays
Collections
User-defined methods
Additional classes
Constructors
Exception handling
File handling
Database connectivity
Inheritance
Streams and lambda expressions
GUI or web development
Write the complete program inside the main method.

FR-01: Display the Welcome Screen
Display the following heading:

==================================================
                 CAMPUSTRACK
==================================================
        Simple Student Result Management System
--------------------------------------------------
FR-02: Read Student Details
Collect the following information:

Field	Data type	Rule
Student ID	String	Read as a single word
Student name	String	Read the complete name
Age	int	Must be from 16 to 30
Sample input
Enter student ID: STU101
Enter student name: Ananya Rao
Enter age: 20
Complete-name requirement
The student name may contain spaces. Use nextLine() to read the complete name.

After reading the student ID using next(), consume the pending newline before reading the name.

Correct value:

Student name: Ananya Rao
Incorrect value:

Student name:
Age validation
The age must be between 16 and 30, inclusive. If the entered age is invalid, use a while loop to request it again.

Enter age: 14
Invalid age. Enter a value between 16 and 30.
Enter age: 20
FR-03: Select the Course
Display this menu:

Select Course
1. BCA
2. B.Sc Computer Science
3. B.E/B.Tech
The course choice must be between 1 and 3. Use a while loop to request the value again when it is invalid.

Use a switch statement to assign the course name and semester fee.

Choice	Course	Semester fee
1	BCA	₹30,000
2	B.Sc Computer Science	₹35,000
3	B.E/B.Tech	₹50,000
Sample input
Enter course choice: 3
Course selected: B.E/B.Tech
Semester fee: ₹50000.00
Invalid choice example
Enter course choice: 5
Invalid course choice. Enter a value from 1 to 3.
Enter course choice: 2
Course selected: B.Sc Computer Science
FR-04: Read Subject Marks
Collect marks for exactly three subjects:

Java
SQL
Aptitude
Each mark must be between 0 and 100, inclusive.

Use three separate variables:

javaMarks
sqlMarks
aptitudeMarks
Do not use an array.

Sample input
Enter Java marks: 78
Enter SQL marks: 72
Enter Aptitude marks: 65
Marks validation
Use a while loop for each mark.

Enter Java marks: 120
Invalid marks. Enter a value between 0 and 100.
Enter Java marks: -5
Invalid marks. Enter a value between 0 and 100.
Enter Java marks: 78
FR-05: Calculate Total and Average
Calculate:

Total marks = Java marks + SQL marks + Aptitude marks
Average = Total marks / 3.0
Use 3.0 so that decimal division takes place.

Display the average with two decimal places.

Example
Java marks     : 78
SQL marks      : 72
Aptitude marks : 65
Total marks    : 215/300
Average        : 71.67
FR-06: Determine the Academic Result
The pass mark for each subject is 35.

The student passes the academic requirement only when:

Java marks >= 35
AND SQL marks >= 35
AND Aptitude marks >= 35
Use a compound condition to check all three marks.

Assign:

PASSED
or:

FAILED
Important rule
A high average must not hide a failed subject.

Example:

Java marks     : 90
SQL marks      : 30
Aptitude marks : 90
Average        : 70.00
Academic Result: FAILED
The student fails because SQL marks are below 35.

FR-07: Determine the Grade
Use an if-else-if ladder.

Condition	Grade
Student failed any subject	F
Average is 75 or above	A
Average is 60 to 74.99	B
Average is 50 to 59.99	C
Average is below 50	D
First check whether the student failed any subject. If yes, the grade must be F even when the average is high.

FR-08: Check Attendance
Read the attendance percentage as a double.

Valid range:

0 to 100
Use a while loop to request the value again when it is outside this range.

The attendance requirement is satisfied when:

Attendance >= 75
Use a ternary operator to assign:

SUFFICIENT
or:

SHORTAGE
Example
Enter attendance percentage: 82
Attendance status: SUFFICIENT
FR-09: Calculate the Fee Balance
The semester fee is already decided by the selected course.

Read the amount paid by the student.

The paid amount must be:

0 or more
AND not greater than the semester fee
Use a while loop when the value is invalid.

Calculate:

Fee balance = Semester fee - Fee paid
Use a ternary operator to assign the fee status:

Fee balance == 0 ? "CLEARED" : "PENDING"
Example
Semester fee : ₹50000.00
Enter fee paid: 40000
Fee balance  : ₹10000.00
Fee status   : PENDING
FR-10: Determine the Final Semester Status
The final semester status is CLEARED only when all three conditions are true:

Academic result is PASSED
AND attendance is at least 75
AND fee balance is 0
Use a ternary operator to assign:

SEMESTER CLEARED
or:

SEMESTER NOT CLEARED
FR-11: Display Exact Reasons
When the final status is SEMESTER NOT CLEARED, display the exact reason or reasons.

Possible reasons:

Java marks are below 35.
SQL marks are below 35.
Aptitude marks are below 35.
Attendance is below 75%.
Semester fee is pending.
Use separate if statements so that every applicable reason is displayed.

Example:

Reasons:
- SQL marks are below 35.
- Attendance is below 75%.
