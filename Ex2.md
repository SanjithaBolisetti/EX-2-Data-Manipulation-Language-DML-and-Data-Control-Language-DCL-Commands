# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
### Date:

## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
UPDATE MANAGER SET SALARY=(SALARY*0.10)+SALARY;
```
### OUTPUT:
![image](https://github.com/SanjithaBolisetti/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393633/a8843b5a-2219-4c38-8c4a-92fbd4e9322b)



### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```
DELETE WORKER FRPM MANAGER WHERE SALARY<2750;
```

### OUTPUT:
![image](https://github.com/SanjithaBolisetti/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393633/4fffac4e-230a-4c25-9ac4-681124979455)



### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```
SELECT ENAME AS 'NAME' ,SALARY * 12 AS 'ANNUAL SALARY' FROM MANAGER;
```

### OUTPUT:
![image](https://github.com/SanjithaBolisetti/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393633/c8eeceff-7e20-4288-8fa9-9c6c11301881)



### Q5)	List the names of Clerks from emp table.


### QUERY:
```
SELECT ENAME FROM MANAGER WHERE DESIGNATION='CLERK';
```

### OUTPUT:
![image](https://github.com/SanjithaBolisetti/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393633/10088bd7-599e-4f36-a6a2-1ae5a8080a22)

### Q6)	List the names of employee who are not Managers.


### QUERY:
```
SELECT ENAME FROM MANAGER WHERE DESIGNATION != 'MANAGERS';
```


### OUTPUT:
![image](https://github.com/SanjithaBolisetti/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393633/36b6838c-bae1-4f37-b08e-3c1a5e5c1002)



### Q7)	List the names of employees not eligible for commission.


### QUERY:
```
SELECT ENAME FROM MANAGER WHERE COMMISSION=0;
```

### OUTPUT:
![image](https://github.com/SanjithaBolisetti/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393633/88ad2b4d-7bb5-4158-9d70-ec77d2aae863)


### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:
```
SELECT ENAME FROM MANAGER WHERE ENAME LIKE 'S%' OR ENAME LIKE '%S';
```

### OUTPUT:
![image](https://github.com/SanjithaBolisetti/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393633/c6731be9-ac28-4e58-b9d2-f01d7a500b4a)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```
SELECT ENAME,DESIGNATION,DEPTNO,HIREDATE FROM MANAGER ORDER BY HIREDATE ASC;
```

### OUTPUT:
![image](https://github.com/SanjithaBolisetti/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393633/9c3b2475-5d3f-4be7-8baf-2258af5f5cc2)



### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```
SELECT * FROM MANAGER WHERE HIREDATE < '30 SEP 81';
```

### OUTPUT:
![image](https://github.com/SanjithaBolisetti/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393633/77a50f94-0847-4fff-8f66-7fcc3332291d)




### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```
SELECT ENAME,DEPTNO,SALARY FROM MANAGER ORDER BY DEPTNO ASC,SALARY DESC;
```

### OUTPUT:
![image](https://github.com/SanjithaBolisetti/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393633/d97b720f-6e6b-4065-92fd-ef8336e7c8be)


### Q12) List the names of employees not belonging to dept no 30,40 & 10

### QUERY:
```
SELECT ENAME FROM MANAGER WHERE DEPTNO NOT IN(30,40,10);
```

### OUTPUT:
![image](https://github.com/SanjithaBolisetti/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393633/c5bd1deb-95c3-4651-bf3a-da21124670fc)



### Q13) Find number of rows in the table EMP

### QUERY:
```
SELECT COUNT(*) AS NUM_ROWS FROM MANAGER;
```


### OUTPUT:
![image](https://github.com/SanjithaBolisetti/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393633/bd64d652-52a1-4440-b2ca-ae1aac92cc84)



### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```
SELECT MAX(SALARY) AS MAX_SALARY,MIN(SALARY) AS MIN_SALARY,AVG(SALRY) AS AVG_SALARY FROM MANAGER;
```


### OUTPUT:
![image](https://github.com/SanjithaBolisetti/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393633/c310ac55-d933-4142-98ab-4ba1bac62ea2)


### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT DESIGNATION,COUNT(*) AS NUM_EMPLOYEES FROM MANAGER GROUP BY DESIGNATION ORDER BY NUM_EMPLOYEES DESC;
```

### OUTPUT:
![image](https://github.com/SanjithaBolisetti/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119393633/3a3e76d4-42af-4033-98c7-6e04c2a3f965)

### Result:
Executing DML queries using SQL is executed successfully.

