# SQL Exercise with HarryPotter Data

Exercise: SQL_exercise_data\
https://docs.google.com/spreadsheets/d/1ZVKyKP-xmVeXDzbRzprdKfE5g2c6XrSrscbUqYuXPoI/edit?usp=sharing


## Solution: SQL exercise
### 1. Write a statement that will select the grade column from Student table

    SELECT grade
    FROM Student;

### 2. Select all records from Student table where school_code column has the value “GF”

    SELECT *
    FROM Student
    WHERE school_code = "GF";

### 3. Select all records from Student table and sort result alphabetically by column pass_fail

    SELECT *
    FROM Student
    ORDER BY pass_fail DESC;

    OR
    
    SELECT *
    FROM Student
    ORDER BY pass_fail ASC;

### 4. List school code, average math, average reading and average writing score group by school code from Student table

    SELECT school_code, 
    ROUND(AVG(math),2) as avg_math, 
    ROUND(AVG(reading),2) as avg_reading, 
    ROUND(AVG(writing),2) as avg_writing
    FROM Student
    GROUP BY school_code;

### 5. Select all records from Student table order by grades (A, B, C, D, F)

    SELECT *
    FROM Student
    ORDER BY grade;

### 6. Write a statement that will select school name, average math, average reading and average writing score from Student table and group by school name from School table

    SELECT school, 
    ROUND(AVG(math),2) as avg_math, 
    ROUND(AVG(reading),2) as avg_reading, 
    ROUND(AVG(writing),2) as avg_writing
    FROM Student as st
    JOIN School as sc
    ON st.school_code = sc.school_code
    GROUP BY school;
