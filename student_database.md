# Student Database Schema

## Department Table

```sql
CREATE TABLE Department (
    DepartmentID INT AUTO_INCREMENT PRIMARY KEY,
    Department_Name VARCHAR(100) NOT NULL,
    Faculty VARCHAR(100) NOT NULL
);
```

## Students Table

```sql
CREATE TABLE students (
    RegNo INT AUTO_INCREMENT PRIMARY KEY,
    FirstName VARCHAR(50) NOT NULL,
    LastName VARCHAR(50) NOT NULL,
    Gender VARCHAR(10),
    DepartmentID INT,
    Level INT,
    Email VARCHAR(100),
    FOREIGN KEY (DepartmentID) REFERENCES Department(DepartmentID)
);
```

## Insert Statement

```sql
INSERT INTO Students(
FirstName, Name, Gender, Department,
Level, Email)
VALUES('emmanuel', 'njoku', 'male', 'computerscience', '500', 'njokuemmanuel541@gmail.com'
);
```

