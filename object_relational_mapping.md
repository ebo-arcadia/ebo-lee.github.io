# Object
- Understand what is ORM and why use it
- Know how Objects and database interact with each
- Know how to use SQLAlchemy
__________


## What is SQLAlchemy?

SQL toolkit and object relational mapper used to map classes to the database

## What is ORM (object-oriented)?

A programming technique used to convert data between incompatible type systems in object-oriented languages

## What problems or issues does it solve?

it allows object model and database to develop in a cleanly decoupled way

## What are the key components?

SQL rendering engine
DBAPI integration, transaction integration, schema description service
Expression Language, SQL statements, Python OOP, built-in methods
SQL Expressions

## what is SQL expressions?

A language represents the primitive constructs of reh relational database

## How to use SQLAlchemy?
- what is SQL expressions statements?
  - SELECT, INSERT, UPDATE, DELETE
- how SQL expressions are constructed using methods relative to a class object? 
  - update() => UPDATE; delete() => DELETE; select() => SELECT
- how to insert values into a table?
  - <object>.insert().values(<column_header_name> = "value")
- how to execute SQL expressions in the context of ORM?
  1. obtain a connection object using DBAPI connection resource
     * e.g. conn = engine.connect()
  2. Feed the expression object to the connection object's inherited method execute()
     * e.g. ins = advisor.insert().values(name="mutual fund", fund="Vanguard 500")
- how to select rows in a table object?
  1. create an object using select() method
  2. construct SQL SELECT expression using Python Str() method
  3. execute SQL SELECT expression using execute() passing the object as a parameter
  4. stores data in a variable
  5. fetch data by executing fetchone() method on the variable
  6. appending the where clause with filtering criteria to filter fetched data
- how to update values in a table?
  1. create an object using update() method
  2. append where() clause with parameter to select a specific column
  3. append values() clause and new value as the parameter
  4. store the object in a statement or variable
  5. execute SQL expression using execute() passing the statement as a parameter
- how to delete rows or values in a table?
  1. run delete() on a target table object
  2. append where() clause passing parameter to select specific column value to delete
  3. store the above operation in a variable or statement
  4. execute SQL delete expression using execute() passing the delete statement as a parameter
- how to execute compound select clauses and eliminate duplicates after querying a table?
  1. create two or three SQL queries statements using select() function
  2. call union() method to a query statement passing the other two statements as parameters
  3. store the object in a variable
  4. execute the statement using DB connection object passing the variable
- how to select rows from a table while excluding certain rows?
  1. using except_() function to construct an SQL except statement object passing two select statements as parameters
  2. executing the object using database connection object
- how to query common rows using multiple select statements?
  1. using intersect() function to create an object passing two select statements as parameters
  2. executing the object using database connection object
- how to interact with database using ORM principle?
  1. import sessionMaker module from sqlalchemy
  2. construct a session class and bound it to the engine object using sessionmaker(bond=engine) configurable method
  3. create session object using Session class to inherit methods such as begin(), add(), etc
  4. call inherited built-in methods on the session object
- how to facilitate associating user-defined Python classes with database tables using declaring mapping?
  1. import declarative base from sqlalchemy ext library
  2. create a declarative base class
  3. create a mapped class containing table to be created passing the base as parameter
  4. using metadata collection adn create_all() method to create database and tables passing engine object as source of db connectivity
- how to persist data to a table using object of a mapped class?
  1. declare an SQL statement using the mapped class passing parameters corresponding to each table column with value
  2. store the statement in a variable
  3. add the statement to the session object passing add() or add_all() method with the variable as parameter
  4. flush the transaction to execute the statement by calling commit() on the session object
- how to modify or update a table using mapped objects?
  1. fetch the content from a table needs to be updated using session object, query(Table Class), and get()
  2. store the content in a variable
  3. assign new values to the attribute of the object
  4. commit the transaction using commit()
  5. using update() to update bulk of attributes passing object of arrays and synchronize_session
- how to customize returned result sets when querying tables?
  1. create session object using sessionmaker library
  2. apply query() with table object as parameter to the session object
  3. apply filter() along with operators
  4. iterate the returned object and display associating attributes
- how to use string-based SQL statement with ORM mapped class and object?
  1. pass SQL statement as string type to text() and subsequently pass it to filter()
  2. call one(), first(), or all() to fetch the result set
  3. return or print the data in the object using for loop
- how to create multiple tables, glue them using relational database principles?
  1. create the parent table along with mapped class
  2. create the child table adding foreign key directive to a column constrained to a column in the parent table
  3. import and use sqlalchemy ORM API directive relationship() 
  4. apply relationship() to the parent table linking it to the child table via attribute with the help of foreign key directive
  5. apply relationship() to the child table linking it to the parent table via attribute with the help of foreign key directive
