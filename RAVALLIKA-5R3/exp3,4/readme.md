#experiment 3 and 4
```
CREATE TABLE employees (
    employee_id NUMBER(5),
    first_name VARCHAR2(20),
    last_name VARCHAR2(20),
    gender CHAR(1),
    job_id VARCHAR2(15),
    department VARCHAR2(30),
    salary NUMBER(8,2),
    commission NUMBER(5,2),
    hire_date DATE,
    city VARCHAR2(20)
);

INSERT INTO employees VALUES
(101, 'John', 'Smith', 'M', 'IT_PROG', 'IT', 65000, 5,
TO_DATE('15-JAN-2020', 'DD-MON-YYYY'), 'Hyderabad');

INSERT INTO employees VALUES
(102, 'Anita', 'Sharma', 'F', 'HR_REP', 'HR', 52000, 3,
TO_DATE('10-JUN-2019', 'DD-MON-YYYY'), 'Bengaluru');

INSERT INTO employees VALUES
(103, 'Rahul', 'Kumar', 'M', 'SA_REP', 'Sales', 48000, 8,
TO_DATE('25-AUG-2021', 'DD-MON-YYYY'), 'Chennai');

INSERT INTO employees VALUES
(104, 'Priya', 'Reddy', 'F', 'MK_MAN', 'Marketing', 72000, 10,
TO_DATE('05-MAR-2018', 'DD-MON-YYYY'), 'Hyderabad');

INSERT INTO employees VALUES
(105, 'David', 'Wilson', 'M', 'FI_ACCOUNT', 'Finance', 58000, NULL,
TO_DATE('18-DEC-2017', 'DD-MON-YYYY'), 'Mumbai');

INSERT INTO employees VALUES
(106, 'Sneha', 'Patel', 'F', 'IT_PROG', 'IT', 69000, 6,
TO_DATE('12-NOV-2022', 'DD-MON-YYYY'), 'Pune');

INSERT INTO employees VALUES
(107, 'Amit', 'Verma', 'M', 'SA_REP', 'Sales', 45000, 4,
TO_DATE('20-JUL-2023', 'DD-MON-YYYY'), 'Delhi');

INSERT INTO employees VALUES
(108, 'Kiran', 'Rao', 'M', 'HR_REP', 'HR', 50000, NULL,
TO_DATE('09-FEB-2021', 'DD-MON-YYYY'), 'Hyderabad');

INSERT INTO employees VALUES
(109, 'Lakshmi', 'Nair', 'F', 'IT_PROG', 'IT', 76000, 7,
TO_DATE('14-SEP-2016', 'DD-MON-YYYY'), 'Kochi');


INSERT INTO employees VALUES
(110, 'Arjun', 'Singh', 'M', 'MK_MAN', 'Marketing', 68000, 5,
TO_DATE('30-APR-2019', 'DD-MON-YYYY'), 'Jaipur');
```
![op](o1.png)
![op](o2.png)
```

SELECT employee_id, first_name,
TO_CHAR(hire_date, 'DD-MON-YYYY')
FROM employees;
```
![op](o3.png)
```
SELECT employee_id, first_name,
TO_CHAR(salary, '$99,999.99')
FROM employees;
```
![op](o4.png)
```

SELECT employee_id, first_name,
TO_NUMBER(TO_CHAR(salary)) + 5000
FROM employees;
```
![op](o5.png)
```
SELECT *
FROM employees
WHERE hire_date > TO_DATE('01-JAN-2020', 'DD-MON-YYYY');
```
![op](o6.png)
```
SELECT first_name || ' ' || last_name
FROM employees;
```
![op](o7.png)
```
SELECT CONCAT(first_name, last_name)
FROM employees;
```
![op](o8.png)
```

SELECT LPAD(first_name, 20, '*')
FROM employees;
```
![op](o9.png)
```


SELECT RPAD(first_name, 20, '*')
FROM employees;
```
![op](o10.png)
```
SELECT LTRIM(first_name)
FROM employees;
```
![op](o11.png)
```
SELECT RTRIM(first_name)
FROM employees;
```
![op](o12.png)
```

SELECT LOWER(first_name)
FROM employees;
```
![op](o13.png)
```

SELECT UPPER(first_name)
FROM employees;
```
![op](o14.png)
```

SELECT INITCAP(first_name)
FROM employees;
```
![op](o15.png)
```

SELECT first_name, LENGTH(first_name)
FROM employees;
```
![op](o16.png)
```
SELECT first_name, SUBSTR(first_name, 1, 3)
FROM employees;
```
![op](o26.png)
```
SELECT first_name, INSTR(first_name, 'a')
FROM employees;
```
![op](o17.png)
```

SELECT employee_id, first_name, last_name, SYSDATE
FROM employees;
```
![op](o18.png)
```
SELECT first_name, hire_date,
NEXT_DAY(hire_date, 'MONDAY')
FROM employees;
```
![op](o19.png)
```
SELECT first_name, hire_date,
ADD_MONTHS(hire_date, 6)
FROM employees;
```
![op](o20.png)
```
SELECT first_name, hire_date,
LAST_DAY(hire_date)
FROM employees;
```
![op](o21.png)
```

SELECT first_name,
MONTHS_BETWEEN(SYSDATE, hire_date)
FROM employees;
```
![op](o22.png)
```
SELECT first_name, salary,
LEAST(salary, 60000)
FROM employees;
```
![op](o23.png)
```

SELECT first_name, salary,
GREATEST(salary, 60000)
FROM employees;
```
![op](o24.png)
```
SELECT first_name, hire_date,
TRUNC(hire_date, 'MONTH')
FROM employees;
```
![op](o25.png)
```
SELECT first_name, hire_date,
ROUND(hire_date, 'MONTH')
FROM employees;
```
![op](o27.png)
```
SELECT first_name,
TO_CHAR(hire_date, 'DAY, DD-MON-YYYY')
FROM employees;
```
![op](o28.png)
```
SELECT *
FROM employees
WHERE hire_date < TO_DATE('01-JAN-2019', 'DD-MON-YYYY');
```
![op](o29.png)


