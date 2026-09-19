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

> **Note:** The `INSERT` statement above doesn't match the `students` table exactly as defined:
> - The table name is `students`, not `Students` (MySQL is case-insensitive for table names on most systems, but worth aligning).
> - The columns listed are `FirstName, Name, Gender, Department, Level, Email`, but the table has `FirstName, LastName, Gender, DepartmentID, Level, Email` — there's no `Name` or `Department` column, and `DepartmentID` is an `INT` foreign key, not a department name string like `'computerscience'`.
> - A corrected version would look like:
>
> ```sql
> INSERT INTO students (
>     FirstName, LastName, Gender, DepartmentID, Level, Email
> )
> VALUES (
>     'emmanuel', 'njoku', 'male', 1, 500, 'njokuemmanuel541@gmail.com'
> );
> ```
> (assuming `DepartmentID = 1` corresponds to Computer Science in the `Department` table, and `Level` is an `INT` so `500` shouldn't be quoted.)
