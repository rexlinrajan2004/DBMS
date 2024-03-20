# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.

# THEORY
## DML(Data Manipulation Language)
*  The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements.
*  It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.

## List of DML commands: 
1. INSERT: It is used to insert data into a table.
2. UPDATE: It is used to update existing data within a table.
3. DELETE: It is used to delete records from a database table.
4. SELECT: The SELECT command shows the records of the specified table.

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
update manager set salary=salary+(salary*0.10);
```


### OUTPUT:
![Screenshot 2024-03-20 104055](https://github.com/divyadivya10/DBMS/assets/119560271/724e8239-542d-4934-b4fb-49fff54f2a51)


### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```
delete from manager where salary<2750;
```

### OUTPUT:
![Screenshot 2024-03-20 104107](https://github.com/divyadivya10/DBMS/assets/119560271/40ad4278-94d1-4272-bb20-1701cc2bb253)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```
select ename as "Name",salary*12 as "Annual salary" from manager;
```

### OUTPUT:
![Screenshot 2024-03-20 104121](https://github.com/divyadivya10/DBMS/assets/119560271/8f445091-2bbf-4655-9dde-0882645118a5)


### Q5)	List the names of Clerks from emp table.


### QUERY:
```
select ename from manager where designation='clerk';
```


### OUTPUT:

![Screenshot 2024-03-20 104134](https://github.com/divyadivya10/DBMS/assets/119560271/039761d7-46bc-4cfa-b914-e896a81f370f)



### Q6)	List the names of employee who are not Managers.

### QUERY:
```
select ename from manager where designation <> 'manager';
```


### OUTPUT:
![Screenshot 2024-03-20 104159](https://github.com/divyadivya10/DBMS/assets/119560271/aeeed000-d241-4a56-b9f2-f608caaf7c2d)



### Q7)	List the names of employees not eligible for commission.


### QUERY:
```
select ename from manager where commission=0;
```


### OUTPUT:
![Screenshot 2024-03-20 104211](https://github.com/divyadivya10/DBMS/assets/119560271/82f02b48-08d4-4842-8cb2-0d2e13c00a01)



### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```

### OUTPUT:
![Screenshot 2024-03-20 104224](https://github.com/divyadivya10/DBMS/assets/119560271/62970562-c9df-47d4-8fa2-bfc5eaeadea3)



### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```


### OUTPUT:
![Screenshot 2024-03-20 104235](https://github.com/divyadivya10/DBMS/assets/119560271/d808e790-d3a2-4bf4-a8ec-ff672fd3742e)


### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```
select * from manager where hiredate<str_to_date('1981-09-30','YYYY-MM-DD');
```

### OUTPUT:
![Screenshot 2024-03-20 104248](https://github.com/divyadivya10/DBMS/assets/119560271/50b67412-0077-4f56-ad80-35508226d4af)


### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```

 select ename,deptno,salary from manager order by deptno asc,salary desc;
```

### OUTPUT:
![Screenshot 2024-03-20 104343](https://github.com/divyadivya10/DBMS/assets/119560271/c30506d8-5081-41ca-a0a1-576e636a2421)



### Q12) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```
### OUTPUT:
![Screenshot 2024-03-20 104356](https://github.com/divyadivya10/DBMS/assets/119560271/8d292810-2736-4d1e-841b-813082fc23cf)


### Q13) Find number of rows in the table EMP

### QUERY:
```
 select count(*) from manager;
```

### OUTPUT:

![Screenshot 2024-03-20 104406](https://github.com/divyadivya10/DBMS/assets/119560271/1b0515a1-7e12-4d92-8947-394b53a715ed)


### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```
select max(salary) as MAX,min(salary) as MIN, avg(salary) as AVG from manager;
```



### OUTPUT:

![Screenshot 2024-03-20 104417](https://github.com/divyadivya10/DBMS/assets/119560271/60b0a6e7-66f4-4b50-96e3-af9ad9da8feb)


### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```


### OUTPUT:

![Screenshot 2024-03-20 104427](https://github.com/divyadivya10/DBMS/assets/119560271/6efeb13d-5412-4b97-ab08-8f3d5345b266)


## RESULT :
Thus the basic DML commands are executed.
