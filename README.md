# sql-imp-interview-que
Q1- 2nd highest salary in employee table
Ans- MySQL- select salary from employee order by salary desc limit 1,1;
 Oracle- select max(salary) from employee where salary<(select max(salary) from employee);

Q2- Nth highest salary 
Ans- MySQL- select salary from employee order by salary desc limit n,n;
 Oracle- select min(salary) from (select salary from employee order by salary desc) where rownum<=2;

Q3-Department wise highest salary
Ans- Mysql- select max(salary), dept from employee group by dept
	select name, population , countrycode from city where population in
 		(select max(population) from city group by countrycode);


Q4-Alternate records from table
ans- select * from (select name, rownum rn from employee) where mod(rn, 2)<>0;
    select * from (select name, rownum rn from employee) where mod(rn, 2) = 0;
    select * from (select name, rownum rn from employee) where mod(rn, 2)<>1;
	
Q5-find the frequency of any name and name of the person
ans- mysql - select name , count(*) from employees group by name;

Q6- Pattern matching in sql (starts with "Char"/ ends with)
Ans-  select name from Table_name where name like "M%"  (starts with M)
    select name from Table_name where name like "%M"  (ends with M)
    select name from Table_name where name like "s_m%" (S "any char" M what ever string)

Q7- Display Nth row in SQl
Ans-  select * from (select emp.*, rownum r from employee) where r=n;
  **For multiple records**
  select * from (select emp.*,rownum r from employee) where r in (x,y,z); *Here x,y,z are the multiple rows to be fetched*

Q7-What is union and union all?
Ans- Union- Used for displaying data from the result of two select statements excluding duplicates
     Union ALL- Used for displaying data from result of two or more select statements including duplicates
     select * from table1
     union
     select * from table2;
   **************************
     select * from table1
     union all
     select * from table2;
    
Q8-
     
