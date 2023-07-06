# [**Refrence**](https://www.webcodeexpert.com/2017/05/most-important-sql-server-interview.html)

---


### **MOST IMPORTANT SQL SERVER INTERVIEW QUESTIONS AND ANSWERS :**

> **Introduction:** In this article i am  going  to explain frequently asked top most  important sql server interview questions and answers.
>  This will help fresher/starting level candidates to improve their sql and clear interview. 
> It will also help intermediate level candidates to brush up their sql skills.

### **First of all:**
How to create table for Employee?
>
> ---
> 
> create table Employee
(
            EmployeeId    int Primary key identity(1,1),
            FirstName      varchar(50),
            LastName       varchar(50),
            Salary             decimal(18,2),
            JoiningDate    date,
            Department   varchar(50)
)
>
> ---
> 

Also read my article Create table in sql server with auto increment primary key column


How to Insert value in Employee Table?
    
> Insert Into Employee values ('Vikas', 'Verma', 40000, '2016-05-21', 'IT')
 Insert Into Employee values ('Anil', 'Kumar', 800000, '2015-10-31', 'Insurance')
 Insert Into Employee values ('Vishal', 'Sonkar', 700000, '2015-12-09', 'Banking')
 Insert Into Employee values ('Abhishek', 'Singh', 44000, '2015-02-19', 'Insurance')
 Insert Into Employee values ('Durgesh', 'Tiwari', 33000, '2015-12-07', 'Insurance')
 Insert Into Employee values ('Ravi', 'Kumar', 55000, '2016-03-31', 'Services')
 Insert Into Employee values ('Lalit', 'Raghuvanshi', 88000, '2016-09-26', 'Services')
 Insert Into Employee values ('Sandeep', 'Kumar', 70000, '2015-02-01', 'Insurance')
>
> ---
> 

We have some other options to insert data in table. Please read the article Multiple ways to insert records in sql table.

### **How to show table data?**

> select *  from Employee

**Employee table will look like :**

EmployeeId | FirstName | LastName | Salary | JoiningDate | Department
--- | ----- | ----- | -----|
1    |
Vikas
Verma
40000.00
2016-05-21
IT
2
Anil
Kumar
800000.00
2015-10-31
Insurance
3
Vishal
Sonkar
700000.00
2015-12-09
Banking
4
Abhishek
Singh
44000.00
2015-02-19
Insurance
5
Durgesh
Tiwari
33000.00
2015-12-07
Insurance
6
Ravi
Kumar
55000.00
2016-03-31
Services
7
Lalit
Raghuvanshi
88000.00
2016-09-26
Services
8
Sandeep
Kumar
70000.00
2015-02-01
Insurance

### **Now create a new table "Incentive"** 

> CREATE TABLE Incentives(
>            EmployeeRefId          int,
>            IncentiveDate           date,
>            IncentiveAmount      decimal(18,2)
>)
>
> ---
>
> 
### **Insert values into this table :**

> insert into Incentives values(1, '2015-09-21', 10000)
> insert into Incentives values(2, '2014-12-25', 8000)
> insert into Incentives values(3, '2015-05-30', 6000)
> insert into Incentives values(1, '2016-09-12', 3000)
> insert into Incentives values(2, '2016-02-25', 11000)

### **Show table data**
> select *  from Incentives

### **Incentives table will look like :** 

EmployeeRefId
IncentiveDate
IncentiveAmount
1
2015-09-21
10000.00
2
2014-12-25
8000.00
3
2015-05-30
6000.00
1
2016-09-12
3000.00
2
2016-02-25
11000.00


Now let’s apply some simple queries on the table created above:
>
> ---
> 
> * Get all Employee details from the Employee table?
> select * from Employee

> * Get EmployeeId, FirstName, LastName from Employee table?

    select EmployeeId, FirstName, LastName from Employee

> * Get FirstName from Employee table using alias name **“Employee Name”**
> select FirstName as EmployeeName  from Employee

* Get FirstName from Employee table in upper case?
> select UPPER(FirstName) from Employee

* Get FirstName from Employee table in lower case?
> select LOWER(FirstName) from Employee

* Get unique Department from Employee table?
> select distinct Department from Employee

* Select first 3 characters of FirstName from Employee table.
> select SUBSTRING(FirstName,0,4) from Employee

* Get position of 'k' in name 'Vikas' from Employee table
> select CHARINDEX ('k', FirstName) from Employee where FirstName='Vikas'

* Get FirstName from Employee table after removing white spaces from right side?
> select RTRIM(FirstName) from Employee

* Get FirstName from Employee table after removing white spaces from right side?
> select LTRIM(FirstName) from Employee

> * Get length of FirstName from Employee table?

     select LEN(FirstName) from Employee

> * Get FirstName from Employee table after replacing 'V' with 'VV'

     select REPLACE(FirstName,'V','VV') from Employee

