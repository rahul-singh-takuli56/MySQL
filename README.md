# Notes on mysql:
# Commands in mySql

### Students is table name and S_id, firstname, and lastname are column names.
### mysql -u root -p
- 

1. **Select** -> extract the data from the table.
   - Syntax: `select * from students;`

2. **Select Distinct** -> used to return only different values from the table.
   - Syntax: `SELECT DISTINCT Country FROM Customers;`

3. **Where** -> used to filter the values.
   - Syntax: `select distinct lastname from students;`

4. **Order By** -> used to sort the values in ascending or descending order.
   - Syntax: `select firstname from students order by s_id;`

5. **And Or Not** -> I know

6. **Insert into** -> to add the values in the table
   - Syntax: `Insert into students`

7. **Null values** -> A field with no values. It is different from 0.

8. **Update** -> Modify the existing data on the table.
   - Syntax: `update students set firstname = 'Rahul45', lastname = 'Takuli45' where s_id = 7;`

9. **Delete** -> used to delete existing data/values (whole row of that condition) in the table
   - Syntax: `delete from customer where s_id = 7;`

10. **Top** -> used to specify the number of records in rows
    - Syntax: `select s_id from students where s_id < 4;`

11. **Min and Max** -> used to return min/max value of selected column
    - Syntax: - ` select max(s_id) from students;`<br>

12. **Count** -> use to return the no of rows that matches a specified criteria;
    - Syntax: `select count(s_id) from students where s_id < 45;`

13. **Sum** -> return the sum of numeric columns
    - Syntax: `select sum(s_id) from students;`

14. **Avg** -> return the avg value of numeric columns
    - Syntax:  `select avg(s_id) from students;`

15. **Like** -> The LIKE operator is used in a WHERE clause to search for a specified pattern in a column.
   - The percent sign % represents zero, one, or multiple characters
   - The underscore sign _ represents one, single character
   - Syntax: `select* from students where firstname like 'r%';` 
   - `Select all customers that starts with the letter "a":`

16. **In** -> The IN operator allows you to specify multiple values in a WHERE clause.
   - Syntax: `select* from students where city in ('city1', 'city2', 'city3');`
### SUBQUERY:
- Use to extract date from multiple tabel 
- Syntax: `select name from students where rollno in (select rollno from register where coursecode in ( select coursecode from course where department = 'mca' ) );`

### JOINS: 
Used to combine rows from two or more tables, based on related column between them.A JOIN clause is used to combine rows from two or more tables, based on a related column between them.
17. **Inner Join** -> returns the data which is common in both the tables.
   - Syntax:  `mysql> select orders.order_id, users.username, orders.product_name, orders.order_date FROM orders INNER JOIN users ON orders.user_id = users.user_id;`
18. **Left Join** -> return all the data from left table which is common in right table and returns null if there is no match
   - Syntax: `mysql> select orders.order_id, users.username, orders.product_name, orders.order_date FROM orders LEFT JOIN users ON orders.user_id = users.user_id;`
19. **Right Join** -> return all the data from right tabel which is common in left table and returns null if there is no match
   - Syntax: `mysql> select orders.order_id, users.username, orders.product_name, orders.order_date FROM orders RIGHT JOIN users ON orders.user_id = users.user_id;`
### Full join is not supported in `MYSQL` instead use `UNION` of left and right:
20. Left Join Union Right join
   - `SELECT
    users.email,
    users.username,
    orders.user_id,
    orders.order_id
FROM
    orders
LEFT JOIN
    users ON orders.user_id = users.user_id `
`UNION SELECT 
    users.email,
    users.username,
    orders.user_id,
    orders.order_id
FROM
    users
RIGHT JOIN
    orders ON orders.user_id = users.user_id;
`
21. **Group By** -> The GROUP BY statement groups rows that have the same values into summary rows, like "find the number of customers in each country".The GROUP BY statement is often used with aggregate functions (COUNT(), MAX(), MIN(), SUM(), AVG()) to group the result-set by one or more columns.
   - Syntax: `select count(order_id) from orders group by user_id;`