#EXPERIMENT 3B
```
select *from employees;
CREATE VIEW emp_view AS
SELECT *
FROM employees;
```
![op](p1.png)
```
CREATE VIEW emp_basic AS
SELECT employee_id, first_name, last_name, department, salary
FROM employees;
```
![op](p2.png)
```
SELECT *
FROM emp_view;
```
![op](p3.png)
```
CREATE VIEW it_employees AS
SELECT *
FROM employees
WHERE department = 'IT';
```
![op](p4.png)
```
CREATE VIEW high_salary AS
SELECT *
FROM employees
WHERE salary > 60000;
```
![op](p5.png)
```
CREATE VIEW hyderabad_emp AS
SELECT *
FROM employees
WHERE city = 'Hyderabad';
```
![op](p6.png)
```
CREATE VIEW female_emp AS
SELECT *
FROM employees
WHERE gender = 'F';
```
![op](p7.png)
```
CREATE VIEW recent_employees AS
SELECT *
FROM employees
WHERE hire_date >= TO_DATE('01-JAN-2020', 'DD-MON-YYYY');
```
![op](p8.png)
```
SELECT employee_id, first_name, salary
FROM high_salary;
```
![op](p9.png)
```
CREATE OR REPLACE VIEW emp_basic AS
SELECT employee_id, first_name, last_name, department, salary, city
FROM employees;
```
![op](p10.png)
```
CREATE VIEW emp_salary_view AS
SELECT employee_id, first_name, last_name, salary
FROM employees
WITH READ ONLY;
```
![op](p11.png)
```
CREATE VIEW sales_emp AS
SELECT *
FROM employees
WHERE department = 'Sales'
WITH CHECK OPTION;
```
![op](p12.png)
```
UPDATE emp_basic
SET salary = 70000
WHERE employee_id = 101;
```
![op](p13.png)
```
DELETE FROM emp_view
WHERE employee_id = 107;
```
![op](p14.png)
```
INSERT INTO emp_basic
(employee_id, first_name, last_name, department, salary, city)
VALUES
(111, 'Ravi', 'Kumar', 'IT', 55000, 'Hyderabad');
```
![op](p15.png)
```
DESC emp_basic;
```
![op](p16.png)
```
SELECT *
FROM it_employees;
```
![op](p17.png)
```

SELECT *
FROM high_salary
WHERE salary > 70000;
```
![op](p18.png)
```
SELECT *
FROM female_emp;
```
![op](p19.png)
```
SELECT first_name, salary
FROM hyderabad_emp;
```
![op](p20.png)
```
DROP VIEW emp_view;
```
![op](p21.png)
```
DROP VIEW high_salary;
```
![op](p22.png)
```

DROP VIEW emp_basic;
```
![op](p23.png)
```
CREATE VIEW hr_employees AS
SELECT *
FROM employees
WHERE department = 'HR';
```
![op](p24.png)
```
CREATE VIEW marketing_emp AS
SELECT employee_id, first_name, department, salary
FROM employees
WHERE department = 'Marketing';
```
![op](p25.png)
```
CREATE VIEW top_earners AS
SELECT *
FROM employees
WHERE salary > 70000;
```
![op](p26.png)
```

CREATE VIEW emp_city AS
SELECT employee_id, first_name, last_name, city
FROM employees;
```
![op](p27.png)

