# Ex. No: 5 Creating Cursors using PL/SQL

### AIM: To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:

### Create employee table
CREATE TABLE employees (empid NUMBER,empname VARCHAR(10),dept
VARCHAR(10),salary NUMBER);
INSERT INTO employees VALUES (1, 'leo das', 'ceo', 100000);
INSERT INTO employees VALUES (2, 'nixan dass', 'HR', 90000);
### PLSQL Cursor code
DECLARE
CURSOR employees_cursor IS
SELECT empid,empname,dept,salary
FROM employees;
emp_id NUMBER;
emp_name VARCHAR2(50);
emp_dept VARCHAR2(50);
Preview Code Blame Raw
Output:
Result:
emp_salary NUMBER;
BEGIN
OPEN employees_cursor;
LOOP
FETCH employees_cursor INTO
emp_id,emp_name,emp_dept,emp_salary;
EXIT WHEN employees_cursor%NOTFOUND;
DBMS_OUTPUT.PUT_LINE('Employee ID: ' || emp_id);
DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name);
DBMS_OUTPUT.PUT_LINE('Department: ' || emp_dept);
DBMS_OUTPUT.PUT_LINE('Salary: ' || emp_salary);
DBMS_OUTPUT.PUT_LINE('--------------------------');
END LOOP;
CLOSE employees_cursor;
END;
### Output:
![image](https://github.com/dineshgl/Ex-6-Creating-Cursors-using-PL-SQL/assets/118668751/e3a881db-b7a2-4091-90e0-0e2839be75f1)

### Result:
THE PROGRAM WAS EXECUTED SUCCESSFULLY
