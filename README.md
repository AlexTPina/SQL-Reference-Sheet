# SQL-Reference-Sheet
# SQL Reference Sheet

## How to Create a Database
-Syntax
CREATE DATABASE databasename;

-Example
CREATE DATABASE testDB;

## How to Create a Table
-Syntax

CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
   ....
);

-Example: 
"The following example creates a table called "Persons" that contains five columns: PersonID, LastName, FirstName, Address, and City"

CREATE TABLE Persons (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255)
);

## How to Get Everything From a Single Table
-Syntax

SELECT * FROM tablename;

-Example
The following SQL statement selects all the records in the "Customers" table:

SELECT * FROM Customers;

## How to Get One Thing From a Single Table With a "Where" Clause
-Syntax

SELECT column1, column2, ...
FROM table_name
WHERE condition;

-Example
The following SQL statement selects all the customers from the country "Mexico", in the "Customers" table:

SELECT * FROM Customers
WHERE Country='Mexico';

However, numeric fields should not be enclosed in quotes:

SELECT * FROM Customers
WHERE CustomerID=1;

-Operators in the WHERE Clause

=	Equal	
>	Greater than	
<	Less than	
>=	Greater than or equal	
<=	Less than or equal	
<>	Not equal. Note: In some versions of SQL this operator may be written as !=	
BETWEEN	Between a certain range	
LIKE	Search for a pattern	
IN	To specify multiple possible values for a column

## How to Alter a Table
The ALTER TABLE statement is used to add, delete, or modify columns in an existing table.

The ALTER TABLE statement is also used to add and drop various constraints on an existing table.

## How to Add Something to a Table
-Syntax
To add a column in a table, use the following syntax:

ALTER TABLE table_name
ADD column_name datatype;

-Example
The following SQL adds an "Email" column to the "Customers" table:

ALTER TABLE Customers
ADD Email varchar(255);

## How to Edit Something Inside of a Table
-Syntax
To change the data type of a column in a table, use the following syntax:

ALTER TABLE table_name
ALTER COLUMN column_name datatype;

-Example
Look at the "Persons" table:

ID	LastName	FirstName	Address	City
1	Hansen	Ola	Timoteivn 10	Sandnes
2	Svendson	Tove	Borgvn 23	Sandnes
3	Pettersen	Kari	Storgt 20	Stavanger
Now we want to add a column named "DateOfBirth" in the "Persons" table.

We use the following SQL statement:

ALTER TABLE Persons
ADD DateOfBirth date;

Now we want to change the data type of the column named "DateOfBirth" in the "Persons" table.

We use the following SQL statement:

ALTER TABLE Persons
ALTER COLUMN DateOfBirth year;

Notice that the "DateOfBirth" column is now of type year and is going to hold a year in a two- or four-digit format.

## How to Remove Something From a Table
-Syntax
Next, we want to delete the column named "DateOfBirth" in the "Persons" table.
We use the following SQL statement:

ALTER TABLE Persons
DROP COLUMN DateOfBirth;

Also:

-Syntax
The DELETE statement is used to delete existing records in a table.

DELETE FROM table_name WHERE condition;

Note: Be careful when deleting records in a table! Notice the WHERE clause in the DELETE statement. The WHERE clause specifies which record(s) should be deleted. If you omit the WHERE clause, all records in the table will be deleted!

