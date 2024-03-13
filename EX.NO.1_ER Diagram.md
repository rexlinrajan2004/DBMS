# EXP NO 1: ER DIAGRAM CREATION, RELATIONAL MODEL AND SCHEMA GENERATION  
### DATE
## AIM:
<div align="justify">
   To create a ER Diagram for Bank management system or College management system using ERD Plus tool and generate the relational model with schema. 
</div>

## Algorithm
1. Create a login with https://erdplus.com.
2. Create a new ER Diagram with name
3. Create a strong entity, relation and attributes.
4. Create a weak entity, relation and attributes.
5. Specify attributes unique, multivalued and composite attributes.

### ER Diagram 
![image](https://github.com/rexlinrajan2004/DBMS/assets/119406566/8e2e46ee-3e97-4b74-8124-69cf27ff4d4c)


### Relational model
![ER diagram](https://github.com/rexlinrajan2004/DBMS/assets/119406566/9b131d39-bf0e-4f69-910e-5790b39f3884)



### SQL DDL Schema 
CREATE TABLE Student
(
  Name INT NOT NULL,
  Student_ID INT NOT NULL,
  DOB INT NOT NULL,
  Address INT NOT NULL,
  Age INT NOT NULL,
  PRIMARY KEY (Student_ID)
);

CREATE TABLE Course
(
  Course_name INT NOT NULL,
  Course_code INT NOT NULL,
  slot INT NOT NULL,
  time INT NOT NULL,
  PRIMARY KEY (Course_code)
);

CREATE TABLE faculty
(
  name INT NOT NULL,
  Salary INT NOT NULL,
  ID INT NOT NULL,
  Age INT NOT NULL,
  PRIMARY KEY (ID)
);

CREATE TABLE Department
(
  Dept_ID INT NOT NULL,
  Dept_name INT NOT NULL,
  PRIMARY KEY (Dept_ID)
);

CREATE TABLE Exam
(
  Date INT NOT NULL,
  Venue INT NOT NULL,
  Time INT NOT NULL,
  PRIMARY KEY (Date)
);

CREATE TABLE Student_Phone_no
(
  Phone_no INT NOT NULL,
  Student_ID INT NOT NULL,
  PRIMARY KEY (Phone_no, Student_ID),
  FOREIGN KEY (Student_ID) REFERENCES Student(Student_ID)
);

CREATE TABLE faculty_phone_no
(
  phone_no INT NOT NULL,
  ID INT NOT NULL,
  PRIMARY KEY (phone_no, ID),
  FOREIGN KEY (ID) REFERENCES faculty(ID)
);


## RESULT 
<div align="justify">
Thus the ER diagram was drawn and relational diagram, SQL DDL staements are generated using ERD plus tool.
</div>