> * Get FirstName and LastName as single column from Employee table separated by
'-' ?
> select FirstName +' - '+ LastName as FullName from Employee

Also read my article Concatenating first,middle and last name in sql server

> * Get FirstName , Joining year, Joining Month and Joining Date from Employee table ?

select YEAR(JoiningDate) AS [Year] , MONTH(JoiningDate) as [Month],
DAY(JoiningDate) as [Day] from Employee

1)   Get all employee details from the Employee table order by FirstName Ascending?

select * from Employee order by FirstName asc 

16)  Get all employee details from the Employee table order by FirstName descending?

select * from Employee order by FirstName desc 

17)  Get all employee details from the Employee table order by FirstName Ascending and Salary descending?

select * from Employee order by FirstName asc, Salary desc 

18)  Get employee details from Employee table whose employee name is “Vikas”?

select * from EMPLOYEE where FirstName='Vikas'

19)  Get employee details from Employee table whose employee name are “Vikas” and “Lalit”?

select * from Employee where FirstName in ('Vikas','Lalit')

20)  Get employee details from Employee table whose employee name are not “Vikas” and “Lalit”?

select * from Employee where FirstName not in ('Vikas','Lalit')

21)  Get employee details from Employee table whose FirstName starts with 'V'

select * from Employee where FirstName like 'V%'

22)  Get employee details from Employee table whose FirstName contains 'k'

select * from Employee where FirstName like '%k%'

23)  Get employee details from Employee table whose FirstName ends with 's'

select * from Employee where FirstName like '%s'

24)  Get employee details from Employee table whose Salary is greater than 70000?

select Salary from Employee where Salary>70000

25)  Get employee details from Employee table whose Salary is less than 70000?

select Salary from Employee where Salary<70000

26)  Get employee details from Employee table whose Salary is between 50000 and 70000?
select Salary from Employee where Salary between 50000 and 70000

27)  Get employee details from Employee table whose joining year is “2015”?

select * from Employee where YEAR(JoiningDate)='2015'

28)  Get employee details from Employee table whose joining month is “February”?

select * from Employee where DATENAME(month, JoiningDate)='February'

29)  Get employee details from Employee table who joined before 20th June, 2015?

select * from EMPLOYEE where JoiningDate > '2015-06-20'

30)  Get employee details from Employee table who joined before 20th June, 2015?

select * from EMPLOYEE where JoiningDate < '2015-06-20'

31)  Get FirstName, JoiningDate and IncentiveDate from Employee and Incentives table?

select FirstName, JoiningDate, Incentivedate from Employee EMP INNER JOIN incentives INC on EMP.EmployeeId = INC.EmployeeRefId

32)  Get Last Name from Employee table after replacing special character (e.g. % (if any)) with white space?

select REPLACE(LastName,'%',' ') as LastName from Employee

33)  Get department, total salary with respect to a department from Employee table?

select Department,SUM(SALARY) TotalSalary from Employee group by department

34)  Get Department, TotalSalary with respect to a department from Employee table order by total salary descending?

select Department, SUM(Salary) as TotalSalary from Employee group by Department order by Salary desc

35)  Get department, no of employees in a department, salary with respect to a department from Employee table order by salary descending?

select Department,COUNT(FirstName) as TotalEmployee, SUM(Salary) as Salary from Employee group by DEPARTMENT order by Salary desc

36)  Get department wise average salary from employee table order by salary ascending?

select Department,AVG(Salary) as AvgSalary from Employee group by Department order by AvgSalary asc

37)  Get department wise maximum salary from Employee table order by salary ascending?

select Department, MAX(Salary) as MaxSalary from Employee group by Department order by MaxSalary asc

38)  Get department wise minimum salary from Employee table order by salary ascending?

select Department,MIN(SALARY) MinSalary from Employee group by Department order by MinSalary asc

39)  Select number of employees joined with respect to year and month from Employee table?

select DATEPART (YYYY,JoiningDate) JoiningYear,DATEPART (MM,JoiningDate) JoiningMonth,COUNT(*) TotalEmployee from
Employee group by DATEPART(YYYY,JoiningDate), DATEPART(MM,JoiningDate)


40)  Select department,  salary with respect to a department from Employee table where  salary greater than 60000 order by Salary descending

select Department,SUM(SALARY) TotalSalary from Employee group by Department having SUM(SALARY) > 60000 order by TotalSalary desc

41) Select FirstName, incentive amount from Employee and incentives table for those employees who have incentives?

select FirstName,IncentiveAmount from Employee EMP INNER JOIN Incentives INC on EMP.EmployeeId = INC.EmployeeRefId

42)  Select First Name, incentive amount from Employee and incentives table for those employees who have incentives and incentive amount greater than 5000

select FirstName,IncentiveAmount from Employee EMP INNER JOIN Incentives INC on EMP.EmployeeId = INC.EmployeeRefId and IncentiveAmount > 5000

43)  Select First Name, incentive amount from Employee and Incentives table for all Employees even if they didn't get incentives?

