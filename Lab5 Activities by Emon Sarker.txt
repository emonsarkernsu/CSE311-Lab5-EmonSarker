Activity 1
-----------------------------------
SELECT emps.Last_Name, emps.Hire_Date
FROM emps
WHERE emps.Department_Id = (SELECT emps.Department_Id
                	    FROM emps
                	    WHERE emps.Last_Name ="Zlotkey")
AND emps.Last_Name != "Zlotkey";


Activity 2
-----------------------------------
SELECT emps.Employee_Id, emps.Last_Name, emps.Salary
FROM emps
WHERE emps.Salary > (SELECT AVG(emps.Salary)
                     FROM emps)
ORDER BY (emps.Salary) ASC;


Activity 3
----------------------------------
SELECT emps.Last_Name, emps.Salary
FROM emps
WHERE emps.Manager_id = (SELECT emps.Employee_Id
                         FROM emps
                         WHERE emps.Last_Name = "King");

Activity 4
-----------------------------------
SELECT emps.Employee_Id,emps.Last_Name,emps.Salary 
FROM emps 
WHERE salary > (SELECT AVG(salary)
		FROM emps) 
AND Last_Name LIKE "%u%";

Activity 5
-----------------------------------
CREATE TABLE emp_new (
    id INT(4) NOT NULL PRIMARY KEY,
    firstName VARCHAR(20),
    lastName VARCHAR(20)
    );

INSERT INTO emp_new (id, firstName, lastName)
VALUES (301, "Emon", "Sarker"),
(302, "Parinda", "Rahman"),
(303, "Tahrima", "Ihsan");

INSERT INTO emp_new(id, firstName, lastName)
SELECT emps.Employee_Id, emps.First_Name, emps.Last_Name
FROM emps;

Activity 6
-----------------------------------
CREATE TABLE EMP(ID Int(7), LAST_NAME Varchar(25), FIRST_NAME Varchar(25), DEPT_ID Int(7));

a) ALTER TABLE EMP
MODIFY LAST_NAME Varchar(30);

b) CREATE TABLE EMPLOYEES2(ID int(6), FIRST_NAME Varchar(20), LAST_NAME Varchar(25), SALARY decimal(8,2), DEPT_ID int(4));

c) DROP TABLE EMP;

d) RENAME TABLE EMPLOYEES2 TO EMP;

e) ALTER TABLE emp 
DROP COLUMN FIRST_NAME;