- how to insert data into a parent table while establishing a relationship with its child table?
  1. construct an SQL insert statement using class object passing rows as parameters
  2. construct an insert statement with data to be inserted into the child table as parameters
  3. pass the statement to the attribute of the parent object established with relationship() module
  4. call either all() or add_all() to the statement object
  5. execute the commit using session or db_connector object using sessionmaker() class
- how to conditionally query two relational tables in a database when there is no or only one foreign key?
  1. load two tables as parameters using query() object
  2. append filter() passing columns from the parent and child table which relationship is established with foreign key construct
  3. append all() to return the result set
  4. using python iterator to display data stored as attributes
- how to conditionally query two relational tables in a database when there are more than one foreign key?
  1. construct a statement querying the child table
  2. call subquery() to construct an SQL SELECT statement embedded within an alias
  3. construct another statement using query() passing the parent table along with the object statement from above
  4. calling outerjoin() to perform left join passing the columns with key used to link the two tables
  5. use python iterator to iterate and display the nested result set
- how to query many-to-one relational tables conditionally using relational operator?
  1. construct SQL SELECT statement using query() passing the parent table object
  2. apply join() passing child table object as parameter to avoid Cartesian warning
  3. apply filter() passing '__eq__' relational operator with required filter condition
  4. iterate the result set and display data with attributes
- how to query relational tables finding combining common columns using relationship operators?
  1. construct an SQL SELECT statement using table class object for the parent table
  2. use filter() method passing child table, its attribute along with a relationship operator
  3. execute the statement using database connector object or conventionally called session
  4. display result set with python iteration if it is an array of objects
  5. display single object with its attribute if not iterable 
  
------------

## Outcomes
1. imported sqlAlchemy and built-in methods
2. created an object of the Engine class using create_engine()
3. created a database using the Engine object in sqlite in-memory
4. imported classes for creating tables
5. created a table using imported classes and methods
6. stored the table in metadata object
7. created insertion of columns and values as object
8. executed SQL expression to insert columns and values in the database
9. executed one SQL expression to insert a list of dictionaries in the database
10. verified the creation of the table, insertion of columns and values using DB Browser for SQLite 
11. executed SQL SELECT statement to fetch data from the database
12. appended where clause to the SELECT statement to customize fetched data from the database
13. verified fetched data from database in the console
14. executed SQL UPDATE statement to update values in a table using table object
15. executed SQL DELETE statement to delete rows in a table using table object
16. deleted multiple columns, rows, tables using delete object to execute SQL DELETE expression
17. updated multiple rows, columns, and tables suing update object to execute SQL UPDATE expressions
18. executed update operation preserving the order when passing parameters using ordered_value() method
19. executed SQL select expression using select object with JOINS to combine rows and columns from multiple tables
20. formed conjunctions of compound SQL expressions using relational operators including AND, OR, NOT functions
21. rendered generic functions, functions passing columns as parameters with the usage of imported keyword func
22. executed combined SQL query or select statements using union() function also eliminated any duplicates
23. executed SQL except statement using except() function to get rows while excluding certain rows
24. executed SQL intersect statement using intersect function to get and common rows in a table combing multiple select statements
25. created session object using sessionmaker class, bounding to engine object to handle interacting with database
26. facilitated associating python classes with database tables creation using declarative base, metadata attributes, and create_all() binding engine object
27. added a single record or multiple records to a table using mapped class, declared session object, and built-in method add(), add_all() and commit()
28. updated a single row and multiple rows in a table using session object, query, variable assignment, and update()
29. applied filter() along with filter operators (==, !=, in_(), and_(), or_()) to customize database query
30. used literal string SQL expression or statement with query object in python
31. used session object, filter(), text(), with parameters to link textual SQL to ORM mapped columns expression
32. linked tables with relationship patterns, one-to-many, many-to-one, one-to-one, many-to-many using relationship() directive
33. constructed and committed a parent table object to the database providing mapped attributes to establish relationships with its child table
34. inserted multiple rows and columns into a parent table and its child table using add() and add_all()
35. created query on two relational tables using query(), filter(), join(), outerjoin(), subquery()
36. iterated the result set and printed rows and columns joined from two tables
37. queried relational tables with a many-to-one relationship conditionally using relational operator '__eq__' along with filter() and join()
38. resolved cartesian warning and side effect using join() statement
39. queried relational tables filtering common rows & columns using relationship operators include contains(), any(), has(), __ne__(), __eq__()