#experiment 4
```
CREATE TABLE dept (
    dno NUMBER(5),
    dname VARCHAR2(20)
);
```
![op](1.png)
```
ALTER TABLE dept
ADD CONSTRAINT dept_pk PRIMARY KEY (dno);

ALTER TABLE dept
MODIFY dname CONSTRAINT dept_dname_nn NOT NULL;
```
![op](2.png)
```
CREATE TABLE student (
    sid NUMBER(5),
    sname VARCHAR2(30),
    did NUMBER(5)
);
```

![op](3.png)
```
ALTER TABLE student
ADD CONSTRAINT student_pk PRIMARY KEY (sid);

ALTER TABLE student
MODIFY sname CONSTRAINT student_sname_nn NOT NULL;

ALTER TABLE student
ADD CONSTRAINT student_dept_fk
FOREIGN KEY (did)
REFERENCES dept(dno);
```
![op](4.png)
```
INSERT INTO dept VALUES (1, 'CSE');
INSERT INTO dept VALUES (2, 'ME');
INSERT INTO dept VALUES (3, 'CE');
INSERT INTO dept VALUES (4, 'EEE');
INSERT INTO dept VALUES (5, 'ECE');
INSERT INTO dept VALUES (6, 'CSM');
INSERT INTO dept VALUES (7, 'CSD');
```
![op](5.png)
```
INSERT INTO student VALUES (101, 'Ravi', 1);
INSERT INTO student VALUES (102, 'Sita', 1);
INSERT INTO student VALUES (103, 'Rahul', 2);
INSERT INTO student VALUES (104, 'Priya', 3);
INSERT INTO student VALUES (105, 'Arjun', 4);
INSERT INTO student VALUES (106, 'Sneha', 5);
INSERT INTO student VALUES (107, 'Kiran', 6);
INSERT INTO student VALUES (108, 'Anita', 7);
INSERT INTO student VALUES (109, 'Ramesh', 1);
INSERT INTO student VALUES (110, 'Lakshmi', 5);
```
![op](5.png)
![op](6.png)
```
SELECT *
FROM student
NATURAL JOIN
(SELECT dno AS did, dname FROM dept);
```
![op](i1.png)
```

SELECT *
FROM student s, dept d
WHERE s.did = d.dno;
```
![op](i2.png)
```
SELECT *
FROM student s
JOIN dept d
ON s.did = d.dno;
```
![op](i3.png)
```
SELECT *
FROM student
NATURAL LEFT OUTER JOIN
(SELECT dno AS did, dname FROM dept);
```
![op](i4.png)
```
SELECT *
FROM student
NATURAL RIGHT OUTER JOIN
(SELECT dno AS did, dname FROM dept);
```
![op](i5.png)
```
SELECT *
FROM student
NATURAL FULL OUTER JOIN
(SELECT dno AS did, dname FROM dept);
```
![op](i6.png)
```
SELECT *
FROM student s
LEFT OUTER JOIN dept d
ON s.did = d.dno;
```
![op](i7.png)
```
SELECT *
FROM student s
RIGHT OUTER JOIN dept d
ON s.did = d.dno;
```
![op](i8.png)
```
SELECT *
FROM student s
FULL OUTER JOIN dept d
ON s.did = d.dno;
```
![op](i9.png)
```
SELECT *
FROM student s
LEFT OUTER JOIN dept d
ON s.did = d.dno;
```
![op](i10.png)
```
SELECT *
FROM student s
RIGHT OUTER JOIN dept d
ON s.did = d.dno;
```
![op](i11.png)
```
SELECT *
FROM student s
FULL OUTER JOIN dept d
ON s.did = d.dno;
```
![op](i12.png)
```
SELECT *
FROM student
CROSS JOIN dept;
```
![op](7.png)
![op](8.png)
![op](9.png)



#virtual lab experiments 

```
 #ist experiments
```
![op](o1.png)
![op](o2-1.png)
![op](o3-2.png)
![op](o4-3.png)

```
#2nd experiment
```
# 2nd experiment

![op](a1.png)
![op](a2.png)