Select FirstName,IncentiveAmount from Employee EMP LEFT JOIN Incentives INC on EMP.EmployeeId = INC.EmployeeRefId

44)  Select First Name, incentive amount from Employee and Incentives table for all Employees even if they didn't get incentives and set incentive amount as 0 for those employees who didn't get Incentives?

Select FirstName, ISNULL (IncentiveAmount,0) AS IncentiveAmount from Employee EMP LEFT JOIN Incentives INC on EMP.EmployeeId = INC.EmployeeRefId

45)  Select First Name, incentive amount from Employee and incentives table for all Employees who got incentives using right join?

Select FirstName, ISNULL (IncentiveAmount,0) AS IncentiveAmount from Employee EMP RIGHT JOIN Incentives INC on EMP.EMPLOYEEID =INC.EmployeeRefId

46)  Select max incentive with respect to employee from Employee and incentives table using sub query?

select Department,(select ISNULL(MAX(IncentiveAmount),0) from INCENTIVES where EmployeeRefId = EmployeeId)
MaxIncentive from Employee

47)  Select TOP 2 salary from Employee table?

select top 2 * from Employee order by salary desc


48)  Select second, third, fourth or nth highest/maximum salary of employee from Employee table?

For this Read article Query to get second, third,fourth or nth highest/maximum salary of employee.

49)  Select FirstName, LastName from Employee table as separate rows?

select FirstName from Employee
union
select LastName from Employee

50)  What is the difference between UNION and UNION ALL?

Both UNION and UNION ALL concatenate the result of two different SQLs. They differ in the way they handle duplicates.
              UNION performs a DISTINCT on the result set, eliminating any duplicate rows.
              UNION ALL does not remove duplicates and it therefore faster than UNION.

Note: While using this commands all selected columns need to be of the same data type.

51)  Select Employee details from employee table if data exists in incentive table?

select * from Employee where exists (select * from Incentives)

52)  Get Employee Id's of those employees who didn't receive incentives without using sub query?

select EmployeeId from Employee
MINUS
select EmployeeRefId from Incentives

53)  Select 20 % of salary from Vikas, 10% of Salary for Anil and for other 15 % of salary from employee table?

SELECT FirstName, CASE FirstName WHEN 'Vikas' THEN Salary * .20 WHEN 'Anil' THEN Salary * .10 ELSE Salary * .15 END "SalaryAmount" FROM
Employee


54)  Select Banking as 'Bank Dept', Insurance as 'Insurance Dept' and Services as 'Services Dept' from employee table?

SELECT case Department when 'IT' then 'Information technology' when 'Banking' then 'Bank Dept' when 'Insurance' then 'Insurance Dept' when
'Services' then 'Services Dept' END as Department FROM Employee

To know more about SELECT CASE in Sql read article: Examples to use case expression in select statement in sql server


55)  Write a query to rank employees based on their incentives for a month?

select FirstName,IncentiveAmount,DENSE_RANK() OVER (PARTITION BY IncentiveDate ORDER BY IncentiveAmount DESC) AS [Rank] from Employee a,
Incentives b where a.EmployeeId = b.EmployeeRefId

56)  Update IncentiveAmount to 9000 in incentive table where employee First Name is Vishal in Employee table?

update Incentives set IncentiveAmount = '9000' where EmployeeRefId =(select EmployeeId from Employee where FirstName = 'Vishal')


Now lets understand how to add or drop foreign key constraint on table

57)  Write syntax to create Employee table?

CREATE TABLE Employee
(
EmployeeId int NOT NULL,
FirstName varchar(50) NULL,
LastName varchar(50) NULL,
Salary decimal(18, 0) NULL,
JoiningDate datetime2(7) default getdate(),
Department varchar(50) NULL
)


58)  Write syntax to set EmployeeId as primary key in Employee table?

ALTER TABLE Employee ADD CONSTRAINT EMPLOYEE_PK PRIMARY KEY(EmployeeId)


59)  Write SQL syntax to set 2 fields(EmployeeId ,FirstName) as primary key in Employee table

ALTER TABLE Employee  ADD CONSTRAINT EMPLOYEE_PK PRIMARY KEY(EmployeeId, FirstName)

60)  Write syntax to drop primary key on Employee table?

ALTER TABLE Employee  DROP CONSTRAINT EMPLOYEE_PK;

61)  Write SQL syntax to create EmployeeRefId in Incentives table as foreign key with respect to EmployeeId in employee table?

ALTER TABLE Incentives ADD CONSTRAINT INCENTIVES_FK FOREIGN KEY (EmployeeRefId) REFERENCES Employee(EmployeeId)

To know more about Primary and Foreign key read article Difference between primary key and foreign key in sql server

62)  Write SQL syntax to drop foreign key on employee table?

ALTER TABLE Incentives DROP CONSTRAINT INCENTIVES_FK;

63) Write syntax to delete employee table?

DROP table Employee 