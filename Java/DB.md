DataBase is collection of data in a format which helps us to access and manage the data easily.

There are different types of data bases 
> RDBMS and non-RDBMS

RDBMS - is Relational DBMS 
non-RDBMS - is non Relational DBMS

The difference between these are RDBMS follows predefined schema, where as non-relational doesnot follows any schema.

Examples of RDMS are oracle, MySql
Examples of nRDBMs are postgre, log4j

Data base creation using oracle software

> Oracle is an RDBMS -> Relational Data Base Management System, which is a SQL database -> Structured Query Language.

Steps to create database in oracle.

	-> connect as admin : conn /as sysdba;
	-> create user : create user `username` identified by `password`;
	-> Grant permission to connect and use database : grant connect, resource to `username`;

	-> To connect : conn `username`/`password`;

>> SQL sub catagories :

	-> DDL, DML, DRL, DCL, TCL

	> DDL commands : create, alter, drop, truncate, rename	-> Autocommited
	> DML commands : insert, update, delete									-> not autocommited
	> DRL commands : select
	> DCL commands : grant, revoke
	> TCL commands : commit, rollback

	> DDL : Data Definiton Language. The commands used in DDL are
					
				-> create : to create a table.
				-> alter  : to alter the table.
				-> drop   : to drop the entire table or delete.
				-> truncate: only data in the specific table is delete, and the table will be empty.
				-> rename : to rename the table name.

	> Syntax to create table : create table `table name` (rows and columns)
			eg: create table employees(empid number(10), empname varchar(20), empsal number(10));
	
	> To see the table created, enter the command : desc `table name`;

	> Different use cases of "alter"
			
			->to add extra column : alter table `table name` add `column name with data type`;
			->to drop the column : alter table `table name` drop column `column name`;
			->to rename the coulum: alter teble `table name` column `previous name` to `changing name`;
			->to modify the datatype: alter table `table name` modify `column name` datatype;


	>DML : Data Management Language : The commands used in this are 

			-> insert : to insert the data into the table.
						syntax : insert into `table name` values(values acc to datatypes);
	> To retrive the data from the table we have to use : select * from `table name`;


	>DCL : Grant, Revoke
	-> This format is used when we want to grant or revoke access to the data.

	>TCL : Transaction Control Language
	-> This format is used to maintain integrity in the transactions.

	>DRL : Data Retrival Language
	-> This format is used to retrive the data from the database with a command called SELECT.


>> CONSTRAINTS :
		-> Constraints are nothing but rules or restrictions which are imposed on the data.

	> Domain integrity constraints
		-> Not null : This contraint is used to avoid the data which is null.

		-> check : This constraint is used to check the data based on a condition. Like, the name of the employee should not exceed 10chars.

	> Entity integrity constraints
		-> Primary : This constraint is a combination of not null and unique. The data which we give should not be null and duplicate. only one primary key is allowed per table.

		-> Unique : This constraint make sure that the data given is unique or not.


	> Referential integrity constraints
		-> Foreign key : This is constraint is used to get the data which is mapped to the column of one table to another table.


	If the data which we given violates the constraints rules then an error will be thrown by the oracle sql server showing the name of the constraint. If we define the name of the constraint then it will show that one, or else oracle itself gives a name and throws the error.

	It is best practice to write the name of the constraints, which will be easy to know where the specific error occurred.
	
	-> constraints are of 3 types 
		*Column level - which will be given along with column definition.
		*Table level - which will be given in the last after giving the values.
		*Alter - used to alter the data.

		->* Only one primary key is allowed per table and if we want to use two columns as primary keys then we have to use composite primary key.


		-> When there is a relation between two tables i.e, parent-child relation, then we cannot delete the parent record, which child exists. By using "ON DELETE CASCADE" we can delete the parent record, even though there is a child.

>> JOINS

	-> A join is a temporary relation between the common columns of the table. It is a mechanism to retrieve data from more than one database tables.

	>Cross join : It retrieves the data with all possible combinations.

	>Inner join : It retrieves the data from different tables with matching columns.



JPA

Hibernate is one of the tool of ORM which is an implementation of jpa specification

ORM -> Object Relational Mapping is an object which is having is-a and has-a relationship



-------------------------------------------------------------------------------------------------------------------------------------------

SQL -> Structured Query Language

SQL is written to retrive and manage the data in RDBMS.

Relational Data Base Management System is a collection of computer programs, that provides a way to store and retrive the data, and SQL is nothing but instructions that tells RDBMS to what to do.


The basic syntax of sql goes like, Select the columns from the table name where the condition is so and so.
There are different types of operators or keywords which helps us to get the result in desired manner.

AND -> this keyword is used to get the data columns from the table where both the conditions where satisfied
OR  -> this keyword is used to get the data columns from the table where atleast one condition needs to be satisfied
ORDER BY -> this is used to get the data in an orderd manner for a preferred column in alphabetical or numerical order in ascending
LIKE operators
Wildcard (%)  ->when we want to get the data that starts from specific word or letter then % is used at the of the WORD%. Similarly if we want to get the data which ends with a specific word then we have to use the % at front of %WORD.
and if we want to get the data if that contains a specific word then we have to write like %WORD%
